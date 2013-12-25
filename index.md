---
layout: default
title: Vimプラグイン読書会
---

## Happy Vimming!

## 過去の開催
- [アーカイブ](./archive)

## 運営
{% for member in site.data.members %}
- {{ member.name }}
  - GitHub : [{{ member.name }}](https://github.com/{{ member.github }})
  - Twitter: [@{{ member.twitter }}](https://twitter.com/{{ member.twitter }})
{% endfor %}
