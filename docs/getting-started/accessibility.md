---
layout: docs
title: Accessibility
description: Learn how Bootstrap supports common web standards for making sites that are accessibile to those using assistive technology.
group: getting-started
---

Bootstrap's aim is to provide an easy-to-use framework of ready-made styles, layout tools and interactive components which  allows developers to create web sites and applications that are not only visually appealing and functionally rich, but also accessible out of the box.

## Contents

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

## Overview and limitations

As Bootstrap is merely designed as a set of building blocks, the overall accessibility of any site created with it will depend in large part on the specific markup, as well as any additional styling and scripting, used by developers. However, provided that these have been implemented correctly, it should be perfectly possible to create web sites and applications with Bootstrap that follow [<abbr title="Web Content Accessibility Guidelines">WCAG</abbr> 2.0](https://www.w3.org/TR/WCAG20/) (A/AA/AAA), [Section 508](https://www.section508.gov/) and similar accessibility standards.

### Structural markup

Bootstrap's styling and layout can be applied to a wide range of markup structures. However, this documentation aims to provide developers with best practice examples which not only demonstrate the use of Bootstrap itself, but also illustrate appropriate semantic markup, including ways in which potential accessibility concerns can be addressed.

### Interactive components

Bootstrap's interactive components – such as modal dialogs, dropdown menus and custom tooltips – are designed to work for touch, mouse and keyboard users. Through the addition of relevant [<abbr title="Web Accessibility Initiative">WAI</abbr> <abbr title="Accessible Rich Internet Applications">ARIA</abbr>](https://www.w3.org/WAI/intro/aria) roles and attributes, these components should also be understandable and operable using assistive technologies (such as screen readers).

Because Bootstrap's components are purposely designed to be fairly generic, authors may – depending on their specific use case – need to include further <abbr title="Accessible Rich Internet Applications">ARIA</abbr> roles and attributes, as well as JavaScript behavior, to more accurately convey the precise nature and functionality of their component. This is usually noted in the documentation.

### Color contrast



## Skip navigation

If your navigation contains many links and comes before the main content in the DOM, add a `Skip to main content` link before the navigation (for a simple explanation, see this [A11Y Project article on skip navigation links](http://a11yproject.com/posts/skip-nav-links/)). Using the `.sr-only` class will visually hide the skip link, and the `.sr-only-focusable` class will ensure that the link becomes visible once focused (for sighted keyboard users).

{% callout danger %}
Due to long-standing shortcomings/bugs in Internet Explorer (see this article on [in-page links and focus order](http://accessibleculture.org/articles/2010/05/in-page-links/)), you will need to make sure that the target of your skip link is at least programmatically focusable by adding `tabindex="-1"`.

In addition, you may want to explicitly suppress a visible focus indication on the target (particularly as Chrome currently also sets focus on elements with `tabindex="-1"` when they are clicked with the mouse) with `#content:focus { outline: none; }`.

Note that this bug will also affect any other in-page links your site may be using, rendering them useless for keyboard users. You may consider adding a similar stop-gap fix to all other named anchors / fragment identifiers that act as link targets.
{% endcallout %}

{% highlight html %}
<body>
  <a href="#content" class="sr-only sr-only-focusable">Skip to main content</a>
  ...
  <div class="container" id="content" tabindex="-1">
    <!-- The main page content -->
  </div>
</body>
{% endhighlight %}

## Additional resources

- ["HTML Codesniffer" bookmarklet for identifying accessibility issues](https://github.com/squizlabs/HTML_CodeSniffer)
- [The A11Y Project](http://a11yproject.com/)
- [MDN accessibility documentation](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
