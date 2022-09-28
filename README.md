## How it works
This site is built on a few technologies
- [Hugo](https://gohugo.io/)
- [Markdown](https://guides.github.com/features/mastering-markdown/)
- [GitHub Actions](https://github.com/features/actions)

### Hugo
Hugo is a tool that allows you to use markdown files (files that end with `.md` typically) to build HTML files based on templates.
This is typically used to allow for quick, non-technical building of websites. A base can be setup by someone more technical, and
a user can fill in the content. It is highly flexible, but more complexity means more HTML/JS/CSS knowledge.

### Markdown
Markdown is a "programming language" (more of a templating language) that's easy to write and *kinda* follows basic formatting
you'd see in something like word. Even this [README.md](/README.md) file is build using markdown!

Learn more about the syntax [here](https://guides.github.com/features/mastering-markdown/).

### GitHub Actions
Behind the scenes, whenever you "save" and update these files, an action will be triggered to build the website and publish it.
It takes between 15-30 seconds for it to go live. You can visit [this page](https://github.com/elizabethteas/personal-site/actions)
to see the status. If you see a red X at the top, something has gone wrong while deploying the website.


## What to edit
99% of the editing of your website will be done through either `.md` files for content or `.yaml/.yml` files for config.

### Layout
From this page you're current at ([here](https://github.com/elizabethteas/personal-site)), at the top you should see what looks
like a file and folder structure. You'll see things like `/assets`, `archetypes`, `content`, etc. Let's go through these and
which you'll end up using.

### config/__default
There are two files here worth editing:
- `params.toml` - includes configuration for your profile picture, title, description, and social media links
- `menus.toml` - configure which headers appear at the top
  - `name` tells us which text is displayed on the page
  - `identifier` tells us which file from the `/content` folder we use
  - `url` tells us what the URL will while visiting this page
  - `weight` orders the list

### content
The majority of the content you'll be creating goes here. 

- Collections of similar pages (like blogs) go in a folder
- The `_index.md` file is the default page (in this case, the Home page)
- Each page name corresponds to the `identifier` in the `menus.toml` mentioned above
- Each page is a markdown page, which means its simple editing will be turned into an HTML page when _deployed_
- The content at the top between the `---` is used by Hugo to help set the tab name and provide metadata
  - The `title` and `date` will be the most common used
  - The CV page is special b/c it shows a PDF. It requires the `type` and `doc` to let it know which layout to use
    and which file to use from the `/static/docs` directory
  - **If you're looking to post your website on things like twitter, we can add more things here to help
  render it better**

### static
This folder is used to organize your documents/pdfs, images, and other non-text type material. This is where your profile pic,
CV, and other pics and docs can go.

### Ignore
You can ignore these for now since they're more technical in nature:
- /.github
- /archetypes
- /assets
- /i18n
- /layouts

## How to edit
You can edit most all of this from right inside GitHub!

### Adding a file or directory
From a given directory, at the top right you'll see a button called "Add file" button that will let you either upload existing 
files (useful for images and pdfs) or create new ones (useful for more `.md` files). By adding a slash `/` in the name of the
file, you can create folders, too.
![picture of github showing add file](/.github/images/add-file.png)

### Editing an existing file
Editing a file in GitHub is easy. Navigate to the file you want, and use the pencil button above the contents to edit it. 
![picture of github showing where to edit](/.github/images/edit-file.png)

While making changes, you can click "Preview" to see a _rought_ preview of what the page will end up looking like.
![picture of github showing file preview](/.github/images/preview-file.png)

Finally, when you're done, scroll to the bottom to save. While you don't have to add a title or description to your change, I
would recommend adding one. GitHub keeps track of a list of all changes (and past history) of your site. These are not 
visible on the website, but are visible on GitHub.
![picture of github showing saving](/.github/images/save-file.png)
