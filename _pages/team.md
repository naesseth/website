---
layout: page
title: Team
permalink: /team/
description: 
nav: true
display_categories: [Postdocs, PhD Students, Alumni]
---

<!-- pages/team.md -->
<div class="projects">
<!-- Display categorized people -->
{%- for category in page.display_categories -%}

{% if category == "Alumni" %} 
<h2 class="category">{{ category }}</h2>
{% endif %} 

{%- assign categorized_people = site.people | where: "category", category -%}
{%- assign ordered_people = categorized_people | group_by: "order" -%}
{%- assign ordered_people = ordered_people | sort: "name" -%}

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

---

### Interested in Joining?

I am currently recruiting a postdoc to join the team to work on generative AI and/or uncertainty quantification. Apply [here](https://vacatures.uva.nl/UvA/job/Postdoctoral-Researcher-in-Machine-Learning/784737802/), I will be reviewing applications on a rolling basis till the position is filled.

If you are a MSc student at UvA and interested in collaborating on a thesis project, contact me via [email](mailto:c.a.naesseth@uva.nl). Indicate which areas you are interested in and attach a CV, including a complete record of your courses and grades.