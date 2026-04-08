---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---





I am a PhD researcher within the [Augmented Instruments Lab](http://instrumentslab.org) at the [Dyson School of Design Engineering](https://www.imperial.ac.uk/design-engineering/), Imperial College London.

My research focuses on tactile interaction with digital musical instruments. Specifically, I am looking at how bidirectionality between digital and physical domains can be achieved using technology, and how this may then affect instrument design and interaction with hybrid instruments. This tends to involve haptic feedback and embedded audio systems, along with user studies and more creative work.

Keep in Touch
======

To stay up to date with my research and upcoming conferences/events that I'll be attending, follow me on [BlueSky](https://bsky.app/profile/mdavison.bsky.social) or [Mastodon](https://mastodon.social/@mattdavison) where I try to post on a vaguely regular basis.

Latest Posts
======
{% include base_path %}
{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}