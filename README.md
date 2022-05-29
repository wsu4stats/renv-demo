# `renv` demonstration

If a collaborator has already setup an renv environment for the project, 
you can leverage this to ensure you use the dependencies, 
and versions of those dependencies, as your collaborator 🙌

### Let's try it out!

#### Exercise 1 -  Using a project where `renv` is already setup

1. Click the green "Use this template" button 
in [this repository](https://github.com/ttimbers/renv-demo) 
to obtain a copy of it for yourself.

2. Clone this repository to your computer.

3. Open RStudio to the project working directory 
by double-clicking on the `*.Rproj` file.

4. Run `renv::restore()` to restore the project library locally on your machine.

5. Click the "Knit" button to run the code and reproduce the analysis!


#### Exercise 2 - Updating an `renv` environment

A common task you will need to do when you collaborate is to update an renv environment as you add dependencies to your project. Let's try that now as well!

1. Install the [`statquotes`](https://github.com/friendly/statquotes) R package via: `install.packages("statquotes")`

2. Add the following code to the code chunk on line 16 of `star-wars.Rmd`

```
library(statquotes)
as.markdown(search_quotes("environment"))
```

3. Call `renv::snapshot()` to save the state of the project library 
to the lockfile (called `renv.lock`).

4. Examine the `renv.lock` file. 
You should see something like this near line 381 of the `renv.lock` file:

```
"statquotes": {
      "Package": "statquotes",
      "Version": "0.2.6",
      "Source": "Repository",
      "Repository": "CRAN",
      "Hash": "d771dc735b1829ff511855197fc4c107",
      "Requirements": [
        "stringr",
        "tidytext",
        "wordcloud"
      ]
    },
```
5. To share the changes to the environment, commit the changes to the `renv.lockfile` and push them to your remote version control repository.

## License

Software licensed under the [MIT License](https://spdx.org/licenses/MIT.html), 
non-software content licensed under the 
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0) License](https://creativecommons.org/licenses/by-nc-sa/4.0/). 
See the [license file](LICENSE.md) for more information.
