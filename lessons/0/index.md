# Hosting a Portfolio with GitHub pages
A start to finish guide on how to create, customize, and host your first portfolio piece on GitHub pages.

## What We'll Cover
- [Create a GitHub account](#create-a-github-account)
- [Create a secret repository](#create-a-secret-repository)
- [Connect to a repository](#connect-to-a-repository)
- [Modify your README](#github)
- [Customize a jekyll theme](#github)

## Create a GitHub Account
This part should be easy since you're already on GitHub. Head to the [sign up page](https://github.com/join)

## Create a Secret Repository
When you use your exact username as the name of your new repo GitHub  will initialize a secret repo that allows you to host a website directly from your profile. Make sure that you meet the following conditions:
- The repo name is the exact same as your username
- You have checked the public box
- You have checked "initialize with a README.md" box
If successful you should see an image similar to below:
![secret repo](secret-repo.jpg)

### Initialize GitHub Pages
On GitHub open your new repo and click the "settings" button. Scroll down to where you see GitHub Pages.
- Enable GitHub Pages
- Use your main branch as the source
- Choose a theme
- Ignore custom domain (for now)

If done properly you should see the following message. Clicking the link will take you to your new live site!
![enable github pages](enable-github-pages.png)

## Connect to a Repository
We're going to connect to our new repo using an SSH connection. In order to do that we need to setup a few things first.