# Kentoy-StarterKit
A lightweight starter kit for web designers like me.

**What's included:**

1. Bourbon *(sass/0-libraries/bourbon)*: **v4.2.6**
2. Bootstrap *(css/bootstrap.min.css)* & *(js/bootstrap.min.js)*: **v3.3.6**
3. jQuery *(js/jquery.min.js)*: **v1.11.3**
4. Animate.css *(plugins/animate-css)*: **v3.4.0**
5. FontAwesome *(plugins/font-awesome)*: **v3.2.1**

**Guidelines - Setup:**

Clone this repo or download as a ZIP file everytime designs will be implemented, this biolerplate serves as a base template for all designs.

Before implementing designs, make sure that sass is configured properly. Standard configuration include setting the output for **main.sass** to **css/_user-styles.css_**. It is recommended that you rename the output css similar to the project name.

To streamline design coding, make sure to utilize bourbon's preset mixins. Refer to [Bourbon's Documentation](http://bourbon.io/docs/).

**Guidelines - Coding Standards:**

We utilize SASS to keep design codes modular and neat. It is important to understand the SASS structure included in this biolerplate.

**Libraries**

- *0-libraries/bourbon/* : this is where we keep bourbon, mixins and variables.
- *0-libraries/_mixins.sass* : If you need to add mixins, put it here. There is a predefined *breakpoint* mixin should you need to utilize media query styling.
- *0-libraries/_vars.sass* : To avoid inconsistencies with colors, fonts, etc., declare client's specs here. Predefined variables include *$white* and *$black*:
  ```
  $white: #fff
  $black: #000

  // CLIENT FONTS
  $primary-font: sans-serif
  ```

**Base**

- *1-base/base.sass* : this is where we add global styling. Common global styles include declaring fontfamily:
  ```
    body
    font-family: $primary-font
  ```

**Page-specific Styling**

- *2-pages/* : The importance why the SASS folder is structured this way is to keep everything modular. If the need to style specific pages arise, add a sass file with filenames matching the page name:
  ```
    index.sass -- styles for the homepage
    about-us.sass -- styles for the about-us page
    contact.sass -- styles for the contact page
  ```

- *2-pages/_pages.sass* : If there is no need to style specific pages, leave this blank. Otherwise, import the sass files here. always import sass files in order according to which file were created first:
  ```
    @import "index"
    @import "about-us"
    @import "contact"
  ```

**Section-specific Styling**

- *3-sections/* : This is where to put styles for specific sections in specific pages. If it tends to be global, add it to base.sass. The filename should be:
  ```
    index-sidebar.sass
    index-main.sass
    about-us-sidebar.sass
    about-us-main.sass
    ...
    and so on..
  ```
  There is no *_sections-index.sass* file. Instead, import the files in its relative page. That is;
  ```
    index-sidebar.sass --> 2-pages/index.sass
    index-main.sass --> 2-pages/index.sass
    index.sass will contain:
        @import "../3-sections/index-sidebar"
        @import "../3-sections/index-main"
  ```

**Compiling Everything**

If done correctly, main.sass will compile everything to css/user-styles.css.
Make sure to take advantage of the @extend feature of SASS. For more info, check [SASS Documentation](http://sass-lang.com/guide)

**Guidelines - From Development to Production:**

Either delete or comment links and script source that are under 'development'.
Then, uncomment the links and scripts under 'production'.