---
title: How to Contribute
tags:
  - guide
---
This page explains how properly setup your computer in order to contribute to this website.
## GitHub Account

- First you need a [GitHub](https://github.com/) account to publish your contribution. You can also do this later by following this guide [[Link GitHub]]. However we suggest setting up the account now. 
- In addition, the account allows you to share your material to the GitHub pages  [Tenors Network](https://github.com/tenors-network).

## Setup


- The rest of this guide is designed for people that have already created the account, if that is not your case, please follow this guide [[Link GitHub]].  
- Open the terminal in the folder where you want download and work on the project.
- Clone the repository `tenors-network.github.io` on your computer, running this following line:
```bash
git clone https://github.com/tenors-network/tenors-network.github.io.git
```

## Work on the project

- 

- Edit the pages which are in the folder `TenorsNetwork`. It is possible to use `obsidian`for that purpose, opening the vault  folder `TenorsNetwork`.
- Check if the rendering is OK, using the script:
```bash
./build.bat
```
- Open the url  `http://localhost:8080` with your favorite web browser.
- Once the editing is finished, you can commit it: 
 ```bash
 git commit -am "an update message"
 git push
 ```

## Hints for the contributions

The pages are in `MarkDown`format. It is a simple format, which  allows LaTeX formulas between `$...$` or `$$...$$`. For a tutorial on this format see [here](https://www.markdownguide.org/basic-syntax/).
