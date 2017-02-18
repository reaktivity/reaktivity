This is the home page

<!-- This includes the entire blog post for all posts with a category of "home". -->
{% assign sorted_pages = (site.posts | sort: 'date') %}
{% for post in sorted_pages reversed %}
{% if post.categories contains 'home' %}
  {{ post.content }}
{% endif %}
{% endfor %}

<!-- This includes just the excerpt for all posts with a category of "home", and links to the post. -->
<!-- Note that the URL is using HTML in this markdown file. Therefore this loop and "logic" should -->
<!-- really be done in a layout HTML file. -->
{% assign sorted_pages = (site.posts | sort: 'date') %}
{% for post in sorted_pages reversed %}
{% if post.categories contains 'home' %}
  {{ post.excerpt }}
  <a href="{{ post.url }}">Read more...</a>
{% endif %}
{% endfor %}

