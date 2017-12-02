<!-- README.md is generated from README.Rmd. Please edit that file -->
    ## 
    ## Attaching package: 'dplyr'

    ## The following object is masked from 'package:rsam':
    ## 
    ##     %>%

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

RStudio Addin Manager
=====================

`{rsam}` provides a command line and user interface to manage RStudio addins.

Installation
------------

``` r
remotes::install_github('yonicd/rsam')
```

UI
--

``` r
library(rsam)

rsam()
```

[![rsam usage](http://img.youtube.com/vi/-XZWv7CJrs8/0.jpg)](https://www.youtube.com/watch?v=-XZWv7CJrs8)

CLI
---

### Retrieve Summary of Installed Addins

``` r
fetch_addins()
```

| Package       | Name                             | Binding             | Interactive | Key                             | Shortcut         |
|:--------------|:---------------------------------|:--------------------|:------------|:--------------------------------|:-----------------|
| blogdown      | Serve Site                       | serve\_site         | true        | blogdown::serve\_site           |                  |
| blogdown      | New Post                         | new\_post\_addin    | true        | blogdown::new\_post\_addin      |                  |
| blogdown      | Update Metadata                  | update\_meta\_addin | true        | blogdown::update\_meta\_addin   |                  |
| bookdown      | Preview Book                     | serve\_book         | true        | bookdown::serve\_book           |                  |
| bookdown      | Input LaTeX Math                 | mathquill           | true        | bookdown::mathquill             |                  |
| chunky        | chunky                           | chunkify            | false       | chunky::chunkify                | Ctrl+Shift+J     |
| clipr         | Value to clipboard               | clipr\_result       | false       | clipr::clipr\_result            |                  |
| clipr         | Output to clipboard              | clipr\_output       | false       | clipr::clipr\_output            |                  |
| colourpicker  | Plot Colour Helper               | plotHelperAddin     | true        | colourpicker::plotHelperAddin   |                  |
| colourpicker  | Colour Picker                    | colourPickerAddin   | true        | colourpicker::colourPickerAddin |                  |
| covr          | Calculate package test coverage  | addin\_report       | false       | covr::addin\_report             |                  |
| cronR         | Schedule R scripts on Linux/Unix | cron\_rstudioaddin  | true        | cronR::cron\_rstudioaddin       |                  |
| ggedit        | ggedit                           | ggeditAddin         | true        | ggedit::ggeditAddin             |                  |
| remedy        | Backtick                         | backtickr           | false       | remedy::backtickr               | Ctrl+Cmd+\`      |
| remedy        | Bold                             | boldr               | false       | remedy::boldr                   | Ctrl+Cmd+B       |
| remedy        | Chunk                            | chunkr              | false       | remedy::chunkr                  | Ctrl+Alt+Cmd+C   |
| remedy        | Chunksplit                       | chunksplitr         | false       | remedy::chunksplitr             | Ctrl+Shift+Alt+C |
| remedy        | H1                               | h1r                 | false       | remedy::h1r                     | Ctrl+Cmd+1       |
| remedy        | H2                               | h2r                 | false       | remedy::h2r                     | Ctrl+Cmd+2       |
| remedy        | H3                               | h3r                 | false       | remedy::h3r                     | Ctrl+Cmd+3       |
| remedy        | H4                               | h4r                 | false       | remedy::h4r                     | Ctrl+Cmd+4       |
| remedy        | H5                               | h5r                 | false       | remedy::h5r                     | Ctrl+Cmd+5       |
| remedy        | H6                               | h6r                 | false       | remedy::h6r                     | Ctrl+Cmd+6       |
| remedy        | Image                            | imager              | false       | remedy::imager                  | Ctrl+Cmd+P       |
| remedy        | Italics                          | italicsr            | false       | remedy::italicsr                | Ctrl+Cmd+I       |
| remedy        | LaTeX                            | latexr              | false       | remedy::latexr                  | Ctrl+Cmd+L       |
| remedy        | List                             | listr               | false       | remedy::listr                   | Ctrl+Shift+Cmd+= |
| remedy        | Right                            | rightr              | false       | remedy::rightr                  | Alt+Cmd+Right    |
| remedy        | Strike                           | striker             | false       | remedy::striker                 | Ctrl+Cmd+S       |
| remedy        | Table                            | tabler              | false       | remedy::tabler                  | Ctrl+Cmd+T       |
| remedy        | Url                              | urlr                | false       | remedy::urlr                    | Ctrl+Cmd+U       |
| remedy        | Xaringan                         | xaringanr           | false       | remedy::xaringanr               | Ctrl+Cmd+X       |
| remedy        | Youtube                          | youtuber            | false       | remedy::youtuber                | Ctrl+Cmd+Y       |
| reprex        | Render reprex                    | reprex\_addin       | true        | reprex::reprex\_addin           |                  |
| rhandsontable | Edit a Data Frame                | editAddin           | true        | rhandsontable::editAddin        |                  |
| rsam          | lla                              | lla                 | TRUE        | rsam::lla                       | Command+Shift+L  |
| shinyjs       | Colour Picker                    | colourPickerAddin   | true        | shinyjs::colourPickerAddin      |                  |
| sinew         | createOxygen                     | oxygenAddin         | false       | sinew::oxygenAddin              |                  |
| sinew         | interactiveOxygen                | interOxyAddIn       | true        | sinew::interOxyAddIn            |                  |
| styler        | Style package                    | style\_pkg          | true        | styler::style\_pkg              |                  |
| styler        | Style active file                | style\_active\_file | true        | styler::style\_active\_file     |                  |
| styler        | Style selection                  | style\_selection    | true        | styler::style\_selection        |                  |
| texPreview    | texPreview                       | texAddin            | false       | texPreview::texAddin            |                  |
| vcs           | alexa                            | alexa               | true        | vcs::alexa                      |                  |

### Set Keyboard Shortcut for Addins

``` r
set_shortcut(fn = 'blogdown::serve_site',shortcut = 'Command+Shift+I')

#if the binding already has a shortcut mapped to it `overide` must be TRUE
set_shortcut(fn = 'blogdown::serve_site',shortcut = 'Command+Shift+I',overide = TRUE)
```

### Toggle Addins on/off

Every time a binding is passed to the `toggle_addin` function it will switch states.

``` r
toggle_addin(key = c("blogdown::serve_site","blogdown::new_post_addin","blogdown::update_meta_addin"))
```

### Limited Liability Addin

Pass through an expression wrapped the global object rsam\_fn() into the Rstudio Addin list

``` r

rsam_fn <- function(){
  library(ggplot2)
  library(dplyr)
  
  iris%>%ggplot(aes(x=Sepal.Length,y=Sepal.Width)) + geom_point()
}

# Change shortcut to whatever you want
rsam::set_shortcut(fn = 'rsam::lla',shortcut = 'Command+Shift+L')
```

Feedbacks and enhancement
-------------------------

You've found a bug, or have an enhancment idea? Feel free to open an issue : <https://github.com/yonicd/rsam/issues>.
