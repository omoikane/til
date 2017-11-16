# Hydrate an object via Closure

In simple terms, a Closure is an anonymous function. However, most of the people are not aware **it can access variables outside the scope that it was created**.

The Closure class in PHP have the special method `bindTo()`. From [documentation](http://php.net/manual/en/closure.bindto.php):

> Closure::bindTo — Duplicates the closure with a new bound object and class scope
>
> ```php
> public Closure Closure::bindTo ( object $newthis [, mixed $newscope = "static" ] )
> ```
>
> The “bound object” determines the value $this will have in the function body and the “class scope” represents
> a class which determines which private and protected members the anonymous function will be able to access.
> Namely, the members that will be visible are the same as if the anonymous function were a method of the class
> given as value of the **newscope** parameter.

Then, I can write this:

```php
class Person
{
    private $name;

    public function getName()
    {
        return $this->name;
    }
}

$person = new Person();

$hydrator = (function (array $data) {
    foreach ($data as $key => $value) {
        $this->{$key} = $value;
    }
})->bindTo($person, get_class($person));

$hydrator([
    'name' => 'Paul'
]);

echo $person->getName(); // echo Paul
```