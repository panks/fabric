#Fabric

Fabric is a minimal and responsive theme for Octopress.

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

Read [here] (http://panks.me/blog/2013/01/new-octopress-theme-fabric/) for detail on installation and setup.

##Instructions


###Installation
It’s the regular, and you probably won’t even read this section if you have ever played a little with Octopress. Go to your Octopress directory, clone my theme and run the rake script to install it, and then ‘rake generate’ to apply it to your blog.

        $ cd octopress
        $ git clone git://github.com/panks/fabric.git .themes/fabric
        $ rake install['fabric']
        $ rake generate


###Disable Ajaxification

Here I tried something new, though the blog is completely static and based on pre-baked files, I thought it would be cool to load the pages(not post) without reloading the entire blog in browser.
It’s a small script but does the job, also it gives your hash url so you can actually pass the links to others if you want.

To use it make the `list item` of your navigation bar item with id as ‘ajax’, navigation bar is defined in `octopress/.themes/fabric/source/_includes/custom/navigation.html` for instance:

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
For using is just go to tapirgo and enter the url to your atom.xml file in ‘Your RSS feed’ field and your email in the next field and click ‘go’ and then you would be provided with two tokens, one is public and the other one would be a secret token, you would need only the public token for using it in your Octopress blog.


##Author

Pankaj Kumar (me@panks.me)

