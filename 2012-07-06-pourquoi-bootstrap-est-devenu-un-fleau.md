---
title: Pourquoi Bootstrap est devenu un fléau
date: '2012-07-06'
description: J'expose ma vision sur le framework css bootstrap par twitter, et comment il est devenu un fléau pour le web design.
categories: [code]
tags: [css, framework, twitter bootstrap, twitter, bootstrap]

layout: post
---

J'exprime dans cet article une opinion strictement personnelle qui peut être partagée ou non par chacun, merci de repecter ce fait si vous choississez de commenter.

### Boostrap un fléau ?

Tout d'abord, et dans un soucis de clarté, il faut bien comprendre que je considère Bootstrap comme un outil très pratique qui fait bien le travail pour lequel il à été conçu.  
Je ne reproche pas ici à Bootstrap ces qualités, le problème que je relate ici est lié à l'utilisateur.

#### Le layout

Depuis l'arrivée de Bootstrap, son utilisation n'a fait que croître et de plus en plus de sites en production l'utilisent **saveur nature**.  
De fait, tous ces sites ont ainsi la même apparence (au détail près de la mise en page) et réutilisent très souvent l'un des layouts proposées par défaut.  
Un détail étrange de la documentation me donne l'impression que Bootstrap n'est pas recommandé pour une utilisation *hors pistes*. C'est la raison pour laquelle je préfère les autres frameworks, et peut-être l'une des raison de la réutilisation massive du layout.

#### Les styles

Le web se retrouve en état de surpopulation de clones Bootstrap auxquels aucun effort particulier de style n'a été apporté.  
Twitter à tenté d'apporter une solution avec le passage à Less, mais ce n'est pas suffisant sans outil adapté à la personnalisation via les variables fournies.

**Nota**: il existe des outils qui ont étés conçus par la communauté mais il y a un problème récurrent d'ergonomie. *Une telle quantité de colorpickers n'est pas ergonomique.*

#### La communication

C'est là le point essentiel de ma réflexion, il manque un aspect que je juge capital dans la documentation de Bootstrap : 

> Bootstrap à originellement été conçus pour faciliter le prototypage d'un site web, afin d'avoir un aperçu de qualité du produit fini.  
> Il reste toutefois possible d'utiliser Bootstrap pour la création d'un produit fini, mais il faut y apporter des efforts de personnalisation des styles selon chaque cas.

### Comment peut-on y remédier ?

1. La solution à troll : il faut tuer Bootstrap
2. Apporter des précisions sur le bon usage de Bootstrap dans sa documentation (un guide pas à pas sur la personnalisation peut apporter une grande aide)
3. Faire évoluer Bootstrap (ceci fera l'objet d'un prochain article)

**Nota final**: Bootstrap reste à mes yeux un outil pratique pour un prototypage ou pour la rédaction d'une documentation (ou autre outil interne au développement en cours) .