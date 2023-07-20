# Docusaurus example

This app was created using `npx create-docusaurus@latest my-website classic`

## Pros

- Easy to use
- Easy to configure
- Easy to add new documentation pages
- Easy to add new categories of documentation
- Easy to add new tags
- Easy to add new blog posts
- DARK MOOOOOOOOOODEEEEEE

## Cons

- It's not really a wiki, it's a documentation app

## How to run

- `npm start`

## What it contains

This app contains a simple example of how we can write our wiki documentation using **Docusaurus**

## How to configure

- `docusaurus.config.js` contains the configuration of the app
- this is the most important part to configure:
```js
themeConfig:
    /** @type {import('@docusaurus/preset-classic').ThemeConfig} */
    ({
      // Replace with your project's social card
      image: 'img/docusaurus-social-card.jpg',
      navbar: {
        title: 'LSAC IT Documentation Wiki',
        logo: {
          alt: 'My Site Logo',
          src: 'img/logo.svg',
        },
        items: [
          {
            type: 'docSidebar',
            sidebarId: 'tutorialSidebar',
            position: 'left',
            label: 'Documentations',
          },
          {
            to: '/blog',
            label: 'Blog',
            position: 'left'
          },
          {
            href: 'https://github.com/LSAC-ONG',
            label: 'GitHub',
            position: 'right',
          },
        ],
      },
      .
      .
      .
```

## How to add:

### Documentation

- If you want to add a new documentation page, you can add it in `docs` folder
- Depending of the quantity, you can add it in a new folder or in an existing one
- For example we created `docs/Poly Olimpycs` which will contatin all the documentation for Poly Olimpycs
- If you want to add a new page, you can add it in `docs/Poly Olimpycs` folder
- You can add a new folder if you want to add a new category of documentation
- For example we created `docs/Poly Olimpycs/backend` which will contain all the documentation for Poly Olimpycs backend
- You can add a new page in `docs/Poly Olimpycs/backend` folder
- You can also just write your documentation in `docs` folder if modularization is not needed, see `docs/Poli Olympics/websockets.md` for example
- Each documentation folder needs a `_category_.json` file which will contain the sidebar configuration
```json
{
    "label": "Poli Olympics",
    "position": 1,
    "link": {
      "type": "generated-index",
      "description": "Documentation for the Poli Olympics 2023 application"
    }
  }
```
- Each documentation page needs to start with this header:
```md
---
sidebar_position: x <!--> x is the position of the page in the sidebar, it's a number, the lower the number, the higher the page will be in the sidebar -->
---

# Main Title
```

### Blog

- If you want to add a new blog post, you can add it in `blog` folder
- You can add a new folder if you want to add a new category of blog posts
- For example we created `blog/2023-07-20-we-have-blogs` which will contains the blog **We have blogs!** which was posted on 20.07.2023
- You can setup authors in `blog/authors.yml`:
```yml
Rares:
  name: Rares Croicia
  title: IT Infra member
  url: https://github.com/RaresCroicia
  image_url: https://github.com/RaresCroicia.png
```
- Your blog post needs to start with this header:
   - `slug` is the url of the blog post
   - `title` is the title of the blog post
   - `authors` is an array of authors, you can add as many as you want
   - `tags` is an array of tags, you can add as many as you want 

```md
---
slug: IT-blog
title: IT Blog
authors: [Rares]
tags: [Wiki, Infra, We love documentation]
---
```

### Screenshots

![Documentation Example](https://imgur.com/a/2hmj07Y)
![Blog Example](https://imgur.com/a/HbhPORx)