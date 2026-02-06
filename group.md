---
layout: page
title: "Group"
subtitle: "People in the lab"
---

## Graduate students
<div class="people-grid">
{% for p in site.data.people.students %}
<div class="person">
  {% if p.photo and p.photo != "" %}
    <img src="{{ site.baseurl }}/{{ p.photo }}" alt="{{ p.name }}">
  {% else %}
    <img src="https://via.placeholder.com/92" alt="{{ p.name }}">
  {% endif %}
  <div>
    <div class="fw-semibold">
      {% if p.website and p.website != "" %}
        <a href="{{ p.website }}">{{ p.name }}</a>
      {% else %}
        {{ p.name }}
      {% endif %}
    </div>
    <div class="meta">{{ p.role }}</div>
    {% if p.interests %}
      <div class="mt-1">
        {% for t in p.interests %}
          <span class="badge-lite">{{ t }}</span>
        {% endfor %}
      </div>
    {% endif %}
  </div>
</div>
{% endfor %}
</div>

## Alumni
<ul>
{% for a in site.data.people.alumni %}
  <li>
    {% if a.website and a.website != "" %}<a href="{{ a.website }}">{{ a.name }}</a>{% else %}{{ a.name }}{% endif %}
    — {{ a.role }}
  </li>
{% endfor %}
</ul>
