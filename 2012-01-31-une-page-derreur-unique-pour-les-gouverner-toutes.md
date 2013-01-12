---
title: Une page d'erreur unique pour les gouverner toutes
categories: [code, snippet]
tags: [php, htaccess, http, erreurs]

description: Ce petit code à ajouter à votre .htaccess que je vous propose vous permettra de récupérer toutes les erreurs http avec le message associé, afin de savoir tout de suite à quelle erreur nous avons affaire (utile pendant un développement). Ce code peut également très bien servir de base pour gérer plus efficacement ces erreurs sur un environnement de production, pour être prévenu par email par exemple, ou tout simplement pour avoir une page toute jolie.

layout: post
---

Ce petit code à ajouter à votre ``.htaccess`` que je vous propose vous permettra de récupérer toutes les erreurs http avec le message associé, afin de savoir tout de suite à quelle erreur nous avons affaire (utile pendant un développement). Ce code peut également très bien servir de base pour gérer plus efficacement ces erreurs sur un environnement de production, pour être prévenu par email par exemple, ou tout simplement pour avoir une page [toute jolie](https://github.com/404).

A garder sous la main donc.

### HTACCESS

```apache
ErrorDocument 400 /errors.php
ErrorDocument 403 /errors.php
ErrorDocument 404 /errors.php
ErrorDocument 405 /errors.php
ErrorDocument 408 /errors.php
ErrorDocument 500 /errors.php
ErrorDocument 502 /errors.php
ErrorDocument 504 /errors.php
```

### PHP

```php
<?php
$status = $_SERVER['REDIRECT_STATUS'];
$codes = array(
	400 => array('400 Bad Request', 'The request cannot be fulfilled due to bad syntax.'),
	403 => array('403 Forbidden', 'The server has refused to fulfil your request.'),
	404 => array('404 Not Found', 'The page you requested was not found on this server.'),
	405 => array('405 Method Not Allowed', 'The method specified in the request is not allowed for the specified resource.'),
	408 => array('408 Request Timeout', 'Your browser failed to send a request in the time allowed by the server.'),
	500 => array('500 Internal Server Error', 'The request was unsuccessful due to an unexpected condition encountered by the server.'),
	502 => array('502 Bad Gateway', 'The server received an invalid response while trying to carry out the request.'),
	504 => array('504 Gateway Timeout', 'The upstream server failed to send a request in the time allowed by the server.'),
);

$title = $codes[$status][0];
$message = $codes[$status][1];
if ($title == false || strlen($status) != 3) {
	$message = 'Please supply a valid HTTP status code.';
}

echo '<h1>Hold up! '.$title.' detected</h1><p>'.$message.'</p>';
```

[Source](http://papermashup.com/create-an-error-page-to-handle-all-errors-with-php/)