---
layout: post
author: rahimi
---

<div class="tldr">
  Emacs users are banned from this post!
</div>

<div class="title-font">
    <h3>Introduction</h3>
</div>

Nah, I'm kidding ! Emacs users or any IDE users are welcome in this post. I actually use VSCode and Neovim interchangeably due to several reason which I will explain later. So, what's so hard about __how to setup Neovim in Debian__ ? You just have to install it with `$ sudo apt install neovim` and call it with `nvim` command right ? Well, yes and no. 

If you want to set it up manually, then you're more than welcome to use command above and stop reading this post, stop wasting your time and go do something valuable. The reason why I'm writing this is: for someone who want to use Neovim's distribution?--I don't know what you called it, distribution or flavour? Or something like that--like LazyVim etc.

"I'm very excited to install Neovim with LazyVim, every YouTuber are using it and it'll be shame if I didn't learn it". If we go to LazyVim official website, you will be disappointed when you see the main requirement is Neovim >= 0.9.0, which needed to be built with LuaJIT. Oh no, let's check which version comes with Debian.

{% highlight shell %}
apt search neovim
{% endhighlight %}

And we can see that it will return.

{% highlight shell %}
neovim/stable 0.7.2-7 amd64
  heavily refactored vim fork
{% endhighlight %}

"God, we can't install LazyVim with this version ! Should we look for another IDE ? Or even better, to look for another distros which come with latest version of Neovim ?", This may be what's in your small brain--for now--after you see __neovim/stable 0.7.2-7__, very stable indeed. 

<div class="title-font">
    <h3>Setup</h3>
</div>

Now, if this is your problem, come along, I have a solution for you. What ? Flatpak ? Well, maybe you can use Flatpak, but I'm going to show how you can use App Image instead.

First of all, we have to download the App Image from Neovim's GitHub, you can do this by using curl.

{% highlight shell %}
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
{% endhighlight %}

Then, turn it into executable, what's the point of a program if you can't execute it right ?

{% highlight shell %}
chmod u+x nvim.appimage # there another way to do this by using numbering, but...idk :p
{% endhighlight %}

Lastly, we have to move this App Image to our path, I choose `/usr/local/bin/`.

{% highlight shell %}
echo $PATH # will list down all PATH in your system
sudo mv nvim.appimage /usr/local/bin/nvim # move the App Image from current folder to path with the name nvim
{% endhighlight %}

**NOTE**: Notice that I use sudo because you need to have super user permission to move something into /usr/local/bin/. Then, I change nvim.appimage to only nvim(the last line) so that I can call it nvim instead of nvim.appimage anytime I want to use it. **END**

This is it, now you can install LazyVim with this version of Neovim--which currently v0.10.2--how fun is that ? The only cons of using App Image: You have download the Neovim App Image and redo all this step every time there's new version release and you want to update. This is because App Image didn't work like package manager, you are the manager for them--or maybe there is App Image manager out there which I didn't explore yet, since I rarely use app image.

<div class="title-font">
    <h3>The Problem</h3>
</div>

Now, maybe you're asking me, "Why you're still using VSCode if you like Neovim so much ?". Well, the reason is......hmmm....How do I explain this ?

The problem is: I can't push my code to GitHub. When I do `git push`, It always asked for username and password, which in turn will return error every time. But, it worked just fine when I push it using VSCode git extension, that's the reason why I use VSCode. 

"What's so stupid about that?" You may asked. It's stupid because I've just realized--actually this past few days--that I've clone all my repo using HTTPS instead of SSH and that's the reason why I can't push to GitHub. If you're wondering, I follow the instructions from The Odin Project and I actually use this step several time, and it doesn't work every time--push to GitHub.

Then, I reread the instructions and you know what, you literally have to generate **SSH_KEYGEN** and copy it to your **SSH and GPG keys** setting. Tell me, "Why on earth I can't figure it out until now that this setup is meant for SSH and still do clone in HTTPS?". It obviously tell that this is for SSH, not HTTPS. Well, I learn from my mistake and yeah, if there're people out there who face the similar problem like me--doubt there is--here are the solution, clone your repo using SSH instead of HTTPS. 


<div class="title-font">
    <h3>Conclusion</h3>
</div>

Well, you actually have other options to install the latest version of Neovim such as Flatpak, build from source, etc. That's the beauty of open source program where you have other alternative to choose from. I hope you have fun with you new Neovim with LazyVim setup and get good with it. And I really hope we can learn a thing or two from this post, mainly to **read instructions carefully and to try understand them before running amok**......CYA!

<div class="title-font">
    <h3>References</h3>
</div>

1. LazyVim: [link](https://www.lazyvim.org/)
2. Setting up Git by The Odin Project: [link](https://www.theodinproject.com/lessons/foundations-setting-up-git)
