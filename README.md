Needed:

- VScode or another IDE that works with quarto (RStudio, Positron), that needs to be [installed](https://quarto.org/docs/download/index.html) first
- In VScode (and Positron), you need to install the [extension for quarto](https://marketplace.visualstudio.com/items?itemName=quarto.quarto)
- need to install the following quarto extension (in your terminal):
  - `quarto add quarto-ext/fontawesome`
 
How to (needs to be improved...)

- [Documentation](https://quarto.org/docs/websites/) on building a quarto website
- `_quarto.yml` defines the base structure of the website.
- When you have made some changes, you can execute `quarto preview` in your terminal to preview your changes, it will open a localhost:port that you can view on your favorite web browser. Note that you can also preview your changes directly inside VScode, depending on your specific configuration.
  - When in preview mode, your changes are automatically re-rendered when saving the latter (not for all changes, e.g. changes made to `_quarto.yml` but any changes in .qmd files will be re-rendered live). 
- Before deploying your website (i.e. in our case, pushing changes on the git repo), execute `quarto render`

##### Add a new project

Go to `/posts/projects/` and create a new folder with a file called `index.qmd`. This file should starts with some YAML metadata style code (between --- YAML DATA ---). Below this, just write some markdown and you're good to go.

##### Add a new activities

Same thing as for the project section but in `posts/activities`

##### When you push on the repo

/!\ For information /!\ DO NOT PUSH YOUR `docs/` folder on your branch, otherwise it will cause annoying conflits to solve between the master branch and yours.
In order for the website to run, we need the HTML code so the `docs` folder needs to be pushed (will be updated after rendering) as well as your local changes.
