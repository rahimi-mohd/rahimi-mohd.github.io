---
layout: post
author: rahimi
---

<div class="tldr">
    Jekyll have been working super fine for me now, I don't have any problem with it even when I try to set it up on different OS with different package manager (Debian based to Arch based).
</div>

**Hello, Jekyll!** I actually really love to write and blog, the reason why I'm not updating my blog is because it's pain in the ass to copy and paste my `base.html`--kinda like a template system for my blog. I actually heard about jekyll a long way back, but I don't have time to try it (or maybe I'm lazy, I don't know).

So, what I'm looking for is a system or framework that can automate or render my writing into proper html, I try to use Emacs (org to html) and Obsidian (markdown to html) but I've never success with the templating system. Yes, I can export my writing into html but I struggle with the templating and styling.

Now that I have some extra time to waste, I want to try jekyll and play around with it. First of all, we have to do some installation and setup before we can use jekyll.

### Setup  

I use Linux Mint for this setup, it will be different based on your operating system and distros. You actually can follow the step from jekyll's [Quickstart](https://jekyllrb.com/docs/) and [Installation](https://jekyllrb.com/docs/installation/) pages if you have any problems.  

Install all the requirements

{% highlight shell %}
sudo apt install ruby-full build-essential zlib1g-dev
{% endhighlight %}

Add `GEM_HOME` and it executable path in `.bashrc`

{% highlight shell %}
.bashrc
GEM_HOME="$HOME/.gems"  # change .gems to gems if you don't want to hide it
export PATH=$PATH:"$HOME/.gems/bin"
{% endhighlight %}

Install jekyll and bundler

{% highlight shell %}
gem install jekyll bundler
{% endhighlight %}

Okay, now we're halfway through the process. We've install Ruby, jekyll, and bundler. Now come the fun part, creating our blog. Create a new folder where you want to put your blog, let's called it `my-blog`.

{% highlight shell %}
mkdir -p Documents/my-blog    # create folder
cd Documents/my-blog          # change direction into my-blog
bundle init                   # create new Gemfile
{% endhighlight %}

To add jekyll as dependency, we have to add `gem "jekyll"` into Gemfile, and run `bundle` to install it. It's also a good time to start commiting our development journey, let's initialize a Git repository and commit it.

{% highlight shell %}
git init
vim .gitignore                        # change vim to any editor you comfortable with

.gitignore
Gemfile.lock                            # this will prevent git to add Gemfile.lock into repository

git add .                             # add all files and folders into stage 
git commit -m "initial blog setup"    # commit all changes
{% endhighlight %}

We're almost there, the last step before we can serve our website is to have a..... website, Duh!. Remember that we still didn't write any HTML, let's fix that by creating new `index.html` in root folder and write anything you want--this is not HTML tutorial. To start serving your website, run `$ jekyll serve` and open `http://localhost:4000` on your favorite web browser. Walla, here's your magnificent, beautiful, little website ready to be seen by the entire world--Nah, just kidding, this only serve the website on your localhost port 4000, you have to deploy it to make it available to the entire world.

Finally, remember that this is the most basic setup, you can follow the official step by step tutorial on jekyll website to get your website running and deploy it to github pages (like me) or maybe on your favorite cloud system or whatever, it's your blog and you can do whatever you like with it.

### Reason

It's obvious why I changed to jekyll, but the main reason is the templating system. I already familiar with jinja2 and Django template (I don't know what they called Django template, so maybe just Django template?), to have this kind of system is the major improvement for any blogger--one more time, I'm not a __blogger__ blogger, just a guy who like to write and want to improve his workflow. My old, plain, and traditional blogging system look like this

{% highlight shell %}
- index.html  
- blogs/
    - base.html
    - blog1.html
    - blog2.html
- statics
    - style.css
    - app.js
{% endhighlight %}

I have to edit `base.html`, save it as `blog{n}.hmlt`, and index it in my index.html. Actually, it's not so bad, but why not use templating system to make my life easier right ? 

### Conclusion

Actually, this is the second day I'm using jekyll--on the time I'm writing this post--so I can't give more comment it pros and cons, and my experience using it, I will come back to it later. But for now, I'm excited to write more blog and to explore more about jekyll--theme? Finally, please, please, please excuse my website's ugly interface, yeah I know it's not beautiful (yet!), but I'm going to fix that later!

---

### Update - 28Sept2024

See, I have once more install Arch with i3wm and I need to re-setup jekyll. This time, I chose to use `rbenv` route to install Ruby, following the guide from [The Odin Project](https://www.theodinproject.com/lessons/ruby-installing-ruby). Here how you can do it too:

> Note: I already have `base-devel` installed, you may need to install it first.

Install rbenv

{% highlight shell %}
git clone https://github.com/rbenv/rbenv.git ~/.rbenv # clone rbenv
~/.rbenv/bin/rbenv init # initialize rbenv
{% endhighlight %}

For some reason, rbenv init command--second command--write the script into .bash_profle and my system cannot read it (or find it), so how I fixed it is by pasting the script to my .bashrc and it work fine.

Install ruby-build

{% highlight shell %}
mkdir -p "$(rbenv root)"/plugins
git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
rbenv -v # this will return rbenv version if successfully installed
{% endhighlight %}

Then, we can install Ruby

{% highlight shell %}
rbenv install {ruby_version} --verbose # change ruby_version into the version that you want, the latest during my installation is 3.3.5
rbenv global {ruby_version} # change ruby_version to the one that you install, this tell our system which Ruby we want to use
{% endhighlight %}

Finally, check Ruby version for our system

{% highlight shell %}
ruby -v # this should return ruby_version, in my case 3.3.5
{% endhighlight %}

Now, we can follow our initial setup above, starting from **Add `GEM_HOME` and it executable path in `.bashrc`**.

**NOTE** Since this is updated setup, meaning that I already have my blog set up in github, I need to install several gems packages (or modules, I don't know what you call it) such as pygments.rb, jekyll-sitemap, jekyll-feed, jekyll-seo-tags and github-pages. I installed all this packages with `$ gem install {package_name} # change package_name with the needed packages`. **END**

**NOTE** You also may or may not get error when trying to run `jekyll serve`, the solution is to run `bundle exec jekyll serve`  instead. **END**

Have fun and...CYA!
