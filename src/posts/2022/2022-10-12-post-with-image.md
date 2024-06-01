---
title: 'Post with an image '
description: "Eleventy's own build-time image transformations. Find more info on11ty.dev/docs/plugins/image/ and edit settings in config-folder."
date: 2022-10-12
tags: ['image', 'feature']
image: './src/assets/images/gallery/asturias-1.jpg'
alt: 'A picturesque valley showcasing majestic mountains and lush forests, creating a serene and captivating landscape'
credit: Lene took this photo.
---

This starter uses Eleventy's build-time image transformations.

Find more info on https://www.11ty.dev/docs/plugins/image/ and edit settings in `config/shortcodes/image`.

Some sample image tests.
<img src="https://res.cloudinary.com/paulapplegate-com/image/upload/c_limit,w_auto/dpr_auto,f_auto,q_auto/hillshire-farm-2_fx2mno.jpg" >

<img data-src="https://res.cloudinary.com/paulapplegate-com/image/upload/c_limit,w_auto/dpr_auto,f_auto,q_auto/Beautiful_Italy.jpg" class="cld-responsive">

![Italy is beautiful](https://res.cloudinary.com/paulapplegate-com/image/upload/c_limit/dpr_auto/f_auto,q_auto/w_auto:breakpoints_200_1920_30_15/israel-ferrera-ewxZ27OmFrs-unsplash_xiwjm2.jpg)


![An image test](https://res.cloudinary.com/paulapplegate-com/image/upload/c_limit/dpr_auto/f_auto,q_auto/w_auto:breakpoints_200_1920_30_15/claudio-schwarz-b_qczKSP_X4-unsplash_hozv15.jpg)

![An image test](https://res.cloudinary.com/paulapplegate-com/image/upload/c_limit/dpr_auto/f_auto,q_auto/w_auto:breakpoints_200_1920_30_15/hillshire-farm-2_fx2mno.jpg)

![landscape](https://applegate-paul.mo.cloudinary.net/zoom/142056.jpg)


![landscape](https://applegate-paul.mo.cloudinary.net/zoom/303312.jpg)
![landscape](https://applegate-paul.mo.cloudinary.net/zoom/465411.jpg)
![landscape](https://applegate-paul.mo.cloudinary.net/zoom/644220.jpg)
![landscape](https://applegate-paul.mo.cloudinary.net/zoom/675381.jpg)
![landscape](https://applegate-paul.mo.cloudinary.net/zoom/763762.jpg)
![landscape](https://applegate-paul.mo.cloudinary.net/zoom/764487.jpg)
![landscape](https://applegate-paul.mo.cloudinary.net/zoom/979439.jpg)

## Syntax

In the most basic version it contains the path to the image, alt text (can be an empty string if the image is decorative), and may hold a caption.

{% raw %}

```jinja2
{% image "path to image", "alt text", "caption text" %}
```

{% endraw %}

It defaults to `loading = 'lazy'`, the picture element gets its set of images from `widths = [440, 880, 1024, 1360]` and compares to a condition of `90vw`.

If you want to be very specific, you can pass in manually all the conditions, add `null` to skip.

The class names are passed in the outer container, the `<picture>` or `<figure>` element (`<figure>` is added if you set a caption).

{% raw %}

```jinja2
{% image "path to image", "alt text", "caption text", "eager", "class names", "(min-width:30em) 50vw, 100vw", [200, 400] %}
{% image "path to image", "alt text", null, "eager" %}
```

{% endraw %}

### Example image with a caption

{% raw %}

```jinja2
{% image "./src/assets/images/gallery/asturias-2.jpg", "Close-up of a delicate white flower with a yellow center, surrounded by green leaves", "Jasmine nightshades blooming in July" %}
```

{% endraw %}

{% image "./src/assets/images/gallery/asturias-2.jpg", "Close-up of a delicate white flower with a yellow center, surrounded by green leaves", "Jasmine nightshades blooming in July" %}

### Example image with all the arguments

{% raw %}

```jinja2
{% image "./src/assets/images/gallery/asturias-3.jpg", "A traditional Asturian village with it's raised granaries, surrounded by lush green hills and mountains", null, "lazy", "class-that-does-nothing", "(min-width:30em) 50vw, 100vw", [200, 400] %}
```

{% endraw %}

{% image "./src/assets/images/gallery/asturias-3.jpg", "A traditional Asturian village with it's raised granaries, surrounded by lush green hills and mountains", null, "lazy", "class-that-does-nothing", "(min-width:30em) 50vw, 100vw", [200, 400] %}

## Markdown sytnax

Thanks to the [markdown-it-eleventy-img](https://github.com/solution-loisir/markdown-it-eleventy-img) package markdown also has it own image syntax. `src` is already prepended here, see `config/plugins/markdown.js`.

### Picture element

```markdown
![alt text](/path/to/image)
![Close-up with unfocused background of a vibrant large blue butterfly gracefully perched on a delicate flower amidst lush green gras](/assets/images/gallery/asturias-4.jpg)
```

![Close-up with unfocused background of a vibrant large blue butterfly gracefully perched on a delicate flower amidst lush green gras](/assets/images/gallery/asturias-4.jpg)

### Figure element with caption

```markdown
![alt text](/path/to/image 'caption text')
![A picturesque valley showcasing majestic mountains and lush forests, creating a serene and captivating landscape](/assets/images/gallery/asturias-1.jpg 'Inside the Somiedo Natural Park, Asturias')
```

![A picturesque valley showcasing majestic mountains and lush forests, creating a serene and captivating landscape](/assets/images/gallery/asturias-1.jpg 'Inside the Somiedo Natural Park, Asturias')
