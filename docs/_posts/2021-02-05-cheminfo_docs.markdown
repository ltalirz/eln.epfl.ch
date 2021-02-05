---
layout: post
title: "Where can i find help in the ELN and how can I improve it?"
date: 2021-02-04 14:11
categories: [tutorial]
---

In this blog post we will discuss where you can find help in the ELN and how you can help use improving the documentation.

# How does the documentation in the ELN work?

If you have been using the ELN you might have been noticing that there is a question mark icon in the top left corner of some pages in the ELN. If you click on it, it will open a popup with help relevant to the view you're currently looking at.

All of this is built using [GitBook](https://github.com/GitbookIO/gitbook) which allows to convert [markdown files](https://www.markdownguide.org/) into something that looks like an online book.
The core of the documentation is in the `src/book` folder of the [c6h6-documentation repository](https://github.com/cheminfo/c6h6-documentation/tree/master/src/book) where you can find subfolders for different categories.

## Mapping views to documentation pages

You might now ask yourself how the mapping between the view in the ELN and the page in the documentation works. This is set up in `index.yml` files like [this here for the PXRD documentation](https://github.com/cheminfo/c6h6-documentation/blob/master/src/book/spectra/pxrd/index.yml). The file contains one key called `uuid` which is the [uuid](https://en.wikipedia.org/wiki/Universally_unique_identifier) of the view. If we analyze the requests the ELN makes using the [network tab in the developer tools](https://developers.google.com/web/tools/chrome-devtools/network/) we find that this is indeed the UUID of the view, and this is also what we find in the [visualizer helper library](https://github.com/cheminfo-js/visualizer-helper/blob/150b2bfea7a0d50778a85b53d2fad51939bde9d8/util/tips.js#L13-L26): for a given view we get the UUID `info._id` and then can use this to find the correct `yml` file that configures the sections of the documentation.

```javascript
async function showTips(info) {
  if (!info) info = await getViewInfo();
  if (!info._id) return;

  //  info._id='15c9a2dcd55c963fdedf2c18a1471b03';
  //  info.rev=90;
  // retrieve tips toc
  await fetch(`${tipsURL + info._id}/index.yml`)
    .then(async (response) => {
      let text = await response.text();
      processTipsToc(text, info);
    })
    .catch();
}
```

And the [`processTipsToc`](https://github.com/cheminfo-js/visualizer-helper/blob/150b2bfea7a0d50778a85b53d2fad51939bde9d8/util/tips.js#L49-L61) function is then the one that actually pops up the documentation.

# How can I help improving the documentation

Since the documentation lives in simple markdown files on GitHub you can contribute by simply editing the markdown files. The process is, as with all contributions to projects on GitHub, fork, edit, pull request.

## Where do I make the changes? 

<hr>

<div class="post-categories">
  {% if post %}
    {% assign categories = post.categories %}
  {% else %}
    {% assign categories = page.categories %}
  {% endif %}
  {% for category in categories %}
  <a href="{{site.baseurl}}/categories/#{{category|slugize}}">{{category}}</a>
  {% unless forloop.last %}&nbsp;{% endunless %}
  {% endfor %}
</div>
