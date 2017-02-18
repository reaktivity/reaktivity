{% assign sorted_pages = (site.posts | sort: 'date') %}
{% for post in sorted_pages reversed %}
{% if post.categories contains 'home' %}
  {{ post.excerpt }}
  [Continue reading...]({{ post.url }})
{% endif %}
{% endfor %}
