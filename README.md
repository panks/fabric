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



##Author

Pankaj Kumar (me@panks.me)

