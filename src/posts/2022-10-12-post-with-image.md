---
title: 'Post with an image '
description: "Eleventy's own build-time image transformations. Find more info on11ty.dev/docs/plugins/image/ and edit settings in config-folder."
date: 2022-10-12
---

This starter uses Eleventy's build-time image transformations. Find more info on https://www.11ty.dev/docs/plugins/image/ and edit settings in `config/shortcodes/imagePlaceholder`.

Syntax:

{% raw %}

```
{% imagePlaceholder "path to image", "alt text", "caption - optional" %}
```

{% endraw %}

## Image with caption

{% imagePlaceholder "./src/assets/images/opengraph-default.jpg", "Alt... The preview image for social media", "Caption.. An interesting caption." %}


{% imagePlaceholder "./src/assets/images/Real_Ant.jpg", "Alt... An ant won a Nikon photography contest", "Caption.. A winning ant." %}

{% imagePlaceholder "./src/assets/images/TimeTravel-Science.jpg", "Some time travel advice", "Don't forget your cheat sheet when time traveling." %}


{% imagePlaceholder "./src/assets/images/train-snow.jpg", "A beautiful shot of a train in the Winter", "Nature and modern man's train." %}
