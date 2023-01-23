This is a template for quarto books

# Structure

We have multiple folders here: 

- chapters: Here are the .qmd files that make up the book.
- images: Images, figues and favicon are here.
- data: Save all data used in this book here.
- R: This is the place for r-scripts.
- inst: spell-check file WORDLIST.txt is here. Used to ignore spelling.
- .github/workflows: Hidden folder with CICD pipeline.
- docs: Book gets rendered into this folder, includes pdf as well.
- bib: Both bib files are saved here.
  
  
  
# Instruction

First, create two branches from GitHub: develop and gh-pages.
Work in the develop branch with a pending merge request to main.
Then, change the _quarto.yml file so that the project data -- author, title -- is correct.
Create a new favicon, [for example online](https://favicon.io/favicon-generator/). 
Write new chapters in the `chapters` folder and add them to _quarto.yml accordingly. 
Note that because we specified `execute-dir: project` in _quarto.yml, the current working directory is at the project level. 
This is independent of where the file that is being executed is located. 
Say: If we are working in a chapter in the `chapters` folder and want to access the data, we can directly use the path: "data/nameofdata", so we don't have to go back to the parent directory first.
You create packages.bib with the RScript `generateReferences.R`, you just have to add packages.

## rendern
Render the book with the terminal command:

`quarto render`


Use

`quarto preview`

to preview the book while you edit.


## Spellcheck
We have set up a GitHub workflow for a German Spell-Check. 
This will be executed automatically when a pull request is made to the main branch. 
For this we need the WORDLIST.txt file in the `inst` folder.
We can define words in the WORDLIST.txt file which should be ignored in the spell-check. 
In the folder R there is a R-Script `CICD.R` with which we can adjust the WORDLIST.txt.


## Stylecheck
In the R folder there is an R script `CICD.R`. 
With this we can do the style check before we merge with main.
In the `CICD.R` file you can check whether files need restyling.

## Publish
When merging with main, the book is automatically re-rendered to the github branch `gh-pages`. 
