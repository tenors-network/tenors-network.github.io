---
title: How to Contribute
tags:
  - guide
---
### To contribute 

- Get a write access to [github.com/tenors-network](https://github.com/tenors-network)
- Clone the repository `tenors-network.github.io` on your computer
```
git clone https://github.com/tenors-network/tenors-network.github.io.git
```
- Edit the pages which are in the folder `TenorsNetwork`. It is possible to use `obsidian`for that purpose, opening the vault  folder `TenorsNetwork`.
- Check if the rendering is OK, using the script:
```
./build.bat
```
- Open the url  `http://localhost:8080` with your favorite web browser.
- Once the editing is finished, you can commit it: 
 ```
 git commit -am "an update message"
 git push
 ```

### Hint on the contributions

The pages are in `MarkDown`format. It is a simple format, which  allows LaTeX formulas between `$...$` or `$$...$$`. For a tutorial on this format see [here](https://www.markdownguide.org/basic-syntax/).
