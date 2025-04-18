## Installation:

- install VScode or another IDE that works with quarto (RStudio, Positron)
- install quarto via: https://quarto.org/docs/download/index.html (select the right operating system)
- depending on the IDE you've installed, click on the appropriate logo and follow the [instuctuction](https://quarto.org/docs/get-started/)
- In VScode (and Positron)
  - need to install the [extension for quarto](https://marketplace.visualstudio.com/items?itemName=quarto.quarto) (in VScode 'extensions' tab)
  - need to install the following quarto extension (in your terminal): `quarto add quarto-ext/fontawesome`
 
## Visualisation:

- [Documentation](https://quarto.org/docs/websites/) on building a quarto website
- When you have made some changes, you can execute `quarto preview` in your terminal to preview your changes, it will open a localhost:port that you can view on your favorite web browser. Note that you can also preview your changes directly inside VScode/RStudio, depending on your specific configuration.
  - When in preview mode, your changes are automatically re-rendered when saving the latter (not for all changes, e.g. changes made to `_quarto.yml` but any changes in .qmd files will be re-rendered live). 
- Before deploying your website (i.e. in our case, pushing changes on the git repo), execute `quarto render`
- `_quarto.yml` defines the base structure of the website (current structure: **Home** - **News** - **Teams** - **Projects** - **Activities** - **Publications**)

## Best Practice:

- _Clone_ the project in your terminal: `git clone https://github.com/ECOMOD-RBINS/website.git`
- Create an _issue_ for each modification/addition you want to make
- From your issue, create a new _branch_
- In the terminal, go to your branch: `git checkout your_branch` 
- Make your modifications/additions
- Send your modifications to your branch
  - _`git status`_
  - _`git add modified_files`_ (all your modified/added files **EXCEPT** `docs/...` folder)
  - _`git commit -m 'blablabla'`_
  - _`git push`_ /!\ **DO NOT PUSH `docs/` folder** on your branch, otherwise it will cause annoying conflits to solve between the master branch and yours! /!\
- Create a _`pull request`_ (possible from the github page) to merge your branch into the master
- Wait that the owner accept your pull request and merge your modifications into the website

## Modifications/additions:
_(Please check what is already done on the website and use the same template/structure in your files)_

#### Add a new project:
- Go to `/posts/projects/` 
- Create a new folder with your project's name
- In the folder, create new file called `index.qmd`. This file should starts with some YAML metadata style code (between --- YAML DATA ---). Below this, just write some markdown and you're good to go.
- In the folder, create new folder called `images` to put your project's logo

#### Add a new activity:
- Go to `/posts/activities/` 
- _idem new project_

#### Add some news:
- Go to `news.qmd` 
- Add your news
- Add your images related to news in `/images/news/` 

#### Add description profile page:
- Go to `/posts/members/` 
- Create a new folder with your initials
- In the folder, create new file called `index.qmd`. Put your info in it (inspired FR's or GL's pages).
- Modify your personal section in `team.qmd`to add the link to your personal page: <a href="/posts/members/your_initials"> (inspired FR's)
- In `team.qmd`, you can also modify your email, LinkedIn, Orcid, .. links.
- To modify your profile photo, go to `/images/your_initials`

#### Add a new publication:
- Go to `/publications/articles/` 
- Create new file called `your_article.qmd`. Put your info in it (inspired Lacroix2018.qmd).

#### Modify Home page:
- Go to `index.qmd`

/!\ Never modify anything in `docs/` folder ! It will automatically update with `quarto render`.




