---
layout: page
title: "Group"
subtitle: "People in the lab"
---

{% assign pi = site.data.people.pi %}

<div class="advisor-row card-lite">
  <h2 class="group-section-heading mb-3">Faculty</h2>

  <div class="advisor-grid">
    {% if pi.photo and pi.photo != "" %}
      <img src="{{ site.baseurl }}/{{ pi.photo }}" alt="{{ pi.name }}" class="advisor-photo">
    {% else %}
      <img src="https://via.placeholder.com/140" alt="{{ pi.name }}" class="advisor-photo">
    {% endif %}

    <div>
      <div class="advisor-name">
          {% if pi.website and pi.website != "" %}
            <a href="{{ pi.website }}">{{ pi.name }}</a>
          {% else %}
            {{ pi.name }}
          {% endif %}
      </div>
      <div class="text-muted">{{ pi.title }}</div>
      <div class="text-muted mb-3">{{ pi.affiliation }}</div>

      <div class="d-flex flex-wrap gap-2">
        {% for l in pi.links %}
          <a class="badge-lite text-decoration-none" href="{{ l.url }}">{{ l.label }}</a>
        {% endfor %}
      </div>
    </div>
  </div>
</div>


{% if site.data.people.phd_students and site.data.people.phd_students.size > 0 %}
<h2 class="group-section-heading">PhD Students</h2>
<div class="people-grid">
{% for p in site.data.people.phd_students %}
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
{% endif %}

{% if site.data.people.masters_undergrad_students and site.data.people.masters_undergrad_students.size > 0 %}
<h2 class="group-section-heading">Masters and Undergrad Students</h2>
<div class="people-grid">
{% for p in site.data.people.masters_undergrad_students %}
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
{% endif %}


<h2 class="group-section-heading">Alumni</h2>

{% assign alumni_degrees = "PhD|MS|BS" | split: "|" %}
{% for degree in alumni_degrees %}
{% assign alumni_group = site.data.people.alumni | where: "degree", degree %}
{% if alumni_group.size > 0 %}
<h3 class="group-subsection-heading">{{ degree }}</h3>
<div class="alumni-grid">
  {% for a in alumni_group %}
    <div class="alumni-card">
      {% if a.photo and a.photo != "" %}
        <img src="{{ site.baseurl }}/{{ a.photo }}" alt="{{ a.name }}" class="alumni-photo">
      {% else %}
        <img src="https://via.placeholder.com/120" alt="{{ a.name }}" class="alumni-photo">
      {% endif %}

      <div class="alumni-name">
        {% if a.website and a.website != "" %}
          <a href="{{ a.website }}">{{ a.name }}</a>
        {% else %}
          {{ a.name }}
        {% endif %}
      </div>

      <div class="alumni-role">{{ a.role }}</div>
    </div>
  {% endfor %}
</div>
{% endif %}
{% endfor %}
