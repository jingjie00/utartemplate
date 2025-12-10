# Universiti Tunku Abdul Rahman (UTAR)'s
# Thesis or Dissertation Template

A LaTeX template for preparing thesis or dissertation documents at Universiti Tunku Abdul Rahman (UTAR).

## Template Information

- **Original Template Author**: Tan Jing Jie
- **Template Website**: https://utartemplete.jingjietan.com
- **GitHub Repository**: https://github.com/jingjie00/utartemplate
- **License**: UTAR Thesis Template License (Attribution Required) - See [LICENSE](LICENSE) file
- **Note**: Please acknowledge the original author when using this template (see Acknowledgement section below)

## Getting Started

### Option 1: Using Overleaf (Recommended for Beginners)

[Overleaf](https://www.overleaf.com/) is an online LaTeX editor that requires no installation:

1. Go to [https://www.overleaf.com/](https://www.overleaf.com/)
2. Sign up for a free account (or log in if you already have one)
3. Click "New Project" → "Upload Project"
4. Upload all files from this template
5. Set the main file to `main-v1.tex` (Menu → Main document)
6. Click "Recompile" to build your document

**Advantages of Overleaf:**
- No installation required
- Works on any device with internet access
- Automatic compilation
- Real-time collaboration
- Free tier available
- Built-in LaTeX distribution

### Option 1b: Using Overleaf in VS Code (Advanced)

You can work with your Overleaf projects directly in VS Code using the Overleaf extension. This gives you the power of VS Code's editor while syncing with Overleaf's cloud compilation.

**Prerequisites:**
- VS Code installed ([Download VS Code](https://code.visualstudio.com/))
- An Overleaf account ([Sign up at Overleaf](https://www.overleaf.com/))

**Setup Instructions:**

1. **Install the Overleaf Extension:**
   - Open VS Code
   - Go to Extensions (View → Extensions or `Cmd+Shift+X` / `Ctrl+Shift+X`)
   - Search for "Overleaf" by James Yu
   - Click "Install"

2. **Get Your Overleaf Cookie:**
   - Open your web browser and log in to [Overleaf](https://www.overleaf.com/)
   - Open your browser's Developer Tools:
     - **Chrome/Edge**: Press `F12` or `Ctrl+Shift+I` (Windows/Linux) / `Cmd+Option+I` (Mac)
     - **Firefox**: Press `F12` or `Ctrl+Shift+I` (Windows/Linux) / `Cmd+Option+I` (Mac)
     - **Safari**: Enable Developer menu first (Preferences → Advanced → Show Develop menu), then press `Cmd+Option+I`
   - Go to the **Application** tab (Chrome/Edge) or **Storage** tab (Firefox) or **Storage** tab (Safari)
   - In the left sidebar, expand **Cookies** → `https://www.overleaf.com`
   - Find the cookie named `overleaf_session2` (or `overleaf_session` for older accounts)
   - Copy the **Value** of this cookie (it's a long string of characters)

3. **Configure the Extension:**
   - In VS Code, press `Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows/Linux) to open the Command Palette
   - Type "Overleaf: Set Cookie" and select it
   - Paste your cookie value when prompted
   - Alternatively, you can set it in VS Code settings:
     - Go to Settings (Code → Preferences → Settings or `Cmd+,` / `Ctrl+,`)
     - Search for "overleaf"
     - Find "Overleaf: Cookie" and paste your cookie value

4. **Open Your Overleaf Project:**
   - Press `Cmd+Shift+P` (Mac) or `Ctrl+Shift+P` (Windows/Linux)
   - Type "Overleaf: Open Project" and select it
   - Choose your project from the list
   - VS Code will download and open your project files locally

5. **Sync Changes:**
   - The extension automatically syncs your changes to Overleaf
   - You can also manually sync by using the command "Overleaf: Sync from Overleaf" or "Overleaf: Sync to Overleaf"
   - Compile your document on Overleaf's website to see the PDF

**Note:** Your cookie may expire after some time. If sync stops working, repeat step 2 to get a fresh cookie.

### Option 2: Installing LaTeX Locally

#### For macOS

**Method 1: MacTeX (Full Distribution - Recommended)**

1. Download MacTeX from: https://www.tug.org/mactex/
2. The download is large (~4GB) but includes everything you need
3. Install the `.pkg` file
4. Use TeXShop (included) or any LaTeX editor

**Method 2: BasicTeX (Smaller Installation)**

1. Install Homebrew if you don't have it:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install BasicTeX:
   ```bash
   brew install --cask basictex
   ```

3. Install additional packages (if needed):
   ```bash
   sudo tlmgr update --self
   sudo tlmgr install collection-latexextra
   ```

**Recommended LaTeX Editors for macOS:**
- [TeXShop](https://www.tug.org/mactex/) (included with MacTeX)
- [TeXstudio](https://www.texstudio.org/)
- [VS Code](https://code.visualstudio.com/) with LaTeX Workshop extension
- [Sublime Text](https://www.sublimetext.com/) with LaTeXTools

#### For Windows

**Method 1: MiKTeX (Recommended)**

1. Download MiKTeX from: https://miktex.org/download
2. Run the installer
3. Choose "Install missing packages on-the-fly" when prompted
4. MiKTeX will automatically download required packages as needed

**Method 2: TeX Live**

1. Download TeX Live from: https://www.tug.org/texlive/windows.html
2. Run the installer
3. Follow the installation wizard (this may take some time)

**Recommended LaTeX Editors for Windows:**
- [TeXstudio](https://www.texstudio.org/) (recommended)
- [TeXworks](https://www.tug.org/texworks/) (included with TeX Live)
- [VS Code](https://code.visualstudio.com/) with LaTeX Workshop extension
- [WinEdt](https://www.winedt.com/) (commercial)

## Compilation Instructions

### Using Command Line

1. Navigate to the template directory:
   ```bash
   cd /path/to/template
   ```

2. Compile the document (run twice for table of contents and cross-references):
   ```bash
   pdflatex main-v1.tex
   bibtex main-v1
   pdflatex main-v1.tex
   pdflatex main-v1.tex
   ```

   Or use a single command that runs all steps:
   ```bash
   latexmk -pdf main-v1.tex
   ```

### Using LaTeX Editors

Most LaTeX editors have a "Build" or "Compile" button. Click it to compile your document. You may need to compile multiple times for:
- Table of contents
- List of figures
- List of tables
- Cross-references
- Bibliography

## Template Structure

```
utartemplate/
├── main-v1.tex          # Main LaTeX file
├── references.bib       # Bibliography file
├── admins/              # Administrative pages
│   ├── abstract.tex
│   ├── acknowledgment.tex
│   ├── approvalsheet.tex
│   ├── coverpage.tex
│   ├── declaration.tex
│   ├── submissionsheet.tex
│   └── titlepage.tex
├── contents/            # Chapter files
│   ├── c1intro.tex
│   ├── c2lit.tex
│   ├── c3aflps.tex
│   ├── c4picepr.tex
│   ├── c5jam.tex
│   ├── c6adam.tex
│   ├── c7nlu.tex
│   ├── c8conclusion.tex
│   └── abbreviations.tex
├── appendices/          # Appendix files
│   └── appendix.tex
└── figures/             # Place your figures here
    └── NN.pdf
```

## Customizing the Template

1. **Title and Personal Information**: Edit the placeholder text in:
   - `admins/coverpage.tex`
   - `admins/titlepage.tex`
   - `admins/abstract.tex`
   - `admins/approvalsheet.tex`
   - `admins/submissionsheet.tex`
   - `admins/declaration.tex`

2. **Content**: Replace "Your content here" placeholders in chapter files

3. **Figures**: Add your figure PDFs to the `figures/` folder and reference them using:
   ```latex
   \includegraphics[width=0.8\textwidth]{your-figure-name.pdf}
   ```

4. **Bibliography**: Add your references to `references.bib` and cite them using:
   ```latex
   \cite{key}      % For in-text citations
   \citep{key}     % For parenthetical citations
   \citet{key}     % For textual citations
   ```
   
   > **💡 Recommended Tool: DOI to BibTeX Converter**
   > 
   > This template author has also created a free online tool to help you convert DOIs to BibTeX format: **[DOI to BibTeX Converter](https://doi2bibtex.web.app/)**
   > 
   > **Features:**
   > - Convert DOIs or URLs to clean BibTeX citations instantly
   > - **arXiv support**: For arXiv papers, automatically extracts and fetches the Related DOI (journal version) so you can cite the original source instead of the preprint
   > - No registration required - completely free to use
   > - Clean, formatted BibTeX output ready to copy
   > - Supports beautification and formatting options
   > - Simply paste your DOI or URL and get the BibTeX entry that you can copy directly into your `references.bib` file
   > 
   > Visit [https://doi2bibtex.web.app/](https://doi2bibtex.web.app/) to try it out!

5. **Changing Reference Style to IEEE**: To change the bibliography style to IEEE format:
   - Open `main-v1.tex`
   - Find the line `\bibliographystyle{plainnat}` (around line 267)
   - Change it to `\bibliographystyle{ieeetr}` for IEEE Transactions format
   - Alternatively, use `\bibliographystyle{IEEEtran}` if you have the IEEEtran package
   - Recompile your document (run `pdflatex` → `bibtex` → `pdflatex` → `pdflatex`)

6. **Abbreviations**: Add your abbreviations to `contents/abbreviations.tex`

## Troubleshooting

### Table of Contents Not Appearing
- Compile the document **twice** (LaTeX needs two passes to generate the TOC)
- Ensure `main-v1.toc` file is generated after first compilation

### Bibliography Not Appearing
- Run the full compilation sequence: `pdflatex` → `bibtex` → `pdflatex` → `pdflatex`
- Check that `references.bib` contains valid BibTeX entries
- Ensure you have citations in your document using `\cite{}`, `\citep{}`, or `\citet{}`

### Missing Packages
- If you get "File not found" errors for packages, install them:
  - **MiKTeX**: Will prompt to install missing packages automatically
  - **TeX Live**: Use `tlmgr install <package-name>`
  - **MacTeX**: Use `sudo tlmgr install <package-name>`

### Cross-References Not Working
- Compile the document **twice** to resolve all cross-references
- Ensure labels are unique and properly formatted: `\label{key}` and `\ref{key}`

## Acknowledgement

This thesis template was originally developed by **Tan Jing Jie**. 

If you use this template for your thesis or dissertation, please acknowledge the original author in your acknowledgements section. An example acknowledgement is already included in `admins/acknowledgment.tex`:

> **Template Acknowledgement**: This thesis was prepared using a template originally developed by Tan Jing Jie. The template is available at: https://github.com/jingjie00/utartemplate

## Template Website

For the latest version of this template and additional resources, visit:
- **GitHub Repository**: https://github.com/jingjie00/utartemplate
- **Template Website**: https://utartemplate.jingjietan.com

## Support

For issues, questions, or contributions related to this template, please refer to the template website or contact the original author.

## License

**License Name**: UTAR Thesis Template License (Attribution Required)  
**License Type**: Permissive with Attribution Requirement

This template is licensed under the UTAR Thesis Template License:

- **Attribution**: Please acknowledge the original author (Tan Jing Jie) in your thesis/dissertation acknowledgements section when using this template
- **Free to Use**: You may use, modify, and distribute this template freely
- **Contributions**: If you contribute to this template (e.g., via pull requests), your contributions are subject to the same license. You only need to acknowledge the license name and description, not the full license text

**Full License**: See [LICENSE](LICENSE) file for complete terms and conditions.

**Quick Summary**: Use freely, and please give credit to the original author in your acknowledgements.

---

**Note**: This template follows UTAR thesis/dissertation formatting guidelines. Please verify with your department for any specific requirements or updates to the formatting guidelines.

