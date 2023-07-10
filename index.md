---
layout: default
---

<!-- About Me Section -->
<div class="container">
  <div id="about">
    <h1>About Me</h1>
    {% include about.md %}
  </div>

  <!-- Papers Section -->
  <div id="papers">
    <h1>Papers</h1>
  <ul>
    <li><a href="assets/papers/Dynamics_of_Axially_Coupled_Rotor_Pair.pdf">Spontaneous Synchronization in Cellular Circadian Clocks</a></li>
    <li><a href="assets/papers/Adverserial_Image_Recognition.pdf">Adverserial Image Recognition.pdf</a></li>
    <!-- add more papers here -->
  </ul>
  </div>

  <!-- Portfolio Section -->
  <div id="portfolio">
    <h1>Portfolio</h1>
      {% assign sorted_portfolio = site.portfolio | sort:"order" %}
      {% for item in sorted_portfolio %}
    <div class="portfolio-item">
        <h2><a href="{{ item.url }}">{{ item.title }}</a></h2>
        <img src="{{ item.image }}" alt="{{ item.title }}">
        <p>{{ item.content | strip_html | truncate:160 }}</p>
    </div>
    {% endfor %}
  </div>

  <!-- Blog Section -->
  <div id="blog">
    <h1>Blog</h1>
    {% for post in site.posts limit:5 %}
      <div class="blog-post">
        <h2>{{ post.title }}</h2>
        <p>{{ post.excerpt }}</p>
        <a href="{{ post.url }}">Read More</a>
      </div>
    {% endfor %}
  </div>

  <!-- Contact Information Section -->
  <div id="contact">
    <h1>Contact Me</h1>
    {% include contact.md %}
  </div>
</div>