

<p align="center">
    <picture>
      <source width="600px" height="300px" srcset="https://github.com/sahiljhawar/BibQuest/blob/main/assets/bibquest.svg">
      <img alt="BibQuest">
    </picture>
</p>


[![PyPi](https://badge.fury.io/py/bibquest.svg)](https://badge.fury.io/py/bibquest)

Often while writing scientific documents, it's tedious to constantly switch between your text editor and various tabs to copy BibTeX entries. Instead of interrupting your writing flow, simply use citation keys in your document and let $\mathrm{\large B{\scriptsize{IB}}Q{\scriptsize{UEST}}}$ fetch all the bibliography entries automatically once you're done writing.

## Installation
### Method 1: 
```bash
pip install bibquest
```
### Method 2: 

```bash
git clone https://github.com/sahiljhawar/BibQuest.git
cd BibQuest
```
With `pip`
```bash
pip install .
```
or, if using `uv`
```bash
uv venv
. .venv/bin/activate
uv pip install .
```

The above methods will make sure that the `bibquest` command is available in your terminal.

## Usage


### Method 1: From `.bcf` file  (recommended)
Compile your LaTeX document once, then use the generated `.bcf` file:
```bash
bibquest example/document.bcf example/bibliography.bib
```

### Method 2: From LaTeX log file
Compile your LaTeX document once, then use the generated log file:
```bash
bibquest example/document.log example/bibliography.bib
```

### Method 3: From TeX source file
Scan your TeX source file directly:
```bash
bibquest --scan-tex example/document.tex example/bibliography.bib
```

## Terminal Output
<p align="center">
    <picture>
      <source width="600px" height="300px" srcset="https://github.com/sahiljhawar/BibQuest/blob/main/assets/example.jpeg">
      <img alt="BibQuest">
    </picture>
</p>


### Options
- `--delay 2.0` - Set delay between requests (default: 1.0 seconds)
- `--append` - Append to existing bibliography file (default behavior)
- `--verbose` - Show verbose output

## Supported Sources
- **arXiv**: `arXiv:2301.12345` or `2301.12345`
- **INSPIRE-HEP**: `Author:2023abc`
- **NASA ADS**: ADS identifiers (fallback method)


## Note
- In arXiv, it uses the arXiv ID instead of the bib key for the entry. This is because arXiv does not let you search with the bib key.
- Try not to use ADS as they rate limit requests. In general as well it is better not to use ADS and instead use arXiv or INSPIRE-HEP. See the [ads2inspire](https://github.com/duetosymmetry/ads2inspire).