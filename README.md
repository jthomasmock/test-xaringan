
# test-xaringan

<!-- badges: start -->
<!-- badges: end -->

The goal of test-xaringan is to test `xaringan` presentation to RStudio Connect.

```{r}
library(rsconnect)

# option 1, send rendered doc alone
deployDoc("test-xaringan.html",
          appName = "themed-xaringan",
          appTitle = "A cool themed slide deck",
          server = "colorado.rstudio.com")

# option 2, send rendered doc alone, replace existing file
deployDoc("test-xaringan.html",
          server = "colorado.rstudio.com",
          appId = "4b9ec25-9264-4ade-ba39-639bcd1dcc50")

# option 3, send source file and specify files
# with rmarkdown::find_external_resources
# note new url, since I want this to include source version as
# opposed to the original which was only the output HTML/css

rsconnect::deployDoc("test-xaringan-sourced.Rmd",
          server = "colorado.rstudio.com",
          appName = "themed-xaringan-sourced",
          appTitle = "A cool themed slide deck, but rendered on Connect",
          )


```
