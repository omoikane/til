# Disabling username and password autofill

> Do not use this tip in a login form!

In an attempt to help users, all modern browsers tend to autofill form fields, even when they should not. For example, the browser may confuse a username and password change form for a login form.

The problem is in the "autocomplete" attribute. Web developers have started to abuse the `autocomplete="off"` attribute and this has caused browsers to ignore the `off` value. In reality, the HTML5 standard has also made available a series of very specific values for this attribute, which the browsers know and respect.

In the specific case of the form for changing the username and password, it is sufficient to indicate the correct value for the autocomplete attribute:

```html
<form>
   <label for="username-field">Username</label>
   <input type="text" name="username" id="username-field" autocomplete="username">

   <label for="password-field">Password</label>
   <input type="password" name="password" id="password-field" autocomplete="new-password">
</form>
```

### References:

- [Create Amazing Forms](https://developers.google.com/web/fundamentals/design-and-ux/input/forms/?hl=en#recommended_input_name_and_autocomplete_attribute_values)
- [Autofill HTML Standard](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#autofill)
