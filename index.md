---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
---
{% assign ordered_blogs = site.blogposts | sort: "display-order" %}

<br /> {% for blog in ordered_blogs %}

{% if forloop.last == true %}


<div class="container blog">
	<div>
		<a href="{{blog.url}}">
			<h3>
			 	{{blog.title}}
			</h3>
		</a>

		<p>
			{{blog.excerpt}}
		</p>
		<a style="float: right" href="{{blog.url}}">Keep Reading >></a>
	</div>
</div>
{% endif %}

{% endfor %}

{% assign ordered_games = site.games | sort: "display-order" %}

<br /> {% for game in ordered_games %}

{% if forloop.last == true %}
<div class="container" onmouseup="openlink(event, '{{game.url}}')">
	<div>
		<h3>
			 {{game.title}}
		</h3>
		<p>
			{{game.desc}}
		</p>
	</div>
	<img src="{{site.url}}/assets/placeholder.png" />
</div>
{% endif %}

{% endfor %}
<br />

<script>
	function openlink(e, link) {
		switch (e.button) {
			case 0:
			case 1:
				document.location.href = link;
				break;
		}
	}
</script>
