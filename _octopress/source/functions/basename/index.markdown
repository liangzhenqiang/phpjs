---
layout: page
title: "JavaScript basename function"
comments: true
sharing: true
footer: true
sidebar: false
alias:
- /functions/view/basename:360
- /functions/view/basename
- /functions/view/360
- /functions/basename:360
- /functions/360
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's basename

{% codeblock filesystem/basename.js lang:js https://raw.github.com/kvz/phpjs/master/functions/filesystem/basename.js raw on github %}
function basename (path, suffix) {
  // http://kevin.vanzonneveld.net
  // +   original by: Kevin van Zonneveld (http://kevin.vanzonneveld.net)
  // +   improved by: Ash Searle (http://hexmen.com/blog/)
  // +   improved by: Lincoln Ramsay
  // +   improved by: djmix
  // *     example 1: basename('/www/site/home.htm', '.htm');
  // *     returns 1: 'home'
  // *     example 2: basename('ecra.php?p=1');
  // *     returns 2: 'ecra.php?p=1'
  var b = path.replace(/^.*[\/\\]/g, '');

  if (typeof(suffix) == 'string' && b.substr(b.length - suffix.length) == suffix) {
    b = b.substr(0, b.length - suffix.length);
  }

  return b;
}
{% endcodeblock %}

 - [view on github](https://github.com/kvz/phpjs/blob/master/functions/filesystem/basename.js)
 - [edit on github](https://github.com/kvz/phpjs/edit/master/functions/filesystem/basename.js)

### Example 1
This code
{% codeblock lang:js example %}
basename('/www/site/home.htm', '.htm');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'home'
{% endcodeblock %}

### Example 2
This code
{% codeblock lang:js example %}
basename('ecra.php?p=1');
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'ecra.php?p=1'
{% endcodeblock %}


### Other PHP functions in the filesystem extension
{% render_partial _includes/custom/filesystem.html %}
## Legacy comments
These were imported from our old site. Please use disqus below for new comments
<div style="overflow-y: scroll; max-height: 500px;">
{% render_partial functions/basename/_comments.html %}
</div>
