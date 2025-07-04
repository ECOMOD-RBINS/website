## Installation

- Install VScode or another IDE that works with quarto (RStudio, Positron)
- Install [Quarto](https://quarto.org/docs/download/index.html)
- Depending on the IDE you have installed, click on the appropriate logo and follow the [instructions](https://quarto.org/docs/get-started/)
- In VScode (and Positron)
  - need to install the [extension for quarto](https://marketplace.visualstudio.com/items?itemName=quarto.quarto) (in VScode 'extensions' tab)
  - need to install the following quarto extension (in your terminal): `quarto add quarto-ext/fontawesome`
 
## Visualization

- [Documentation](https://quarto.org/docs/websites/) on building a quarto website
- When you have made some changes, you can execute `quarto preview` in your terminal to preview your changes, it will open a localhost:port that you can view on your favorite web browser. Note that you can also preview your changes directly inside VScode/RStudio, depending on your specific configuration.
  - When in preview mode, your changes are automatically re-rendered when saving the latter (not for all changes, e.g. changes made to `_quarto.yml` but any changes in .qmd files will be re-rendered live). 
- Before deploying your website (i.e. in our case, pushing changes on the git repo), execute `quarto render`
- `_quarto.yml` defines the structure of the website

## Best practices

- Clone the project in your terminal: `git clone https://github.com/ECOMOD-RBINS/website.git`
- Create an issue for each modification/addition you want to make
- From your issue, create a new branch
- In the terminal, fetch updates (i.e. your new branch) from the remote (i.e. the remote repository) with: `git fetch origin`. Git fetch downloads changes from the remote repository to your local repository, but it doesn't automatically merge these changes into your working files. It simply retrieves the data and updates your remote-tracking branches while `git pull` is basically a `git fetch` followed by a `git merge`, it downloads changes from the remote repository and immediately tries to merge them into your current branch.
- In the terminal, go to your branch: `git checkout your_branch`
- To check whether or not the master is up to date
(in case there have been any changes since the new branch was created that could potentially create conflicts)
	1. From master branch: git pull
	2. If the status is up-to-date, OK. If not, switch to the new branch and merge the updated master: git merge master
- Make your modifications/additions
- Send your modifications to your branch
  - `git status`
  - `git add modified_files` (add all your modified/added files **EXCEPT** `docs/` folder)
  - `git commit -m 'blablabla'`
  - `git push` /!\ **DO NOT PUSH `docs/` folder** on your branch, otherwise it will cause annoying conflits to solve between the master branch and yours!
- Create a `pull request` (possible from the github page) to _merge_ your branch into the master
- Wait that the owner accept your pull request and merge your modifications into the website

## Modifications and/or additions
Please check what has already been done on the website and use the same template/structure in your files.

### Add a new project
- Go to `/projects/` 
- Create a new folder with the name of your project
- In the folder, create a new file called `index.qmd`. This file should start with a snipped of YAML code (between --- YAML DATA ---). Below this, just write some markdown and you are good to go.
- In the folder, create a new folder called `images` to put the logo of your project or any images or figures you would like to share.
- If you project is incomplete and you still need to work a bit on it before it is published online, you can add the keyword `draft: true` in the YAML header of your project file.
- Once a project is over, the project folder needs to be moved into `completed-projects`

### Add a new activity
- Go to `/activities/` 
- Follow the same instructions as for new projects

### Add some news
- Go to `news.qmd` 
- Add your news
- Add your images related to news in `/images/news/` 

### Add a description profile page
- Go to `/posts/members/` 
- Create a new folder with your initials
- In the folder, create a new file called `index.qmd`. Put your info in it.
- Modify your personal section in `team.qmd`to add the link to your personal page: <a href="/posts/members/your_initials">
- In `team.qmd`, you can also modify your email, LinkedIn, Orcid,... links.
- To modify your profile photo, go to `/images/your_initials`

### Add a new publication
- Go to `/publications/articles/` 
- Create a new file called `your_article.qmd`. Put your info in it (e.g. Lacroix2018.qmd).

### Modify the main (home) page
- Go to `index.qmd`

/!\ Never modify anything in the `docs/` folder ! It will automatically be updated with `quarto render`. 




