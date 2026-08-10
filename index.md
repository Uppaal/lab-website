---
layout: default
title: ""
---

<div class="hero">
  <div>
    <h1 class="mb-2">{{ site.title }}</h1>
    <p class="lead mb-3">{{ site.description }}</p>

    <div class="card-lite">
      <h5 class="mb-2">Research themes</h5>
      <ul class="mb-0">
        <li><span class="text-highlight">Multilingual NLP and Cultures:</span> Democratizing inclusive LLMs across languages and cultures while enhancing pluralistic alignment.</li>
        <li><span class="text-highlight">Efficient Multimodal LLMs:</span> Developing efficient multimodal LLMs for high-stakes applications in education and healthcare.</li>
        <li><span class="text-highlight">Cognitive Language Agents:</span> Unifying cognitive concepts and languages to enable complex reasoning, planning and human behavior simulation.</li>
        <li><span class="text-highlight">Evaluation and Mechanistic Interpretation:</span> Exploring robust methods for evaluating and interpreting black-box foundation models.</li>
      </ul>
    </div>

  </div>

  <div class="carousel-frame">
    <div id="labCarousel"
       class="carousel slide"
       data-bs-ride="carousel"
       data-bs-interval="3000">

      <div class="carousel-inner">

        {% for slide in site.data.carousel %}
        <div class="carousel-item{% if forloop.first %} active{% endif %}">
          <img
            src="{{ site.baseurl }}/{{ slide.image }}"
            class="d-block w-100 carousel-img"
            alt="{{ slide.alt }}"
          />
          {% if slide.caption %}
          <div class="carousel-caption d-none d-md-block">
            <p class="mb-0">{{ slide.caption }}</p>
          </div>
          {% endif %}
        </div>
        {% endfor %}

      </div>

      <button class="carousel-control-prev" type="button" data-bs-target="#labCarousel" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#labCarousel" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </div>
</div>

<section class="sponsors">
  <h5 class="mb-2">Sponsors</h5>
  <p>We are grateful to the following organizations for supporting our research:</p>
  <ul class="mb-0">
    <li>National Science Foundation (CISE/IIS core)</li>
    <li>National Institutes of Health (NLM R01, NIBIB R01)</li>
    <li>Department of Defense</li>
    <li>IARPA (Video LINCS)</li>
    <li>UW ICTR</li>
    <li>Wisconsin Alumni Research Foundation</li>
    <li>American Family Insurance</li>
    <li>Coefficient Giving (previously Open Philanthropy)</li>
    <li>Microsoft</li>
    <li>NVIDIA</li>
    <li>Google</li>
  </ul>
</section>
