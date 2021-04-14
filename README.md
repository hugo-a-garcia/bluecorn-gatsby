<h1 align="center">
  Minimal Gatsby Site and Core Blog
</h1>

This project is built with the minimal set of depencies for creating a Gatsby based site with a blog. The two major components are:

- Gatsby minimal stater
- Gatsby blog core theme

## Recipe

###

1. Create a Github repository

2. Use the Gatsby CLI to create a new site, specifying the minimal starter.

   ```shell
   # create a new Gatsby site using the minimal starter
   npm init gatsby
   ```

3. Navigate into your new site’s directory and start it up.

   ```shell
   cd my-gatsby-site/
   ```

4. Add the site to the remote repository in github.

   ```shell
   git remote add origin <git url of your repository>
   ```

5. Push the site to the repo.

   ```shell
   git push -u origin master`
   ```

6. Install the theme

   ```shell
   npm install gatsby-theme-blog-core --legacy-peer-deps
   ```

7. Install required dependencies

   ```shell
   npm install --save-dev @mdx-js/react
   npm install gatsby-image
   ```

8. Add the configuration to your `gatsby-config.js` file

   ```js
   // gatsby-config.js
   module.exports = {
     siteMetadata: {
       // Used for the site title and SEO
       title: `My Blog Title`,
       // Used to provide alt text for your avatar
       author: `My Name`,
       // Used for SEO
       description: `My site description...`,
       // Used for resolving images in social cards
       siteUrl: `https://example.com`,
       // Used for social links in the root footer
       social: [
         {
           name: `Twitter`,
           url: `https://twitter.com/gatsbyjs`,
         },
         {
           name: `GitHub`,
           url: `https://github.com/gatsbyjs`,
         },
       ],
     },
     plugins: [
       {
         resolve: `gatsby-theme-blog-core`,
         options: {
           // basePath defaults to `/`
           basePath: `/blog`,
         },
       },
     ],
   };
   ```

9. Start the development server

   ```shell
   gatsby develop
   ```
10. Add a post in the directory `content/posts` with the filename `hello-world.md`

    ```md
    ---
    title: Hello World
    date: 2021-04-15
    ---
    ```

11. Open http://localhost:8000/blog

12. Success! Happy Hacking :)
---
# Reference:

## 1. Youtube video presented by Laurie Barth:
Build a site with the new Blog Theme 2.0 and explore all the new features and functionality. 
[Gatsby Tutorial: Exploring Blog Theme 2.0](https://www.youtube.com/watch?v=Ycnso8BqEyc)

## 2. Minimal Starter:

<p align="center">
  <a href="https://www.gatsbyjs.com/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter">
    <img alt="Gatsby" src="https://www.gatsbyjs.com/Gatsby-Monogram.svg" width="60" />
  </a>
</p>
<h1 align="center">
  Gatsby minimal starter
</h1>

## 🚀 Quick start

1.  **Create a Gatsby site.**

    Use the Gatsby CLI to create a new site, specifying the minimal starter.

    ```shell
    # create a new Gatsby site using the minimal starter
    npm init gatsby
    ```

2.  **Start developing.**

    Navigate into your new site’s directory and start it up.

    ```shell
    cd my-gatsby-site/
    npm run develop
    ```

3.  **Open the code and start customizing!**

    Your site is now running at http://localhost:8000!

    Edit `src/pages/index.js` to see your site update in real-time!

4.  **Learn more**

    - [Documentation](https://www.gatsbyjs.com/docs/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Tutorials](https://www.gatsbyjs.com/tutorial/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Guides](https://www.gatsbyjs.com/tutorial/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [API Reference](https://www.gatsbyjs.com/docs/api-reference/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Plugin Library](https://www.gatsbyjs.com/plugins?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)

    - [Cheat Sheet](https://www.gatsbyjs.com/docs/cheat-sheet/?utm_source=starter&utm_medium=readme&utm_campaign=minimal-starter)


## 3. Blog core theme:

<p align="center">
  <a href="https://www.gatsbyjs.com">
    <img alt="Gatsby" src="https://www.gatsbyjs.com/Gatsby-Monogram.svg" width="60" />
  </a>
</p>
<h1 align="center">
  The Gatsby blog core theme
</h1>

A Gatsby theme for creating a blog child theme. It includes all of the data structures you need to get up and running building a blog and includes no additional theming or style opinions.

## Installation

### For a new site

If you're creating a new site and want to use the blog theme, you can use the blog theme starter. This will generate a new site that pre-configures use of the blog theme.

```shell
gatsby new my-themed-blog https://github.com/gatsbyjs/gatsby-starter-blog-theme-core
```

### For an existing site

1. Install the theme

```shell
npm install gatsby-theme-blog-core
```

2. Add the configuration to your `gatsby-config.js` file

```js
// gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-theme-blog-core`,
      options: {
        // basePath defaults to `/`
        basePath: `/blog`,
      },
    },
  ],
}
```

3. Add blog posts to your site by creating `md` or `mdx` files inside `/content/posts`.

   > Note that if you've changed the default `contentPath` in the configuration, you'll want to add your markdown files in the directory specified by that path.

4. Run your site using `gatsby develop` and navigate to your blog posts. If you used the above configuration, your URL will be `http://localhost:8000/blog`

