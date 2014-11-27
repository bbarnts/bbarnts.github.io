---
layout: post
title: I’m not a blogger, but I keep making blogs
---

Welcome to my third ever blog post on the second blog site I’ve created.
The obvious truth is that I am not a blogger, I’m just a guy who likes playing with new
tools. I recently read something about Jekyll and wanted to give it a try.
The page you’re looking at is the result of my first attempt. It turns out
I think Jekyll is pretty cool and I think it could easily become one of my _go to_ tools
for creating simple sites like this one.


So what’s so great about Jekyll? Plain text.
--------------------------------------------
I love plain text. Just ask my coworkers. I write everything in Vim and fill
our project wikis with ASCII flowcharts. Even better than regular plain text
is plain text with [Markdown](http://daringfireball.net/projects/markdown/syntax). 
Markdown is a standardized way (although there is no official standard)
of adding structural elements like heading levels, emphasis, and tables to your plain text document. 
Markdown conventions are very readable in plain text form but can also be easily translated
to HTML (with tools like Jekyll) where we can control the styling with good ol’ CSS. 

For example, note how readable this table is in Markdown:



    | Movie               | Release year    |
    | ------------------- | --------------: |
    | Star Wars           | 1977            |
    | Empire Strike Back  | 1980            |


As opposed to the HTML equivalent:

{% highlight html %}
<table>
<tbody>
<tr>
<th>Movie</th>
<th>Release year</th>
</tr>
<tr>
<td>Star Wars</td>
<td>1970</td>
</tr>
<tr>
<td>Empire Strike Back</td>
<td>1980</td>
</tr>
</tbody>
</table>
{% endhighlight %}

With Jekyll, you can write the content of your site in Markdown. I created this post,
for example, by just adding a text file to my ```_posts``` directory. Jekyll handles 
translating it to HTML, applying the layout I’ve defined for posts (adding header, footers, etc).
This leads me to another thing I like about Jekyll.

It’s just HTML
--------------
The website that Jeykll renders from the Markdown files is a self-contained collection of static
HTML files. No runtime environments, frameworks, or databases are required. This means
you can pretty much host your site from anywhere that can serve files. You could even
zip it up and email it to someone. Using Github Pages, you can even host your site for free.
That’s what I’m doing for this site.


One of the most obvious drawbacks of Jekyll is that there is no built-in commenting
feature like you see on every Wordpress blog. If you have any thoughts to share, feel
free to shoot me a message via email or Twitter.

