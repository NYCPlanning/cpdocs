
#Capital Planning Docs Site: 

http://docs.capitalplanning.nyc/

#How to use:

1. Install mkdocs on your computer with `brew install mkdocs`
2. Clone repo
3. To create a new page for a data product, add a new .md file inside the `docs` folder. (To edit an exisiting page, just edit the existing .md file and then skip to Step 4.)
4. To add your newly created page to the index of the site, add the title of the new page and the .md file name as a bullet point inside the `mkdocs.yml` file. 
5. Test your edits live on your own served page using the command `mkdocs serve`.
6. After testing the edits, **push the changes to the GitHub master origin** repo.
7. Finally, deploy the updates to the public site using the command `mkdocs gh-deploy`.

#Guide from MkDocs:

http://www.mkdocs.org/user-guide/deploying-your-docs/