## Usage

### Theme options

| Key                      | Default value    | Description                                                                                                 |
| ------------------------ | ---------------- | ----------------------------------------------------------------------------------------------------------- |
| `basePath`               | `/`              | Root url for all blog posts                                                                                 |
| `contentPath`            | `content/posts`  | Location of blog posts                                                                                      |
| `assetPath`              | `content/assets` | Location of assets                                                                                          |
| `mdxOtherwiseConfigured` | `false`          | Set this flag `true` if `gatsby-plugin-mdx` is already configured for your site.                            |
| `excerptLength`          | `140`            | Length of the auto-generated excerpt of a blog post                                                         |
| `imageMaxWidth`          | `1380`           | Set the max width of images in your blog posts. This applies to your featured image in frontmatter as well. |
| `filter`                 | `{}`             | Set the posts filter, for example: `{ frontmatter: { draft: {ne: true} } }`                                 |
| `limit`                  | `1000`           | Set the amount of pages that should be generated                                                            |

#### Example usage

```js
// gatsby-config.js
module.exports = {
  plugins: [
    {
      resolve: `gatsby-theme-blog-core`,
      options: {
        // basePath defaults to `/`
        basePath: `/blog`,
      },
    },
  ],
}
```

### Additional configuration

In addition to the theme options, there are a handful of items you can customize via the `siteMetadata` object in your site's `gatsby-config.js`

```js
// gatsby-config.js
module.exports = {
  siteMetadata: {
    // Used for the site title and SEO
    title: `My Blog Title`,
    // Used to provide alt text for your avatar
    author: `My Name`,
    // Used for SEO
    description: `My site description...`,
    // Used for resolving images in social cards
    siteUrl: `https://example.com`,
    // Used for social links in the root footer
    social: [
      {
        name: `Twitter`,
        url: `https://twitter.com/gatsbyjs`,
      },
      {
        name: `GitHub`,
        url: `https://github.com/gatsbyjs`,
      },
    ],
  },
}
```

### Blog Post Fields

The following are the defined blog post fields based on the node interface in the schema

| Field       | Type     |
| ----------- | -------- |
| id          | String   |
| title       | String   |
| body        | String   |
| slug        | String   |
| date        | Date     |
| tags        | String[] |
| excerpt     | String   |
| image       | String   |
| imageAlt    | String   |
| socialImage | String   |

## Available components and styling

There are some existing components that you can import and use. Reference the full path to do so, e.g. `gatsby-blog-theme-core/src/components/post`.

Also note that there are classNames on elements in these components allowing you to target them with styles.
