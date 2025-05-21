---
title: How to Contribute
tags:
  - guide
---
This page explains how to contribute to the [Tenors Network](https://github.com/tenors-network) GitHub page, with a focus for this wiki.

## GitHub Account

- First you need a [GitHub](https://github.com/) account to publish your contribution and your material.
- After that you need to create a personal access token  

# Quick Contribution

- You can edit this wiki directly from GitHub by opening the desired file and clicking the edit button.
- Once you are in the edit page write your contribution in `Markdown`, a simple format that allows you to include LaTeX formulas, automatically highlight code, and other very useful things. You can find a guide following this [link](https://www.markdownguide.org/basic-syntax/).
- When you are finished you can click on the `commit changes...` button to save your changes, specifying a message with a brief description of the changes.

# Long-term Contribution

This part is designed for those who will be frequent contributors to this wiki. This option allows you to work offline on your laptop, and then in a second moment publish their contributions. 

## Clone the project
  
- Open the terminal in the folder where you want download and work on the project.
- Clone the repository `tenors-network.github.io` via HTTPS on your computer, running this following line:
```bash
git clone https://github.com/tenors-network/tenors-network.github.io.git
```

## Set up on local machine

- All `Markdown` pages are located in the directory `TensorNetwork` and can be edited with any markdown editor. Among many editors we suggest [Obsidian](https://obsidian.md/) mainly for the presence of plugins which make easier writing in markdown. 
-  In Obsidian open the folder `TensorNetwork` as vault.

## Review and Publish

- While you are writing and before publish your notes, you can create a preview of the website running the following line in your terminal.  
```bash
./build.bat
```

- It creates the website based on your local content and it is available [http://localhost:8080](http://localhost:8080) in your favorite web browser.

- Once you have finished editing, you may commit the changes by running the following lines in the terminal inside the project folder, replacing `{bash}"<Commit message>"` with a brief description of the changes.  
 ```bash
 git pull
 git commit -am "<Commit message>"
 git push
 ```


