# Basic Authentication handler
This plugin adds Basic Authentication to a WordPress site.

Note that this plugin requires sending your username and password with every
request, and should only be used over SSL-secured connections or for local
development and testing. Without SSL we strongly recommend using the
OAuth authentication handler in production environments.

## Installing
1. Download the plugin into your plugins directory
2. Enable in the WordPress admin

## Using
This plugin adds support for Basic Authentication, as specified in RFC2617.
Most HTTP clients will allow you to use this authentication natively. Some
examples are listed below.

### cURL

```bas
curl --user admin:password https://example.com/wp-json/
```

### PHP

```php
$args = array(
	'headers' => array(
		'Authorization' => 'Basic ' . base64_encode( $username . ':' . $password ),
	),
);
```
### Angular

```javascript
const httpOptions = {
	headers: new HttpHeaders({
		Authorization:
		"Basic " + btoa( environment.WP_Admin_username + ":" + environment.WP_Admin_password),
	}),
};
```