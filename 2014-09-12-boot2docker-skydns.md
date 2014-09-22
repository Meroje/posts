---
title: Boot2docker OSX et networking
categories: [docker]
tags: [docker, devops]
comments: true
share: true

description: Avec boot2docker c'est génial on peut récupérer tous les avantages de docker sur osx. Tous ? On va voir.

link: http://www.asbjornenge.com/wwc/vagrant_skydocking.html

image:
  feature: docker-large_h-dark-trans.png
  credit: Docker
  creditlink: https://docker.com
layout: post
---

L'article lié explique déjà très bien les concepts, mais aujourd'hui [boot2docker](http://boot2docker.io/) est le moyen préféré pour faire tourner nos containers en local, la route change donc de la façon suivante:

``` sh
sudo route -n add -net 172.17.0.0  192.168.59.103

# On teste pour être bien sur
ping `docker inspect -format='\{\{.NetworkSettings.IPAddress\}\}' skydns`
```

L'auteur montre ensuite comment utiliser skydns comme notre résolveur principal, ce serveur tourne dans une vm et il est peu probable qu'elle tourne en permanence (surtout pour les macbooks), on peut utiliser dnsmasq

```
# /etc/dnsmasq.conf
server=/docker/172.17.42.1
```

ou simplement mettre à profit les méchanismes d'osx:

```
# /etc/resolver/docker
nameserver 172.17.42.1
domain docker
```
