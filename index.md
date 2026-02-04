---
layout: default
title: Home
---

<section class="hero">
  <div class="hero-card">
    <h1>{{ site.profile.name }}</h1>
    <p class="lead">
      {{ site.profile.title }} at {{ site.profile.affiliation }}. I build practical,
      human-centered AI systems with a focus on reliability, interpretability, and
      real-world deployment.
    </p>
    <div class="callout">
      Open to research collaborations, speaking invitations, and industry partnerships.
      Reach me at <a href="mailto:{{ site.profile.email }}">{{ site.profile.email }}</a>.
    </div>
  </div>
  <aside class="hero-card profile-card">
    <img src="{{ site.profile.headshot | relative_url }}" alt="Headshot">
    <div class="profile-meta">
      <div><strong>Location:</strong> {{ site.profile.location }}</div>
      <div><strong>Website:</strong> <a href="{{ site.profile.website }}">{{ site.profile.website }}</a></div>
      <div><strong>GitHub:</strong> <a href="{{ site.profile.github }}">{{ site.profile.github }}</a></div>
      <div><strong>Scholar:</strong> <a href="{{ site.profile.scholar }}">{{ site.profile.scholar }}</a></div>
    </div>
    <div class="tag-list">
      <span class="tag">LLMs</span>
      <span class="tag">HCI</span>
      <span class="tag">ML Systems</span>
      <span class="tag">Retrieval</span>
    </div>
  </aside>
</section>

<section class="section">
  <div class="section-title">
    <h2>Selected Papers</h2>
    <a href="{{ '/papers/' | relative_url }}">View all</a>
  </div>
  <ul class="list-plain">
    {% for pub in site.data.publications limit:2 %}
    <li>
      <strong>{{ pub.title }}</strong><br>
      {{ pub.authors }}<br>
      <span class="card-meta">{{ pub.venue }} ({{ pub.year }})</span>
    </li>
    {% endfor %}
  </ul>
</section>

<section class="section">
  <div class="section-title">
    <h2>Featured Projects</h2>
    <a href="{{ '/projects/' | relative_url }}">View all</a>
  </div>
  <div class="card-grid">
    {% for project in site.data.projects limit:2 %}
    <div class="card">
      <h3>{{ project.name }}</h3>
      <div class="card-meta">{{ project.role }}</div>
      <p>{{ project.description }}</p>
      <div class="tag-list">
        {% for tech in project.tech %}
        <span class="tag">{{ tech }}</span>
        {% endfor %}
      </div>
    </div>
    {% endfor %}
  </div>
</section>

<section class="section">
  <div class="section-title">
    <h2>Recent Experience</h2>
    <a href="{{ '/experience/' | relative_url }}">View all</a>
  </div>
  <div class="card-grid">
    {% for role in site.data.experience limit:2 %}
    <div class="card">
      <h3>{{ role.role }}</h3>
      <div class="card-meta">{{ role.org }} | {{ role.start }} - {{ role.end }}</div>
      <p>{{ role.summary }}</p>
    </div>
    {% endfor %}
  </div>
</section>
