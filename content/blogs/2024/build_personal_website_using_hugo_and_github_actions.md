---
title: "Build Personal Website using HUGO and GitHub Actions"
date: 2024-01-30T19:31:27+05:30
draft: false
tags: ["GitHub Actions", "Hugo"]
categories: ["Tech"]
---

## Getting Started with Hugo
Hugo is a fast and flexible static site generator written in Go. In this guide, we'll walk through the steps to get started with Hugo and create your first tech blog.

### Prerequisites
Before you begin, make sure you have the following installed on your system:
- Hugo (Follow the installation instructions on [Hugo's official website](https://gohugo.io/getting-started/installing/))

### Creating a New Hugo Site
To create a new Hugo site, open your terminal and run the following commands:
```bash
hugo new site my-tech-blog
cd my-tech-blog
```

### Initialize a New Git Repository and add Git Submodule
These command initializes a new Git repository in the current directory and adds the PaperMod theme as a Git submodule to our Hugo project.
```bash
git init
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```
### Create a Hugo Configuration File with Theme Settings
This command creates or appends to a hugo.yaml file and sets the theme for your Hugo site to "PaperMod."
```bash
echo "theme: PaperMod" >> hugo.yaml
```

### Create a New Blog Post
This command generates a new Markdown file for a blog post titled "first_blog" in the content/blogs/2024/ directory. The file will be pre-populated with some basic front matter.
```bash
hugo new blogs/2024/first_blog.md
```
### Run the Hugo Development Server
This command starts the Hugo development server, allowing you to preview your site locally. The -D flag includes content marked as draft in the preview. Visit http://localhost:1313/ in your web browser to see your Hugo site with the PaperMod theme and the newly created blog post.
```bash
hugo server -D
```

Hurrah!!🥳🎉 We have created our first website using HUGO site generator. 
Adjust the commands and configurations as needed based on your project requirements.
