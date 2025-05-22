# BibQuest

Often while writing scientific documents, it's tedious to constantly switch between your text editor and various tabs to copy BibTeX entries. Instead of interrupting your writing flow, simply use citation keys in your document and let this tool fetch all the bibliography entries automatically once you're done writing.

## Installation

```bash
pip install bibquest
```
or
```bash
git clone https://github.com/sahiljhawar/BibQuest.git
pip install .
```
or 

```bash
uv pip install .
```

## Usage

### Method 1: From LaTeX log file (recommended)
Compile your LaTeX document once, then use the generated log file:
```bash
bibquest example/document.log example/bibliography.bib
```

### Method 2: From TeX source file
Scan your TeX source file directly:
```bash
bibquest --scan-tex example/document.tex example/bibliography.bib
```

### Options
- `--delay 2.0` - Set delay between requests (default: 1.0 seconds)
- `--append` - Append to existing bibliography file (default behavior)
- `--verbose` - Show verbose output

## Supported Sources
- **arXiv**: `arXiv:2301.12345` or `2301.12345`
- **INSPIRE-HEP**: `Author:2023abc`
- **NASA ADS**: ADS bibcodes (fallback method)


## Note
- In arXiv, it uses the arXiv ID instead of the bib key for the entry. This is because arXiv does not let you search with the bib key.
- Try not to use ADS as they rate limit requests. In general as well it is better not to use ADS and instead use arXiv or INSPIRE-HEP. See the [ads2inspire](https://github.com/duetosymmetry/ads2inspire).