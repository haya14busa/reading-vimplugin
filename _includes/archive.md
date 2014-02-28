{% for i in site.data.archives %}
  {% if i.id == page.id %}
    {% assign archive = i %}
  {% endif %}
{% endfor %}

### 日時

{{ archive.date | date: "%Y/%m/%d %a" }}

### プラグイン

{% for plugin in archive.plugins %}
- [{{ plugin.author }}/{{ plugin.name }}]({{ plugin.url }}/tree/{{ plugin.hash }}){% if archive.part and forloop.length == 1 %} ({{ archive.part }}) {% endif %}
{% endfor %}

{% if archive.aim %}
### 目的
{{ archive.aim }}
{% endif %}

### 参加者リスト
{{ archive.members.size }} 名。

<ul>
{% for member in archive.members %}
  <li>{{ member }}</li>
{% endfor %}
</ul>

### ログ
<{{ archive.log }}>

{% if archive.links %}
### 関連リンク
{% for link in archive.links %}
  - [{{ link.title }}]({{ link.url }})
{% endfor %}
{% endif %}

{% if archive.other %}
### その他
{{ archive.other }}
{% endif %}
