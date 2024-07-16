# Troubleshooting Issues

## Usability

### Import functionality

#### Reproduce

- open `File` menu 

- choose `Import...` option

- a warning message will show up

<p><center>
<img title="" src="file:///Users/demian/Library/Application%20Support/marktext/images/5105511df36fd76ddf096e5db7e4f1eb1faa189e.png" alt="Screenshot 2024-07-16 at 01.13.57.png" data-align="left" width="386"><br/>
<i><sup>Install pandoc before you want to import files.</sup></i>
</center></p>

#### Reason

When launching `MarkText` from `Finder`, it only searches for `pandoc` in the directories `/usr/bin:/bin:/usr/sbin:/sbin:/Library/TeX/texbin` ([source](https://github.com/marktext/marktext/issues/1392#issuecomment-1567759362))

#### Solution

Install missing packages

- Mac OS

```bash
brew install pandoc librsvg python homebrew/cask/basictex
```

Create a new symbolic link inside the `/Library/TeX/texbin/` directory pointing to the  `/usr/local/bin/pandoc` file.

- Mac OS

```bash
sudo cp -v -s /usr/local/bin/pandoc /Library/TeX/texbin/
```
