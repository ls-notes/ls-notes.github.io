# Today I Learned

## 2025-07-12

### how to setup github pages for publishing your notes.
- first create a repo like : <username>.github.io
- create a README.md file (or create index.html/md. Index file has higher precedence)
- create yaml config file with name "_config.yml"
- add following content to the file. it can modified later. (this is just for reference)
```yml
title: My GitHub Pages Site
description: A personal website hosted on GitHub Pages.
theme: jekyll-theme-minimal # Or any other Jekyll theme
```
- now you can create your notes in new files and those will show the github pages homepage (like https://<username>.github.io)
- you can link the other notes files in the index file so it will be visible on the homepage. Linking follows same pattern as Markdown. For eg:
```md
[My Azure Notes](Azure.md)
```
- make sure to not use any special chars (like '|') in the url description as those maybe a meta character in markdown.

## 2025-07-22

### Powershell treats multi-value string in AD as arrays.
Eg: If you retreiving a multi-value attribute 'attribute1', it can be queried like below
```powershell
$AllADUser | select samAccountName, @{Name='Attribute1'; Expression = {$_.AttributeName -join ";"} }
```

- references:
  - https://community.spiceworks.com/t/get-multi-valued-string-from-ad-object/794916/3 
