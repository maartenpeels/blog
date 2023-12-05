---
title: "Building a Hugo Blog with Lowkey Theme: Host on GitHub Pages for Free"
date: 2023-12-05T14:38:16+01:00
draft: false
---

## Overview
This guide will walk you through the steps to set up a blog using Hugo, the popular static site generator, and the Lowkey theme. The blog will be hosted on GitHub Pages.

### Prerequisites
- Basic understanding of Git and GitHub
- Familiarity with the command line interface
- Hugo installed on your local machine
- GitHub account

## Steps

### Step 1: Install Hugo 🌐
If you haven't installed Hugo yet, visit [Hugo's official website](https://gohugo.io/getting-started/installing/) for installation instructions specific to your operating system.

### Step 2: Create a New Site 🏗️
Use the following command to create a new Hugo site:

```bash
hugo new site myblog
```

Replace `myblog` with your desired blog name.

### Step 3: Install (Lowkey) Theme 🎨
Navigate to your Hugo site's directory and add the Lowkey theme repository as a submodule(or clone if you plan to edit it):

```bash
git submodule add https://github.com/nixentric/Lowkey-Hugo-Theme.git themes/lowkey
```

For other themes, you can have a look at the [Hugo Themes: Complete List](https://themes.gohugo.io/).

### Step 4: Configure the Theme ⚙️
Copy the example `config.toml` or `config.yaml` file from the installed theme to your site's root directory and configure it based on your preferences and needs.

### Step 5: Create Content 📝
Use Hugo's command-line interface to create new content for your blog:

```bash
hugo new content posts/first-post.md
```

This command creates a new Markdown file for your first blog post under the `content/posts/` directory. The template can be edited under `archetypes/default.md`.

### Step 6: Customize and Edit Content ✏️
Edit the Markdown files in your preferred text editor. Use Hugo's templating syntax to customize layouts, add images, and format your content.

### Step 7: Test Locally 🖥️
Run Hugo's local server to test your site:

```bash
hugo server -D
```

`-D` is to also show the posts that are in draft state.

Visit `http://localhost:1313/` in your web browser to preview your blog.

### Step 8: Set Up the GitHub Repository 🗃️
Create a new GitHub repository for your blog. Push your Hugo site files to the repository.

### Step 9: Enable GitHub Pages / Workflow 🔄
Follow [this](https://gohugo.io/hosting-and-deployment/hosting-on-github/) guide starting at `Step 3` to set up GitHub pages and automatically build/deploy your blog.


### Step 11: Visit Your Blog 👀
After GitHub Actions has built/deployed your site, your blog will be live at `https://your-username.github.io/your-repo-name`

### Step 12: Add Custom Domain (Optional) 🌐
Follow the guide [here](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages) to add a custom domain to your blog.

### Conclusion 🎉
Congratulations! You've successfully set up a blog using Hugo with the Lowkey(or other) theme and hosted it on GitHub Pages. Continue to create engaging content and explore further customization options to make your blog unique.

Happy blogging! 🚀