# How to fix mixed content for Wordpress

When using an Nginx proxy you should add the following piece of code to `wp-config.php`:

```
f ( (!empty( $_SERVER['HTTP_X_FORWARDED_HOST'])) ||
     (!empty( $_SERVER['HTTP_X_FORWARDED_FOR'])) ) {
    $_SERVER['HTTPS'] = 'on';
}
```
