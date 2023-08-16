---
layout: default
---

<!-- About Me Section -->
<div class="container">
  <div id="about">
    <h1>About Me</h1>
    {% include about.md %}
  </div>
  
  <br/>
  <div id="blog">
    <h1>Blogs</h1>
    For my <b>CS, Math</b>, and <b>Physics</b> blogs and random inspirations, you can find them at <a href='https://www.cloudnest.org/blog/' style='color:#123ac4'>cloudnest.org</a>. 
  </div>

  <br/>
  <!-- Papers Section -->
  <div id="papers">
    <h1>Papers</h1>
  <ul>
    <li><a href="assets/papers/Spontaneous_Synchronization_in_Cellular_Circadian_Clocks.pdf">Spontaneous Synchronization in Cellular Circadian Clocks</a></li>
    <li><a href="assets/papers/Adversarial_Image_Recognition.pdf">Adversarial Image Recognition</a></li>
    <li><a href="assets/papers/A_general_graph_based_method_for_resource_optimization.pdf">A General Graph Based Method for Resource Optimization</a></li>
    <li><a href="assets/papers/Dynamics_of_Axially_Coupled_Rotor_Pair.pdf">Dynamics of Axially Coupled Rotor Pairs</a></li>
    <li><a href="assets/papers/ML_Music_Recognition.pdf">Music Genre Classification with CNN</a></li>
  </ul>
  </div>

  <!-- Portfolio Section -->
  <div id="portfolio">
    <h1>Portfolio</h1>
      {% assign sorted_portfolio = site.portfolio | sort:"order" %}
      {% for item in sorted_portfolio %}
    <div class="portfolio-item">
        <h2><a href="{{ site.baseurl }}{{ item.redirect }}">{{ item.title }}</a></h2>
        <img src="{{ item.image }}" alt="{{ item.title }}">
        <p>{{ item.content | strip_html | truncate:160 }}</p>
    </div>
    {% endfor %}
  </div>

  <!-- Contact Information Section -->
  <div id="contact">
    <h1>Contact Me</h1>
    {% include contact.md %}
  </div>
</div>