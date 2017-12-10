# powerbi-vcs-dotnet

Port of the powerbi-vcs utility by kodonnell to c#/dotnet. Original codebase [here](https://github.com/kodonnell/powerbi-vcs)


## Git textconv driver support
This port as an added feature of dumping the extracted file contents to the console to allow for better diffs in git.

Add to repo .gitattributes file:
```
*.pbit diff=pbit
*.pbix diff=pbit
```

Add to global or local .gitconfig file:
```
[diff "pbit"]
	textconv = \"C:/Path/To/Utility/PowerBiVcs.exe\" -s
```

Diffs in git will do their diff on the extracted file content. Textconv diffs are only a visual guide, and can't be used to merge changes, but this provides better insight into what has changed in the power bi report.

Documentation of git textconv drivers [https://git.wiki.kernel.org/index.php/Textconv]

#TODO
- Compare file output with output from pythion library
- Fix metadata export
- Fix pbix/pbit rebuild