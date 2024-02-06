---
title: "Building and Deploying Personal Website Using Hugo and Github Action"
date: 2024-01-30T15:10:21+05:30
draft: false
---

In today's digital age, having a personal website is crucial for showcasing your portfolio, sharing your thoughts, and establishing your online presence. In this article, we will walk through the process of creating a personal website using the Hugo Site Generator and automating the deployment with GitHub Actions.

## Why Do You Need a Personal Website?

1. **Professionalism:** A personal website adds a touch of professionalism to your online presence, making it easier for potential employers or clients to find and learn more about you.

2. **Portfolio Showcase:** It serves as an excellent platform to showcase your work, projects, and achievements in a visually appealing manner.

3. **Content Sharing:** A personal website allows you to share your thoughts, experiences, and expertise with a broader audience, positioning yourself as an authority in your field.

Now, let's dive into the step-by-step process of creating and deploying your personal website.

## Step 1: Create a New Hugo Site

```bash
hugo new site rd-website --format yaml
cd .\rd-website\
```

This command initializes a new Hugo site named "rd-website" and navigates to the project directory.

## Step 2: Initialize Git and Add a Theme

```bash
git init
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
echo "theme: PaperMod" >> config.yaml
```

These commands set up Git for version control and add a Hugo theme named "PaperMod" to your project.

## Step 3: Create a Blog Page

```bash
hugo new blogs/2024/setting_up_hugo.md
```

This command creates a new blog post under the "blogs" directory.

## Step 4: Configure Hugo

Edit the `config.yaml` file and set the `baseURL` to your GitHub Pages URL:

```yaml
baseURL: "https://rahuldabgotra.github.io/"
```

## Step 5: Run Locally and Check

```bash
hugo server -D
```

This command runs the Hugo server locally, allowing you to preview your website. The `-D` flag includes drafts.

## Step 6: Push to GitHub

```bash
echo "# rahuldabgotra.github.io" >> README.md
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/rahuldabgotra/rahuldabgotra.github.io.git
git push -u origin main
```

These commands initialize a GitHub repository, add a README file, commit changes, and push them to the main branch.

## Reference Resources

- **Video Tutorial:**
  [Deploy Hugo to GitHub Pages](https://youtu.be/_QSr2_pxIJs?si=W4HCuWr29bkutc8t)

- **Articles:**
  [Deploy Hugo to GitHub Pages](https://theplaybook.dev/docs/deploy-hugo-to-github-pages/)
  [GitHub Pages Quickstart](https://docs.github.com/en/pages/quickstart)

By following these steps, you've successfully created and deployed your personal website using Hugo and GitHub Actions. This automation ensures that your website stays up-to-date with minimal effort, allowing you to focus on creating compelling content.
