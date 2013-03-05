#Fabric

Fabric is a minimal and responsive theme for [Octopress](http://octopress.org/).
View the theme in action [here](http://panks.me)

##Install

Type the code below in terminal.

	$ cd octopress
	$ git clone git://github.com/panks/fabric.git .themes/fabric
	$ rake install['fabric']
	$ rake generate

Have problems when installing with zsh? Try `rake install\['fabric'\]` instead.

##Features

- Clean design
- Tapirgo search
- Responsive layout
- Ajaxified pages
- and many more..


##Instructions
(The content below I have copied from a blog post which I made about this theme, so It would not repesent a very typical/formal Readme file)

* [Installation](#installation)
* [Disable Ajaxification](#disable-ajaxification)
* [Tapirgo Search](#tapirgo-search)
* [Add accounts for social links](#add-accounts-for-social-links)
* [Disable scroll to top button](#disable-scroll-to-top-button)
* [Image border](#image-border)
* [Arrow after ‘Read on’](#arrow-after-%E2%80%98read-on%E2%80%99)


###Installation

###[Click here to download the latest version](https://github.com/panks/fabric/archive/master.zip)

It’s the regular, and you probably won’t even read this section if you have ever played a little with Octopress. Go to your Octopress directory, clone my theme and run the rake script to install it, and then ‘rake generate’ to apply it to your blog.

    $ cd octopress
    $ git clone git://github.com/panks/fabric.git .themes/fabric
    $ rake install['fabric']
    $ rake generate


###Disable Ajaxification

Here I tried something new, though the blog is completely static and based on pre-baked files, I thought it would be cool to load the pages(not post) without reloading the entire blog in browser.
It’s a small script but does the job, also it gives your hash url so you can actually pass the links to others if you want.

To use it make the `list item` of your navigation bar item with id as ‘**ajax**’, navigation bar is defined in `octopress/.themes/fabric/source/_includes/custom/navigation.html` for instance:

    <li id="ajax"><a href="{{ root_url }}/index.html">Home</a></li>
    <li id="ajax"><a href="{{ root_url }}/about/index.html">About</a></li>
    <li id="ajax"><a href="{{ root_url }}/blog/archives/index.html">Archives</a></li>
    <li><a href="{{ root_url }}/atom.xml">RSS</a></li>

Anyway, some might find it little annoying or uneasy to work with and prefer just plan simple urls and reloading of pages. So to disable it:
Go to: `octopress/.themes/fabric/source/_includes/head.html` and remove the javascript file **ajaxify.js** I have also commented it in there for easy identification.

And then reinstall the theme and rebuild your blog with

    $ rake install['fabric']
    $ rake generate

or you can remove those `id="ajax"` for list items in navigation bar.

Done!


###Tapirgo Search

This is probably the biggest change which I put into the theme which was not available by default and wasn’t even discussed about in other themes available - [Tapirgo](http://tapirgo.com/)

Most of the people using Octopress use google custom search for providing search to their users but I don’t really like it that way,

**One** - You have redirect your users to another website in a new tab

**Two** - Google shows it’s ads which is annoying

and **Three** -Google search from it’s cache so your readers won’t get the latest content from your website listed on the search result rather they would get something which google stored at it’s server while crawling your blog, so it might contain some article which you deleted a few days back or might not contain the latest post of yours. Which beats the whole point of searching the blog.

Taprigo on the other hand gives you a real nice way to search static websites, using your [RSS](http://en.wikipedia.org/wiki/RSS) feeds i.e. your atom.xml file, and it’s keeps reading your feeds every 15 mins (well that’s what they claim) and they also provide you with their API using which you can ping the server to reindex your feeds immediately.

For using is just [go to tapirgo](http://tapirgo.com/) and enter the url to your atom.xml file in ‘Your RSS feed’ field and your email in the next field and click ‘go’ and then you would be provided with two tokens, one is public and the other one would be a secret token, you would need only the public token for using it in your Octopress blog.

![Tapirgo](http://panks.me/images/tapirgohome.png)

Now create a field named `tapir_token` in your `_config.yml` file in Octopress directory and assign it’s value as the public token. That’s all from your side. Now one can search your blog while being inside your blog and in the real content.
For some reason if you want to use google search then you can do it this way: Go to: `octopress/.themes/fabric/source/_includes/custom/navigation.html` and

**Replace**

    <form method="get" action="{{ root_url }}/search.html" id="search">
        <input name="query" type="text" style="margin-top:20px;" size="40" placeholder="Search..." x-webkit-speech />
    </form>

**With**


    <form class="search" action="{{ site.simple_search }}" method="get">
        <input class="alignright" type="text" name="q" results="0">
        <input type="hidden" name="q" value="site:{{ site.url | shorthand_url }}">
    </form>


###Add accounts for social links

It has a real nice social bar in which you can display your github, facebook, twitter, linkedin, googleplus, lastfm, skype and youtube accounts. For using it just make a field `sitename_user` in your `_config.yml`file and supply your username/id in it.

For instance for facebook, add `facebook_user: yourfacebookusername`

For some of the services the fields are already present in the `_config.yml` file


###Disable scroll to top button

I have give a scroll to top button, which become visible as the user start scrolling the page and would scroll the top of the page when clicked on it, which slows it’s speed down when reaches the top.

But there are all sort of people on this planet and for some weird reason from mars few of them might find it annoying so to disable it:

Go to: `octopress/.themes/fabric/source/_layouts/default.html` and remove the following lines as described there.

And then reinstall the theme and rebuild your blog

    $ rake install['fabric']
    $ rake generate


###Image border

Image borders by default are made in such way to give the effect of a real photograph pasted on a surface.

![Image Border](http://panks.me/images/imagewithborderex.png)

To disable that effect, class your image to ‘noborder’ : `<img src="/image/location/filename.png" class="noborder">`


###Arrow after ‘Read on’

This is a tiny stuff and someone who has used Octopress for a month of two won’t even need it, but I just felt like mentioning it for the sake of completion.

When you use in your posts to show excerpts then there is a ‘Read on’ link after each summary to go the full post and you would notice there would be bold arrow before it and a tiny arrow in front of it. That bold arrow is put by my and the tiny arrow is put by Octopress configuration, so to remove the tiny arrow go to your `_config.yml` file and search for this line

`excerpt_link: "Read on &rarr;"  # "Continue reading" link text at the bottom of excerpted articles`

and remove `&rarr;` from it.

Well that’s all, hope you would like this theme. For furthur information or any suggestion feel free to contact me.


###Pull requests are very much welcome and appreciated.

##Author

Pankaj Kumar (me@panks.me)


##License

[The MIT License (MIT)](http://pankaj.mit-license.org/)
