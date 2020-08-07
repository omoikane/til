# How to immediately call an anonymous function in PHP

With javascript you can define an anonymous function and execute it immediately:

```js
// JS example
(function () {
	/* do something */
}());
```

## How can you achieve this in PHP?

Before PHP 7 you can use the internal function `call_user_func()`:

```php
call_user_func(function () {
	/* do something */
});
```

From PHP 7 you can use this syntax:

```php
(function () {
	/* do something */
})();
```
