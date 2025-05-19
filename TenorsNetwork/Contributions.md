---
title: How to Contribute
tags:
  - guide
---
This page explains how properly setup your computer in order to contribute to this website.
## GitHub Account

- First you need a [GitHub](https://github.com/) account to publish your contribution. You can also do this later by following this guide [[Link GitHub]]. However we suggest setting up the account now. 
- In addition, the account allows you to share your material to the GitHub pages  [Tenors Network](https://github.com/tenors-network).

## Clone the project
  
- Open the terminal in the folder where you want download and work on the project.
- Clone the repository `tenors-network.github.io` on your computer, running this following line:
```bash
git clone https://github.com/tenors-network/tenors-network.github.io.git
```

## Set up on local machine

- All pages are written in `Markdown`, a simple format that allows you to include LaTeX formulas, automatically highlight code, and other very useful things. You can find a guide following this [link](https://www.markdownguide.org/basic-syntax/).
 - All pages are located in the directory `TensorNetwork` and can be edited with any markdown editor. Among many editors we suggest [Obsidian](https://obsidian.md/) mainly for the presence of plugins which make easier writing in markdown. 
-  In Obsidian open the folder `TensorNetwork` as vault.

## Review and Publish

- **While** you are writing and before publish your notes, you can create a preview of the website with `build.bat` script inside the project folder. Alternatively, you can run the following line in your terminal.  
```bash
./build.bat
```
- The script creates the website based on your local content and it is available [http://localhost:8080](http://localhost:8080) in your favorite web browser. By clicking the link the website will be opened in your default web browser.
- Once you have finished editing, you may commit the changes by running the following lines in the terminal inside the project folder, replacing `{bash}"<Commit message>"` with a brief description of the changes.  
 ```bash
 git pull
 git commit -am "<Commit message>"
 git push
 ```


