# Hydrate an object without use reflection

From the [PHP documentation](http://php.net/manual/en/language.oop5.visibility.php):

> The visibility of a property, a method or (as of PHP 7.1.0) a constant can be defined by prefixing
> the declaration with the keywords public, protected or private. Class members declared public can
> be accessed everywhere. **Members declared protected can be accessed only within the class itself
> and by inheriting classes.** Members declared as private may only be accessed by the class that
> defines the member.

Then, I can write this:

```php
class Entity {
    protected $foo;
    protected $bar;
    protected $baz;

    public function getFoo()
    {
        return $this->foo;
    }

    public function getBar()
    {
        return $this->bar;
    }

    public function getBaz()
    {
        return $this->baz;
    }
}

class EntityHydrator extends Entity
{
    public function hydrate(Entity $entity, array $data)
    {
        $entity->foo = $data['foo'];
        $entity->bar = $data['bar'];
        $entity->baz = $data['baz'];
    }
}

$data = ['foo' => 1, 'bar' => 2, 'baz' => 3];

$entity = new Entity();
$hydrator = new EntityHydrator();
$hydrator->hydrate($entity, $data);

echo $entity->getFoo(); // 1
echo $entity->getBar(); // 2
echo $entity->getBaz(); // 3
```