#Pages

Pug pages are ultimately compiled into html files. Each page extends the main pug template and contains several optional blocks.

##Extending a Template

Each page extends the main site.pug template as the first command within a pug page. In the case of adding a subfolder of pug pages, make sure to correct the path the extend function looks for. And of course, this also applies when you want to change the extended template.

**Base Level**

```pug
extends ../templates/site.pug
```

**Within 1 Subfolder**

```pug
extends ../../templates/site.pug
```

##Changing the Theme

In some cases there are special treatments that are particular only to a certain type of page. For example, the index.pug page adds a class of mimo-theme which is used as a hook for the mimo-theme.css styles. The theme variable will allow you to change a theme specific class on the html element.

```pug
block theme
  - pageTheme = "homepage"
```

##Injecting Content

In order to add content to your page, there is a content block that is setup by default on each of the two included pages within Mimogear. This content will be nested directly into the main element of your site.

```pug
block content
  p Any pug code can be nested here
```

##Changing the Page's Title and Description

Much like changing the theme per page, there are two variables that also control what the page title and page description are. Changing these values will override the default title and description managed through the package.json.

```pug
block title
  - var title = "A different title"

block description
  - var description = "A different description"
```

##Adding Additional Stylesheets

In the case you would like to add additional stylesheets on a page per page bases, there is an optional block labeled additional-stylesheets at the end of the head region.

```pug
block additional-stylesheets
  link(
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/additional-stylesheet.css"
  )
```

##Adding Additional Scripts

In the case you would like to add additional scripts on a page per page bases, there is an optional block labeled block additional-scripts at the end of the footer region.

```pug
block additional-scripts
  script(src="https://cdnjs.cloudflare.com/ajax/libs/additional-script.js")
```