---
layout: page
title: Games
permalink: /games/
---

{% for game in site.games %}
<a href="{{game.url}}">{{game.title}}</a>

{% endfor %}
