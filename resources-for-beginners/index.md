---
layout: page
title: Hot Buzzwords & Handy Resources
modified: 2015-09-02T13:23:02.362000-04:00
excerpt: "A simplified list of helpful terms and resources for getting started"
image:
  feature: sample-image-3.jpg
  credit: WeGraphics
  creditlink: http://wegraphics.net/downloads/free-ultimate-blurred-background-pack/
---

{% include _toc.html %}

### Graphics and Fonts

[**WEGraphics**](http://wegraphics.net/tag/free) offers beautiful, free and paid backgrounds, web fonts, and plug-ins for Photoshop and Illustrator.

### Lorem Ipsum

[**Hipster Ipsum**](http://hipsum.co) is a modern twist on the traditional Latin nonsense filler used to set up print or display layouts.

### Peer groups

[**Girl Develop It**](https://www.girldevelopit.com/chapters) Many thanks to GDI Boulder founder [Cara Jo Miller](https://www.linkedin.com/in/carajomiller) for introducing me to GitHub Pages, Markdown, Jekyll, and the Minimal Mistakes theme.

[**Hacker Spaces**](http://www.hackerspaces.org/).  Many thanks to the Boulder Hackerspace, AKA [Solid State Depot](http://boulderhackerspace.com/).

## Development environment

[**Sublime Text 2**](http://www.sublimetext.com/) is a popular code editor with uniquely powerful features such as multiple cursors.  ("Say what?")  It's free to use without limitation and runs on Mac, Windows, or Linux.  Sublime Text 3 is in beta.

Github

## Server technologies

### Preprocessing

**Mark Down** allows for writing copy in plain text with very simple markups for headers, bold, or links.  It requires processing to apply style.  Again, very clean and minimal.

**Jekyll** is a server-side preprocessor which can render .md (markdown) files and style templates into ready-to-serve html files, which are then cached as static files on the server.  Sometimes it takes a few minutes for Jekyll to scan changes to the markdown or style files and render new html.

**Sass**

**YAML** is a way of storing structured data in a plain text file.  It's similar to the notion of using an XML file to hold a data structure, but the syntax is clean and minimal.

## Themes

Many thanks to [Michael Rose](https://mademistakes.com/) for the free use of his [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) Jekyll theme.


**Pro-tip:** Delete the `gh-pages` branch after cloning and start fresh by branching off `master`. There is a bunch of garbage in `gh-pages` used for the theme's demo site that I'm guessing you won't want.
{: .notice}

---

## Scaffolding

How Minimal Mistakes is organized and what the various files are. All posts, layouts, includes, stylesheets, assets, and whatever else is grouped nicely under the root folder. The compiled Jekyll site outputs to `_site/`.

{% highlight text %}
minimal-mistakes/
├── _includes/
|    ├── _author-bio.html        # bio stuff layout. pulls optional owner data from _config.yml
|    ├── _browser-upgrade.html   # prompt to install a modern browser for < IE9
|    ├── _disqus_comments.html   # Disqus comments script
|    ├── _footer.html            # site footer
|    ├── _head.html              # site head
|    ├── _navigation.html        # site top navigation
|    ├── _open-graph.html        # Twitter Cards and Open Graph meta data
|    └── _scripts.html           # site scripts
├── _layouts/
|    ├── home.html               # homepage layout
|    ├── page.html               # page layout
|    ├── post-index.html         # post index layout
|    └── post.html               # single post layout
├── _posts/                      # MarkDown formatted posts
├── _sass/                       # Sass stylesheets
├── _templates/                  # used by Octopress to define YAML variables for new posts/pages
├── about/                       # sample about page
├── assets/
|    ├── css/                    # compiled stylesheets
|    ├── fonts/                  # webfonts
|    ├── js/
|    |   ├── _main.js            # main JavaScript file, plugin settings, etc
|    |   ├── plugins/            # scripts and jQuery plugins to combine with _main.js
|    |   ├── scripts.min.js      # concatenated and minified _main.js + plugin scripts
|    |   └── vendor/             # vendor scripts to leave alone and load as is
|    └── less/
├── images/                      # images for posts and pages
├── 404.md                       # 404 page
├── feed.xml                     # Atom feed template
├── index.md                     # sample homepage. lists 5 latest posts
├── posts/                       # sample post index page. lists all posts in reverse chronology
└── theme-setup/                 # theme setup page. safe to remove
{% endhighlight %}

---

## Site Setup

A quick checklist of the files you'll want to edit to get up and running.

### Site Wide Configuration

`_config.yml` is your friend. Open it up and personalize it. Most variables are self explanatory but here's an explanation of each if needed:


#### url

Used to generate absolute urls in `sitemap.xml`, `feed.xml`, and for generating canonical URLs in `<head>`. When developing locally either comment this out or use something like `http://localhost:4000` so all assets load properly. *Don't include a trailing `/`*.

Examples:

{% highlight yaml %}
url: http://mmistakes.github.io/minimal-mistakes
url: http://localhost:4000
url: //cooldude.github.io
url:
{% endhighlight %}

#### Google Analytics and Webmaster Tools

Google Analytics UA and Webmaster Tool verification tags can be entered under `owner` in `_config.yml`. For more information on obtaining these meta tags check [Google Webmaster Tools](http://support.google.com/webmasters/bin/answer.py?hl=en&answer=35179) and [Bing Webmaster Tools](https://ssl.bing.com/webmaster/configure/verify/ownership) support.

## Adding New Content with Octopress

While completely optional, I've included Octopress and some starter templates to automate the creation of new posts and pages. To take advantage of it start by installing the [Octopress](https://github.com/octopress/octopress) gem if it isn't already.

{% highlight bash %}
$ gem install octopress --pre
{% endhighlight %}

### New Post

Default command

{% highlight bash %}
$ octopress new post "Post Title"
{% endhighlight %}

Default works great if you want all your posts in one directory, but if you're like me and want to group them into subfolders like `/posts`, `/portfolio`, etc. Then this is the command for you. By specifying the DIR it will create a new post in that folder and populate the `categories:` YAML with the same value.

{% highlight bash %}
$ octopress new post "New Post Title" --dir posts
{% endhighlight %}

### New Page

To create a new page use the following command.

{% highlight bash %}
$ octopress new page new-page/
{% endhighlight %}

This will create a page at `/new-page/index.md`

---

## Layouts and Content

Explanations of the various `_layouts` included with the theme and when to use them.

### Post and Page

These two layouts are very similar. Both have an author sidebar, allow for large feature images at the top, and optional Disqus comments. The only real difference is the post layout includes related posts at the end of the page.

### Post Index Page

A [sample index page]({{ site.url }}/posts/) listing all posts grouped by the year they were published has been provided. The name can be customized to your liking by editing a few references. For example, to change **Posts** to **Writing** update the following:

* In `_config.yml` under `links:` rename the title and URL to the following:
{% highlight yaml %}
  links:
  - title: Writing
    url: /writing/
{% endhighlight %}
* Rename `posts/index.md` to `writing/index.md` and update the YAML front matter accordingly.
* Update the **View all posts** link in the `post.html` layout found in `_layouts` to match title and URL set previously.

### Feature Images

A good rule of thumb is to keep feature images nice and wide so you don't push the body text too far down. An image cropped around around 1024 x 256 pixels will keep file size down with an acceptable resolution for most devices. If you want to serve these images responsively I'd suggest looking at the [Jekyll Picture Tag](https://github.com/robwierzbowski/jekyll-picture-tag) plugin[^plugins].

[^plugins]: If you're using GitHub Pages to host your site be aware that plugins are disabled. You'll need to build your site locally and then manually deploy if you want to use this sweet plugin.

The post and page layouts make the assumption that the feature images live in the `images/` folder. To add a feature image to a post or page just include the filename in the front matter like so. It's probably best to host all your images from this folder, but you can hotlink from external sources if you desire.

{% highlight yaml %}
image:
  feature: feature-image-filename.jpg
  thumb: thumbnail-image.jpg #keep it square 200x200 px is good
{% endhighlight %}

To add attribution to a feature image use the following YAML front matter on posts or pages. Image credits appear directly below the feature image with a link back to the original source if supplied.

{% highlight yaml %}
image:
  feature: feature-image-filename.jpg
  credit: Michael Rose #name of the person or site you want to credit
  creditlink: http://mademistakes.com #url to their site or licensing
{% endhighlight %}

### Thumbnails for OG and Twitter Cards

Feature and thumbnail images are used by [Open Graph](https://developers.facebook.com/docs/opengraph/) and [Twitter Cards](https://dev.twitter.com/docs/cards) as well. If you don't assign a thumbnail the default graphic *(default-thumb.png)* is used. I'd suggest changing this to something more meaningful --- your logo or avatar are good options.

**Pro-Tip**: You need to [apply for Twitter Cards](https://dev.twitter.com/docs/cards) before they will begin showing up when links to your site are shared.
{:.notice}


<!--- This is how to insert a figure (as in a scientific paper)

<figure>
  <img src="{{ site.url }}/images/paragraph-indent.png" alt="screen shot of paragraphs with default indent style set">
  <figcaption>Example of the default paragraph style (indented first line and bottom margin removed).</figcaption>
</figure>

/-->


### Videos

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

Not sure if this only effects Kramdown or if it's an issue with Markdown in general. But adding YouTube video embeds causes errors when building your Jekyll site. To fix add a space between the `<iframe>` tags and remove `allowfullscreen`. Example below:

{% highlight html %}
<iframe width="560" height="315" src="http://www.youtube.com/embed/PWf4WUoMXwg" frameborder="0"> </iframe>
{% endhighlight %}

### Social Sharing Links

Social sharing links for Twitter, Facebook, and Google+ are included on posts/pages by default. To hide them on specific posts or pages add `share: false` to the YAML Front Matter. If you'd like to use different social networks modify `_includes/_social-share.html` to your liking. Icons are set using [Font Awesome](http://fontawesome.io).

---

## Further Customization

Jekyll 2.x added support for Sass files making it much easier to modify a theme's fonts and colors. By editing values found in `_sass/variables.scss` you can fine tune the site's colors and typography.

For example if you wanted a red background instead of white you'd change `$bodycolor: #fff;` to `$bodycolor: $cc0033;`.

To modify the site's JavaScript files I setup a Grunt build script to lint/concatenate/minify all scripts into `scripts.min.js`. [Install Node.js](http://nodejs.org/), then [install Grunt](http://gruntjs.com/getting-started), and then finally install the dependencies for the theme contained in `package.json`:

{% highlight bash %}
npm install
{% endhighlight %}

From the theme's root, use `grunt` concatenate JavaScript files, and optimize .jpg, .png, and .svg files in the `images/` folder. You can also use `grunt dev` in combination with `jekyll build --watch` to watch for updates JS files that Grunt will then automatically re-build as you write your code which will in turn auto-generate your Jekyll site when developing locally.

---

## Questions?

Found a bug or aren't quite sure how something works? By all means Ping me on Twitter [@mmistakes](http://twitter.com/mmistakes) or [file a GitHub Issue](https://github.com/mmistakes/minimal-mistakes/issues/new). And if you make something cool with this theme feel free to let me know.

---

## License

This theme is free and open source software, distributed under the MIT License. So feel free to use this Jekyll theme on your site without linking back to me or including a disclaimer.
