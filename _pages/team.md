---
layout: page
title: Team
permalink: /team/
description: 
nav: true
display_categories: [PI, Postdocs, PhD Students]
---

<!-- pages/team.md -->
<div class="projects">
<!-- Display categorized people -->
{%- for category in page.display_categories -%}


{%- assign categorized_people = site.people | where: "category", category -%}
{%- assign ordered_people = categorized_people | group_by: "order" -%}

<div class="grid">
{%- for o in ordered_people -%}
{%- assign sorted_people = o.items | sort_natural: "last_name" -%}  
<!-- Generate cards for each person -->
  {%- for person in sorted_people -%}
    {% include person_card.html %}
  {%- endfor %}
{%- endfor -%}
</div>
{%- endfor -%}
</div>