---
title: Troubleshooting
---

If you ever run into problems installing or using Jekyll, here are a few tips
that might be of help. If the problem you’re experiencing isn’t covered below,
**please [check out our other help resources](/help/)** as well.

- [Base-URL Problems](#base-url-problems)
- [Configuration problems](#configuration-problems)
- [Markup Problems](#markup-problems)


## Base-URL Problems

If you are using base-url option like:

{% highlight bash %}
jekyll serve --baseurl '/blog'
{% endhighlight %}

… then make sure that you access the site at:

{% highlight bash %}
http://localhost:4000/blog/index.html
{% endhighlight %}

It won’t work to just access:

{% highlight bash %}
http://localhost:4000/blog
{% endhighlight %}

## Configuration problems

The order of precedence for conflicting [configuration settings](../configuration/)
is as follows:

1. Command-line flags
2. Configuration file settings
3. Defaults

That is: defaults are overridden by options specified in `_config.yml`,
and flags specified at the command-line will override all other settings
specified elsewhere.

## Markup Problems

The various markup engines that Jekyll uses may have some issues. This
page will document them to help others who may run into the same
problems.

### Liquid

The latest version, version 2.0, seems to break the use of `{{ "{{" }}` in
templates. Unlike previous versions, using `{{ "{{" }}` in 2.0 triggers the
following error:

{% highlight bash %}
'{{ "{{" }}' was not properly terminated with regexp: /\}\}/  (Liquid::SyntaxError)
{% endhighlight %}

### Excerpts

Since v1.0.0, Jekyll has had automatically-generated post excerpts. Since
v1.1.0, Jekyll also passes these excerpts through Liquid, which can cause
strange errors where references don't exist or a tag hasn't been closed. If you
run into these errors, try setting `excerpt_separator: ""` in your
`_config.yml`, or set it to some nonsense string.

<div class="note">
  <h5>Please report issues you encounter!</h5>
  <p>
  If you come across a bug, please <a href="{{ site.help_url }}/issues/new">create an issue</a>
  on GitHub describing the problem and any work-arounds you find so we can
  document it here for others.
  </p>
</div>
