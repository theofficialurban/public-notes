---
share: "false"
---




```yaml
share: true
path:  file.md # given as an example path
links:
  mdlinks: true
  convert: true
  internals: false
  nonShared: false
  unlink: false

embed:
  send: false
  remove: keep
  char: ->
attachment:
  send: true
  folder: 
dataview: true
hardBreak: false
includeLinks: truerepo:
  owner: theofficialurban
  repo: public-notes
  branch: master
  autoclean: false
copylink:
  base: https://public-notes.github.io/public-notes
```

- `share`: This key is used to share a note with the plugin.
    You could also use another shareKey based on the key set in « Manage other repo ». It allows you to separate your different repository. If the main and secondaries key are used, the main repo will be used.
- `path`: You can override all path settings using this key. The path will be relative to the root of your repository.
- `links`:
    - `mdlinks`: Convert all `[[markdown|alias]]` in `[alias](markdown)`
    - `convert`: Enable or disable the conversion of links. Disabling this will remove the `[[link]]` or `[](link)` syntax, while keeping the file name or the alternative text.
    - `internals`: Convert internals links to their counterpart in the website, with relative path. Disabled, the plugin will keep the internal link as is.
    - `nonShared`: Convert internal links pointing to a unshared file to their counterpart in the website, with relative path. Disabled, the plugin will keep the filename.
    - `unlink`: Deletes link syntax (retains only name or alias) for unshared files only.
- `embed`:
    - `send`: Send embedded note to GitHub
    - `remove`: Modify the aspect of the embedded files link. Can take the followed value:
        - `remove | true`: Delete the citation completely and leave an empty line
        - `keep | false`: Leave as in Obsidian
        - `links`: Convert to links (delete or edit the "!")
        - `bake`: Include the content of the embed (support blocks, heading and entire file)
    - `char`: Add a character(s) before the embedded links. Used only if you set "remove" to "links".
- `attachment`:
    - `send`: Send all attachments to GitHub
    - `folder`: Change the default folder for the attachments
- `dataview`: Convert dataview queries to markdown.
- `hardbreak`: Convert all linebreaks to markdown «hard break».
- `includeLinks`: Allows sending files linked by a simple link, such as `[[markdown]]` or `[](markdown)`
- `shortRepo`: Allow to use one of the repo set in other repo settings.
- `repo`:
    - `owner`: Owner of the repo
    - `repo`: Repository name
    - `branch`: Branch of the repo
    - `autoclean`: Disable or enable autocleaning
- `title`: Change the title of the note.
- `baseLink`: Change the base link for the copy link command. Also disable the link replacer part. Can be used as an properties object with the name `copylink:`
    - `base`: Base link
    - `remove`: Remove part of the link. It must be a list!