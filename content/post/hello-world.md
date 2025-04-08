---
title: Hello World 🌍
description: This is my very fist post on my blog.
dateFormatted: April 8th, 2025
---

![Hello World](/assets/images/posts/hello-world.jpeg)

Oh, hi there! 👋 Welcome to my very first blog post. Think of it like that awkward "Hello, World!" program we all wrote when first learning to code.

I've decided to kick things off by embracing the concept of less is more, mostly because I’m lazy—oops, I meant "efficient" and I found out static sites are an awesome way to achieve this. Plus, who has time for complicated CMS setups, database migrations, updates, etc etc...

## 🚀 Static Websites: When Less Really is More

You might be thinking: "Static websites? Sounds boring!" But hear me out, they're like the IKEA furniture of web development—sleek, functional, and occasionally frustratingly simple. No moving parts means fewer things to break, less to mantain.

I've been experimenting with Static by DevDojo because:

- It's free (my favorite price).
- It's easy (my favorite difficulty level).
- You can get something looking nice really fast.

## 🛠️ How to Static Like a Pro (or at least Fake It)
Here's the quick guide to getting started with Static by DevDojo:

Install Static CLI: First, ensure you have Node.js installed. Then, open your terminal and run:

`npm install -g @devdojo/static`

This command installs the Static CLI globally, allowing you to create and manage your static sites with ease.

Create a New Project: Navigate to the directory where you want your project to reside and run:

`static new my-static-site`

Replace my-static-site with your desired project name. This command creates a new folder with all the necessary files for your static site.

Navigate to Your Project Folder:

`cd my-static-site`

Move into your project's directory to start working on it.

Start the Development Server: Launch the local development server with:

`static dev`

Your site is now running locally at http://localhost:3000/. Open this URL in your browser to view your site.

Build for Production: Once you're satisfied with your site, generate the production-ready files by running:

`static build`

This command creates a dist folder containing your optimized static files, ready for deployment.

Congratulations, you're now the proud owner of a static website!

## 🤔 Why Static Websites Are Actually Awesome

⚡ Speed: Super fast loading times due to optimized static assets.

🔐 Security: Less vulnerable to hacking because, honestly, there’s nothing dynamic to hack.

💰 Cost-effective: Hosting is virtually free. For example, GitHub Pages offers free hostin


## 🌐 Deploying Your Static Website on GitHub Pages

Let’s take advantage of GitHub Pages to host your static site completely for free! Follow these simple steps to deploy your site automatically each time you update your repository.

Step-by-Step Guide for GitHub Pages
1. Create a GitHub Repository:

Visit GitHub and create a new repository (for example, my-static-site).

Clone it locally, or set your existing project to track this remote.

```
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/my-static-site.git
git push -u origin main 
```

Replace yourusername and my-static-site with your GitHub username and repo name.

2. Add GitHub Actions Workflow:

In your repository, you should find new folder `.github/workflows` and a `static.yml`.

***Note on GitHub Workflow***

I faced some issue when trying to deploy with default workflow.

Turns out some versions of github actions were outdated, here my update working verison of the file.

`static.yml`
```
# Simple workflow for deploying static content to GitHub Pages
name: Deploy static content to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["main"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Single deploy job since we're just deploying
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v4
      - name: GitHub Action for npx
        uses: mikeal/npx@1.0.0
      - name: Run NPM Install
        run: npm install
      - name: Run the static build step
        run: npx @devdojo/static build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          # Upload entire repository
          path: './_site/'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4

```

I added a [pull requst]( https://github.com/static-templates/aria/pull/4) so hopefully someone from devdojo will update this in their templates.


3. Enable GitHub Pages in Your Repository:

Go to your repository’s Settings tab.

Select Pages from the sidebar.

Under Build and deployment, set the source to GitHub Actions. GitHub will use your configured workflow.

4. (Optional) Add a Custom Domain:

To make your website more professional, you can use a custom domain:

Purchase your domain or use one you already own.

Follow the official GitHub documentation to configure your custom domain.




## 🎉 In Conclusion (or Just Getting Started?)
Remember, simplicity doesn't mean sacrificing style or functionality. Sometimes, stripping things down to basics is exactly what's needed to get moving and for me was how I ended up with my blog running.

Sure, this blog post might just be a test run, but it's my test run. And I'm really happy with it. Hopefully soon I will have some more to share.

Stay tuned for more rambling!