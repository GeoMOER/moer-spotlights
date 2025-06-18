---
title: R packages on OPSI PCs
header:
  image: "/assets/images/teaserimages/ai.png"
  caption: '[Marco Verch via ccnull.de](https://ccnull.de/foto/kuenstliche-intelligenz-bei-der-arbeit/1095606). [CC-BY 2.0](https://creativecommons.org/licenses/by/2.0/de/). Image cropped.'
toc: true
---

<!--more-->
### Install R packages on OPSI PCs in your own account

Required: University computer and account
Target: R environment in the university user account, regardless of the university computer currently in use


1. Ask R where it currently installs and searches for packages:
```r
.libPaths() # First entry by default on C:/something -> not in the H: drive and therefore not in the Acount but locally on the computer.
```

2. Create your own R package folder on H: (creating once is sufficient):
```r
mypath <- "H:/R/win-library"
dir.create(mypath, recursive = TRUE, showWarnings = TRUE)
```

3. Set up R permanently in such a way that packages are installed and loaded there by making an entry in the .Rprofile file
Create (or edit) a file with the name .Rprofile in the home directory (H:/Documents/.Rprofile) with the following content:
```r
.libPaths("H:/R/win-library")
```
If you already have an .Rprofile, add this line without deleting any other content.
If you do not write this line in .Rprofile and/or the .Rprofile file is in the “wrong” place, the setting will be lost every time R is restarted.


4. check: Should now show H:/R/win-library in the first position, even after restarts and also on other computers.
```r
.libPaths()
```

### Install packages in general

Classic via CRAN
```r
?install.packages()
```

Latest development versions (often unstable) via GitHub
```r
?devtools::install_github()
```

Previous versions
```r
?remotes::install_version()
```



### RTools installation

Why? Necessary if packages do not have to be installed via CRAN, e.g. via `devtools::install_github()`

Download the appropriate RTools version from [https://cran.r-project.org/bin/windows/Rtools/](https://cran.r-project.org/bin/windows/Rtools/)
Appropriate means matching the R version. The R version appears at the top of the console when you open Rstudio, e.g. 4.4.3 (-> then select Rtools 4.4)

Installation in the folder suggested by Rtools (C:/) is possible, but is then only available on the local computer. Then it has to be executed once on each university computer














