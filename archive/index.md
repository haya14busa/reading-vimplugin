---
layout: default
title: 過去の開催 - Vimプラグイン読書会
---

<table>
  <thead>
    <tr>
      <th>No.</th>
      <th>Date</th>
      <th>Plugin</th>
      <th>Lingr Log</th>
    </tr>
  </thead>
  <tbody>
{% for archive in site.data.archives %}
  {% if archive.id < 10 %}
    {% assign htmlname = archive.id | prepend: '00'  %}
  {% elsif archive.id < 100 %}
    {% assign htmlname = archive.id | prepend: '0' %}
  {% else %}
    {% assign htmlname = archive.id %}
  {% endif %}
  <tr>
    <td><a href="{{ htmlname }}.html">第{{ archive.id }}回</a></td>
    <td>{{ archive.date | date: "%Y/%m/%d %a" }}</td>
    <td>
    {% for plugin in archive.plugins %}
    <a href="{{ plugin.url }}/tree/{{ plugin.hash }}">{{ plugin.author }}/{{ plugin.name }}</a><br>
    {% endfor %}
    </td>
    <td><a href="{{ archive.log }}">ログ</a></td>
  </tr>
{% endfor %}
  </tbody>
</table>
