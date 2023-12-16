+++
title = 'Let me teach you how to set up Hugo!'
date = 2023-12-16T20:00:20+05:30
draft = false
+++
# What is Hugo?
![Hugo logo](/Hugo.png)

Hugo is simply a static site generator. What it does is that it allows you to build static websites by just editing your Markdown files and it will create the HTML code. It also does this blazingly fast, so it lets you compile hundreds of thousands of pages with very minimal downtime. 

# Why would I want to learn this?

Good question! I was also wondering why anyone would want to learn about Hugo, as there are plenty of good platforms where we can write and it would be appreciated just as well, and might even get a better reach. 

For me personally, the two main reasons that stood out were 
-  Typing into a text editor is much faster for me than typing into a browser. I also like coding, so the look and feel of my **light-mode** VSC editor is much more appealing to write than into a browser with a clunky rich-text editor.

- I have complete control over how I want to structure my blogs and posts, and people who are genuinely interested are not sidetracked by other authors. There would also be some connectivity between one post and the next one, which is hard to maintain on an external platform

So, if this is something you wish to do as well, without having to spend hours on trying to figure out how to install this thing, lets get right in!

# Installation

So, Before installing Hugo, we need to install [Git](https://git-scm.com/downloads) for version controlling our files and building Hugo from source code. We also need to install the programming language [Go](https://go.dev/dl/) which allows us to use modules in Hugo as well as build it from source code.

However, It is easier to download it from a package manager than from source, because of the less amount of stuff you need to download. I would **HIGHLY** recommend to download both Git and Go so that we can deploy our blogs to Github Pages in the future.

There are different Package Managers like Chocolatey, Scoop and Winget for Windows, Homebrew and Snap for Linux systems (which is the easiest because snap comes pre-installed with many Linux Distro's) and Homebrew and MacPorts for Mac OS.

I first downloaded [Scoop](https://scoop.sh/) by opening Windows Powershell and running these commands

```
> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
> Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
and then installed the extended version of Hugo using a single command 

```
scoop install hugo-extended
```

We can check if Hugo is installed by opening up Command Prompt and running 

```
hugo version
```
This gives us an output that looks like this

```
hugo v0.121.1-00b46fed8e47f7bb0a85d7cfc2d9f1356379b740+extended windows/amd64 BuildDate=2023-12-08T08:47:45Z VendorInfo=gohugoio
```

## Starting your first Blog

Now, the process is much easier. There are only a couple of very simple steps to get quickly started on the first blog post.

### Setting up a site

Here we set up a new 'site' for Hugo using the below command.
```
hugo new site <your site name>
``` 
This means that the development environment for all your posts is created into a folder. To the people familiar with programming, this is similar to using create-react-app or using a builder like Vite to set up your stack.

Now, we run the next few commands to add the theme to our site:

```
cd <your site name>
```
This moves you into your site directory

```
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
```

This does a few things. First it initializes a git repository, then it adds a Hugo theme as a submodule, since it is also a repository present in Github. Finally, in the .toml file, we indicate that we are using the specific theme.

```
hugo server
```
Finally we run this to see a basic template in our localhost which looks something like this

![Initial Project Screenshot](/Hugo2.png)

### Adding a post

We can add a new post to hugo, using the below command.

```
hugo new content posts/example.md
```

This creates a markdown file with the following fields: 

- Title
- Date of Creation
- Draft

The title is self explanatory, It's the title of the post which you wish to create. The date is automatically recorded when you use the command to create a post. Draft is usually set to true, which lets you test the post before pushing to production. 

### Conclusion

Now youre almost done! You can edit the title, add text and markdown and voila it gets modified. To see the changes you can run this to see the live changes as your blog gets created.
```
hugo server
```
 

Finally, the site can be pushed to a Github repository, and published to Github Pages, or Firebase or Netlify depending on which platform you prefer. 

With this, you can also start blogging on your own site in less than 30 minutes! Do let me know if you found it useful, and any other topics that you wish to see me cover. Signing off for now!