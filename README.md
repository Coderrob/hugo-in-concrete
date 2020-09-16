# Hugo In Concrete

_Currently a Work-in-Progress_

This page tells you how to get started with the Concrete theme.

<a href="https://www.buymeacoffee.com/coderrob" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-green.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

## Setting up a new site

To prepare your new site environment just a few steps are required:

1. Create a new empty Hugo site.

   ```Shell
   hugo new site demosite
   ```

1. Change the directory to the root of the new site.

   ```Shell
   cd demosite
   ```

1. Create a new theme folder

   ```Shell
   mkdir themes
   ```

## Get the Concrete theme

From the site root either clone or add the Concrete repository as a new submodule.

   ```Shell
   # Cloning
   git clone https://github.com/coderrob/hugo-in-concrete themes/concrete

   # Submodule
   git submodule add https://github.com/coderrob/hugo-in-concrete themes/concrete
   ```

## Preview the Concrete theme

   ```Shell
   cd themes/concrete/exampleSite/
   hugo serve --themesDir ../..
   ```

## Concrete configuration

1. Add the Concrete theme to the site `config.toml`.

   ```Toml
   baseURL = "http://example.org/"
   languageCode = "en-us"
   title = "My New Hugo Site"

   # Set the theme to Concrete
   theme = "concrete"
   ```

1. Configure the site navigation.

   ```Toml
   # Add the site navigation links
   [menu]

   [[menu.main]]
   name = "Home"
   url = "/"
   weight = 1

   [[menu.main]]
   name = "Blog"
   url = "/posts/"
   weight = 2
   ```

1. Configure the syntax highlighting to use Github shortcodes.

   ```Toml
   # Required for using the Github style syntax
   [markup]
   defaultMarkdownHandler = "goldmark"

   [markup.goldmark]

   [markup.goldmark.extensions]
   definitionList = true
   footnote = true
   linkify = true
   strikethrough = true
   table = true
   taskList = true
   typographer = true

   [markup.goldmark.parser]
   attribute = true
   autoHeadingID = true

   [markup.goldmark.renderer]
   hardWraps = false
   unsafe = true
   xHTML = false

   [markup.highlight]
   codeFences = true
   hl_Lines = ""
   lineNoStart = 1
   lineNos = false
   lineNumbersInTable = true
   noClasses = true
   style = "github"
   tabWidth = 4

   [markup.tableOfContents]
   endLevel = 6
   startLevel = 2
   ```

## Test your site

1. Test your site.

   ```Shell
   hugo server --theme concrete -D
   ```
