# Documentation
We use DocFX for our help and documentation side of things.

## [DocFX](https://dotnet.github.io/docfx/)
You can download the zip package of the precompiled binaries if you would like to play from [here](https://github.com/dotnet/docfx/releases "DocFX Installer").

To build the project, call the DocFX binary and point it to the repository ```docfx.json``` file and use the parameter ```--serve``` to spawn a web-service that listens on [http://localhost:8080](http://localhost:8080) E.G.

```
c:\docfx\docfx.exe c:\docs\docfx.json --serve
```

## Atom

Atom is a third-party text editor that supports Markdown, you can download the program from [here](https://atom.io/ "Install Atom").

Once Atom is installed run the following from a command prompt or terminal.  This will install some useful packages that will assist in the formatting of your documentation.
```
apm install tool-bar markdown-writer tool-bar-markdown-writer git-clone
```

## Command Palette
In the welcome screen we are introduced to probably the most important command in Atom, the Command Palette. If you press "Ctrl+Shift+P"  while focused in an editor pane, the command palette will pop up.

![Command Palette](images/atom/palette.jpg)

More on its uses later.

## [GitHub repository](https://github.com/TransVault/documentation)
You will need a GitHub account if you wish to contribute to our documentation library. If you do not have an account, you can sign up for a free one [here](https://github.com/join).

You can clone our repo by opening the `Command Palette` and typing `git-clone` and press enter.
Enter `https://github.com/TransVault/documentation.git` into the `clone-from` field, and select a local path to save your temporary changes.

You will be prompted to enter your GitHub credentials so please enter them and CRACK ON!

## Markdown Preview
Pressing "Shift+Control+M" whilst in an existing document will bring up the markdown preview pane, so you can see how your document will look once it's published.

## GitHub in Atom

"Ctrl-Shift-9" can be used to toggle the GitHub pane within Atom.

Any saved changes made to the documentation will appear in "Git" in the right hand pane as follows.

![Unstaged Changes](images/atom/unstaged-changes.jpg "Unstaged Changes")

To stage your changes you can either select "Stage All" or right click a file and select "Stage"

Once selected your staged files will appear as below:

![Staged Changes](images/atom/staged-changes.jpg "Staged Changes")

To commit your changes enter a simple "commit message" noting what changes have been made, then press `Commit to Master`

![Commit Changes](images/atom/commit-changes.jpg "Commit")

The final step is to ![Push](images/atom/push.jpg "Push Bottom Right") your changes into the repository. When doing this for the first time, you will be prompted to enter your GitHub userID and password.

When any changes have been committed do remember to check the live [GitHub](https://github.com/TransVault/documentation "GitHub") page to confirm everything is ok.

### Reviewing your Changes

If you select one of the `Unstaged Changes` in the Git pane, it will bring up a new window like the following:

![Changes Made](images/atom/changes-made.jpg "Changes Made")

Lines in Red are rows deleted, those in green are additions to the file.

### Pulling changes from GitHub

If changes have been made by other users to the live repository, the push button will be replaced with ![Pull](images/atom/pull.jpg "Pull Bottom Right").  Pressing this will upload your local copy with the updated files.
