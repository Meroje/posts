---
title: PHP rencontre l'elegance et la beaute, intro a Laravel 3.0
categories: [code, laravel]
tags: [php, laravel, framework]

description: Laravel est un framework dont la motivation première est la beauté du code. Cette nouvelle version, qui arrive moins d’un an après la création de ce framework apporte tout son lot de nouveautées, toutes plus intéressantes les unes que les autres. On y trouvera entre autres les migrations de base de données, l’intégration native des tests unitaires et les modules.

layout: post
---
### Il est là !

Laravel est un framework dont la motivation première est la _beauté_ du code.
Cette nouvelle version, qui arrive moins d'un an après la création de ce framework apporte tout son lot de nouveautées, toutes plus intéressantes les unes que les autres. On y trouvera entre autres les migrations de base de données, l'intégration native des tests unitaires et les modules.

Toutes les notions mentionnées ici sont très bien [documentées](http://laravel.com/docs)

### Les routes

{% highlight php %}
<?php
Route::get('/', function()
{
return View::make('home.index');
});
{% endhighlight %}

Voila à quoi ressemble l'utilisation la plus basique de Laravel.

### Les sessions

Les sessions servent à faire transiter des données entre les pages, Laravel en tire très avantageusement l'utilité.

{% highlight php %}
<?php
return Redirect::to('profile')->with('message', 'Welcome Back!');
{% endhighlight %}

### Les modules (aka. Bundles)

La plus importante innovation apportée par cette version est incontestablement le retour des modules avec une nouvelle intégration bien plus efficace que la précédente.
Un module fonctionne exactement comme l'application principale (votre application est en réalité un module), il devient ainsi très aisé de partager un code à la communautée.  
[Retrouvez les modules ici](http://bundles.laravel.com/) et [apprenez en plus ici](http://laravel.com/docs/bundles)

### Les migrations

Les migrations permettent de définir le schéma de notre base de donnée, et de modifier celui-ci. Il est ainsi possible d'ajouter une colonne à une table, par exemple à partir d'un module afin d'étendre le profil utilisateur.

{% highlight php %}
<?php
Schema::create('users', function($table)
{
	$table->increments('id');
	$table->string('email')->unique();
	$table->string('password');
});
{% endhighlight %}

[Retrouvez les migrations ici](http://laravel.com/docs/database/schema)

### La ligne de commande : Artisan

Laravel se dote d'un outil en ligne de commande qui permet de faciliter un bon nombre d'intéractions avec l'application, comme lancer des tests, installer un module, ou exécuter une migration :

{% highlight sh %}
$ php artisan test

$ php artisan migrate

$ php artisan migrate:rollback
{% endhighlight %}

[Retrouvez artisan ici](http://laravel.com/docs/artisan/commands)

### Les tests unitaires

Laravel propose une intégration inédite et très efficace de PHPUnit, rendant possible de lancer aisément les tests de votre application, d'un module, du framework, ou encore de l'ensemble.

[Retrouvez les tests ici](http://laravel.com/docs/testing)

### Les événements

Un système de gestion des événements simple est inclut dans Laravel, permettant de construire une application encore plus flexible.

### Mangez-en !

J'espère que cet aperçu des nouveautés vous à donné envie de découvrir Laravel plus en profondeur.
Merci de m'avoir lu!

[Source](http://forrst.com/posts/PHP_meet_elegance_Introducing_Laravel_3_0-dfi)