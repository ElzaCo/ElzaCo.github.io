---
layout: null
title: Elza Co - Projects
description: Current and past projects at Elza Co.
banner-image: /assets/images/maps.jpg
permalink: /projects/
sitemap:
    priority: 1.0
    lastmod: 2018-11-15
    changefreq: weekly
---
<html>
	<head>
		{% include head.html %}
	</head>
	<body>
		<!-- Header -->
		<header>
			<h1>{{site.title}}</h1>
			<nav>
				{% include nav.html %} 
			</nav>
		</header>

		<!-- Banner -->
		<section class="banner align-center">
			<h1>Projects</h1>
			<h2>Current and past projects at Elza Co.</h2>
		</section>

		<!-- Projects -->
		<section class="container 75% col-2 projects">
			{% assign pages = site.projects | sort:"url"  %}
			{% for page in pages %}
				<a class="box img-preview" style="background-image:url('{{ page.image }}');" href="{{ site.baseurl }}{{ page.url }}">
				</a>
				<div class="box">
					<h3>{{ page.title }}</h3>
					<p>{{ page.description }}</p>
					<a class="goto" href="{{ site.baseurl }}{{ page.url }}">go to project</a>
				</div>
			{% endfor %}
			
		</section>

		<!-- Contact -->
		<section class="contact">
			<div class="form box">
				<form method="POST" action="https://formspree.io/{{site.email}}">
					<input type="hidden" name="_next" value="{{site.url}}{{site.formspree_thankyou_page}}" />
					<div class="field">
						<label for="name">Name</label>
						<input type="text" name="name" id="name" />
					</div>
					<div class="field">
						<label for="email">Email</label>
						<input type="text" name="email" id="email" />
					</div>
					<div class="field">
						<label for="message">Message</label>
						<textarea name="message" id="message" rows="3"></textarea>
					</div>
					<div class="field">
						<input type="submit" value="Send Message" />
					</div>
				</form>
			</div>
			<div class="location box">
				<h3>Location</h3>
				<p>{{site.location}}</p>
			</div>
			<div class="phone box">
				<h3>Phone</h3>
				<p><a href="tel:{{site.phone}}">{{site.phone}}</a></p>
			</div>
			<div class="email box">
				<h3>Email</h3>
				<p><a href="mailto:{{site.email}}">{{site.email}}</a></p>
			</div>
			<div class="other box">
				<h3>Github</h3>
				<p><a href="https://github.com/{{site.github}}">github</a></p>
			</div>
		</section>
	</body>
</html>