---
layout: default
---

<!-- About Me Section -->
<div class="container">
  <section id="about">
    <h1>About Me</h1>
    {% include about.md %}
  </section>


  <!-- Papers Section -->
  <section id="papers">
    <h1>Papers</h1>
    [download pdf](https://belovanna.github.io/assets/mydoc.pdf)
  </section>

  <!-- Portfolio Section -->
  <section id="portfolio">
    <h1>Portfolio</h1>
    {% for item in site.portfolio %}
    <div class="portfolio-item">
        <h2><a href="{{ item.url }}">{{ item.title }}</a></h2>
        <img src="{{ item.image }}" alt="{{ item.title }}">
        <p>{{ item.content | strip_html | truncate:160 }}</p>
    </div>
    {% endfor %}
  </section>

  <!-- Blog Section -->
  <section id="blog">
    <h1>Blog</h1>
    {% for post in site.posts limit:5 %}
      <div class="blog-post">
        <h2>{{ post.title }}</h2>
        <p>{{ post.excerpt }}</p>
        <a href="{{ post.url }}">Read More</a>
      </div>
    {% endfor %}
  </section>

  <!-- Contact Information Section -->
  <section id="contact">
    <h1>Contact Me</h1>
    {% include contact.md %}
  </section>
</div>