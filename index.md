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
    
1. [Spontaneous Synchronization in Cellular Circadian Clocks](assets/pdf/Dynamics_of_Axially_Coupled_Rotor_Pair.pdf)
2. [Adverserial Image Recognition.pdf](assets/pdf/Adverserial Image Recognition.pdf)
3. 
4. 
5. 
  </div>

  <!-- Portfolio Section -->
  <div id="portfolio">
    <h1>Portfolio</h1>
    {% for item in site.portfolio %}
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