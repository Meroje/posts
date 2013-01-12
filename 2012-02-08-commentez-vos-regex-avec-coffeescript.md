---
title: Commentez vos RegEx avec CoffeeScript
categories: [code, snippet]
tags: [javascript, coffeescript]

description: "Javascript, et par extension coffeescript nous permettent de réaliser, entres autres, une pré validation des formulaires côté client, pour améliorer l’expérience de celui-ci. Pour cela nous disposons d’un outil très utile : les regex (ou expressions régulières)."

layout: post
---
Javascript, et par extension coffeescript nous permettent de réaliser, entres autres, une pré validation des formulaires côté client, pour améliorer l'expérience de celui-ci. Pour cela nous disposons d'un outil très utile : les regex (ou expressions régulières).

Cependant il faut bien reconnaitre que ce n'est pas toujours très lisible, surtout en équipe quand le collègue s'est chargé de ces regex.

### Prenons l'exemple d'une validation d'adresse email :

``` js
var emailPattern = /^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$/i;

if ( "john.smith@gmail.com".match( emailPattern ) ) {
   console.log( "E-mail is valid" );
} else {
   console.log( "E-mail is invalid" );
}
```

En regardant uniquement la première ligne, il est très dur (voir impossible pour un débutant) de comprendre ce que fait ce code.

Et c'est là que CoffeeScript nous vient en aide !

### Même si vous n'utilisez pas toutes les subtilités de ce précompileur, il peut vous être très utile !

Observons le même code que précedemment, cette fois ci écrit pour coffeescript :

```coffeescript
emailPattern = /// ^ #begin of line
   ([a-z0-9_.-]+)    #one or more letters, numbers, _ . or -
   @                 #followed by an @ sign
   ([\da-z.-]+)      #then one or more letters, numbers, _ . or -
   \.                #followed by a period
   ([a-z.]{2,6})     #followed by 2 to 6 letters or periods
   $ ///i            #end of line and ignore case

if "john.smith@gmail.com".match emailPattern
   console.log "E-mail is valid"
else
   console.log "E-mail is invalid"
```

Nous voyons dés le premier regard toute la différence qu'apporte ce compileur : _nous pouvons écrire notre regex sur plusieurs lignes_, ce qui nous permet de commenter facilement chaque morceau de cette regex.

[Source](http://www.elijahmanor.com/2012/02/regular-expressions-in-coffeescript-are.html)