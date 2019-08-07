---
layout: post
title:  "Jekyll blog with Github Pages"
date:   2019-08-06 16:39:35 -0700
categories: jekyll update
---

Here is how I went about setting up this blog using Jekyll and Github Pages. Note that the setup assumes MacOS. 

### 1. **Setup Jekyll on your local machine**

Follow the simple instructions on the [Jekyll website](https://jekyllrb.com/), replacing my-awesome-site with an appropriate name for your blog folder. Copied below; run this on your terminal

{% highlight terminal%}
$gem install bundler jekyll
$jekyll new my-awesome-site
$cd my-awesome-site
$bundle exec jekyll serve
# => Now browse to http://localhost:4000
{% endhighlight %}

### 2. **Set up a Github Pages repo**

Create a new repository on Github [here](https://github.com/new) called username.github.io where username is your Github username. Note that the username in your repo name has to match your Github username. 

### 3. **Set up your local git repo to link to your Github repo**

On your local machine, go to your blog folder (`my-awesome-site` in this example), and do the following

{% highlight terminal %}
$git init
$git remote add origin git@github.com:username/
username.github.io.git
{% endhighlight %}

The above will initialize your blog folder as a git repo and link it to the Github repo you created in step 2. Replace username in the remote repo url with your Github username.

### 4. **Update gemfile and config.yaml to reflect the desired theme**

For your blog to show up properly on Github pages, you need to make the following changes:
<br>
<br>
Add the following to your Gemfile in your local blog repo
{% highlight ruby %}
gem "hitchens-theme" # blog theme
gem "github-pages", group: jekyll_plugins 
gem "jekyll-remote-theme" 
{% endhighlight %}


Then run `build install` to install the gem.
<br> 
<br>
Make the following changes to your `_config.yml` file in your local blog repo

{% highlight yaml %}
# theme: minima  # comment the default theme
remote_theme: patdryburgh/hitchens 
{% endhighlight %}

Note that for Github pages to apply the theme, you need to specify it as a remote theme rather than simply update theme to `theme: <your chosen theme>`. Also change the title, description and other sections as needed. 

### 5. **Push your changes to Github**

Run the following lines on your terminal to add, commit and push changes on your local repo to Github.

{% highlight terminal %}
git add .
git commit -m 'commit message'
git push -u origin master
{% endhighlight %}

You should now be able to see your blog at your `username.github.io`
<br>
<br>
Note that there are other ways of setting up your blog. The above is the approach I followed, and an aha! moment was the realization that I need to specify the theme as a remote-theme as I have done above for the blog to display on Github. 
<br><br>
You should also be able to view your blog on your local machine by typing  `bundle exec jekyll serve` on your terminal, and going to [localhost:4000](http://localhost:4000/)















