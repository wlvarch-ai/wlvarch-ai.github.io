---
title: Tools
permalink: /tools/
lead: A curated register of tools members have used, with an honest verdict and a review date.
---

This register is not a directory. It covers only tools that a member has used on real work. Terms, prices and capabilities change quickly, so check the review date before relying on an entry. Entries older than six months should be treated as out of date.

{% if site.data.tools and site.data.tools.size > 0 %}
| Tool | Used for | Cost | Data terms | Verdict | Reviewed |
| --- | --- | --- | --- | --- | --- |
{% for t in site.data.tools %}| [{{ t.name }}]({{ t.url }}) | {{ t.used_for }} | {{ t.cost }} | {{ t.data_terms }} | {{ t.verdict }} | {{ t.reviewed | date: "%b %Y" }} ({{ t.reviewer }}) |
{% endfor %}
{% else %}
<p class="empty">No tools reviewed yet.</p>
{% endif %}

To add or update a tool, edit `_data/tools.yml`. The [contributor guide]({{ '/contribute/' | relative_url }}#adding-a-tool) explains how.
