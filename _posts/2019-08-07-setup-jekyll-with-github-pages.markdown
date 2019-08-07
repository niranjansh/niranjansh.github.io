---
layout: post
title:  "Jekyll blog with Github Pages"
date:   2019-08-06 16:39:35 -0700
categories: jekyll update
---

Here is how I went about it for the blog you are reading right now. Note that I am using a Macbook Pro running MacOS Mojave

### 1. **Setup Jekyll on your local machine**

Follow the simple instructions on the [Jekyll website](https://jekyllrb.com/), replacing my-awesome-site with an appropriate name for your blog folder

{% highlight terminal%}
$gem install bundler jekyll
$jekyll new my-awesome-site
$cd my-awesome-site
$bundle exec jekyll serve
# => Now browse to http://localhost:4000
{% endhighlight %}

### 2. **Set up a Github Pages repo**

Create a new repository on Github [here](https://github.com/new) called username.github.io where username is your Github username. Note that the username has to match your Github username. 

### 3. **Set up your local git repo to link to your Github repo**

On your local machine, go to your blog folder (`my-awesome-site` in this example), and do the following

{% highlight terminal %}
$git init
$git remote add origin git@github.com:username/
username.github.io.git
{% endhighlight %}

This will set up the blog on the local machine from step 1 as a git repo and link it to the Github rep you created in step 2. Replace username with your github username

### 4. **Update gemfile and config.yaml to reflect the desired theme**

For your blog to show up properly on Github pages, you need to make the following changes:

Make the following to your Gemfile in your local blog repo
{% highlight ruby %}
gem "hitchens-theme" # blog theme
gem "github-pages", group: jekyll_plugins 
gem "jekyll-remote-theme" 
{% endhighlight %}


Then run `build install` to install the gem

Make the following changes to your `_config.yml` file

{% highlight yaml %}
# theme: minima  # comment the default theme
remote_theme: patdryburgh/hitchens 
{% endhighlight %}

Note that for Github pages to apply the theme, you need to specify it as a remote theme rather than simply update theme to `theme: hitchens-theme`. Also change the title, description and other sections as needed. 

### 5. **Push your changes to githib**

{% highlight terminal %}
git add .
git commit -m 'commit message'
git push -u origin master
{% endhighlight %}

You should now be set-up with your blog!

Note that there are other ways of setting up your blog. The above is the approach I followed, and one of the aha moments was the realization that I need to specify the theme as a remote-theme as I have done above, rather than just change the theme in the yaml to the one I had on my local. 

You should also be able to see your blog on your local machine by typing  `bundle exec jekyll serve` on your terminal, and going to [localhost:4000](http://localhost:4000/)















