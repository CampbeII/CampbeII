# Hosting a Portfolio with GitHub Pages
A start to finish guide on how to create, customize, and host your first portfolio piece on GitHub pages.

## What We'll Cover
- [Create a GitHub account](#0-create-a-github-account)
- [Create a secret repository](#1-create-a-secret-repository)
- [Initialize GitHub pages](#2-initialize-github-pages)
- [Connect to a repository](#3-connect-to-a-repository)
- [Clone the repository](#3-clone-the-repository)
- [Customize a jekyll theme](#github)

## 0. Create a GitHub Account
This part should be easy since you're already on GitHub. Head to the [sign up page](https://github.com/join)
Take some time to dig into your settings you can change the theme, your picture, and more.

## 1. Create a Secret Repository
When you use your exact username as the name of your new repo GitHub  will initialize a secret repo that allows you to host a website directly from your profile. Make sure that you meet the following conditions:
- [x] The repo name is the exact same as your username
- [x] You have checked the public box
- [x] You have checked "initialize with a README.md" box

If successful you should see an image similar to below:
![secret repo](images/secret-repo.png)

### 2. Initialize GitHub Pages
On GitHub open your new repo and click the "settings" button. Scroll down to where you see GitHub Pages.
- [x] Enable GitHub Pages
- [x] Use your main branch as the source
- [x] Choose a theme
- [x] Ignore custom domain (for now)

If done properly you should see the following message. Clicking the link will take you to your new live site!
![enable github pages](images/enable-github-pages.png)

## 3. Connect to a Repository
Nothing beats the [GitHub Documentation](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh). Head there to find the instructions for your operating system. If you aren't familiar with the command line, I recommend you download [GitHub desktop](https://desktop.github.com/) as it handles the connection for you.

## 4. Clone the Repository
This command will create a new directory on your computer using the same name as the repository.

```shell
git clone git@github.com:username/username.git
```

Sweet! Okay, we should now have the following files in our directory:

```shell
ls
README.md
_config.yml
```
**README.md**
This is a markdown file. It uses GitHubs' modified markdown syntax which you can read more about [here](https://docs.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax).

A README.md will be the first thing someone sees when they visit your repo. However this is a __special__ README.md file because it will show up on your profile page for everyone to see!

**_config.yml**
This is a [YAML](https://docs.ansible.com/ansible/latest/reference_appendices/YAMLSyntax.html) file. It is used to configure our theme. When you change your theme in your settings, the change will be applied here.

## 5. Customizing Your Website
View your website by visiting the link specified in your settings under GitHub Pages. It typically looks like:
```shell
https://username.github.io/username
```
The first thing you will notice is that your website contains the contents of your `README.md` file along with some other automatically generated content. In order to change the look of this page we will need to add some files to our project.

Visit the repository of your chosen theme. You can find a list of themes [here](https://pages.github.com/themes/)

In the theme repo we are going to want to copy the following files & structure exactly:

- `_layouts/default.html`
- `assets/css/styles.scss`

To quickly copy the contents of the `default.html` and `styles.scss` files you can click the "Raw" button when viewing the file.
![raw copy](images/raw.png)

**Remove what you don't need**
I want to create a completely custom design, but keep all the essential template variables. I will remove all content within the `<header>`, `<main>`,  and `<footer>` elements.

