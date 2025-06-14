# Git for Research Collaboration - LaTeX Beamer Presentation

## About This Presentation

**Title:** "From Email Chaos to Seamless Collaboration: How Git Could Transform Research Teamwork"

**Duration:** 15 minutes

**Target Audience:** Academic researchers, graduate students, and research teams who struggle with version control and collaboration challenges

**Topic Overview:**
This presentation introduces Git as a solution to common research collaboration problems. It covers:
- Research collaboration challenges (the "Final_v3_REAL_FINAL.docx" problem)
- What Git is and why it matters for researchers
- Essential Git concepts and commands
- Practical workflow for research teams
- Addressing common concerns about Git adoption
- File type recommendations and getting started resources

## File Structure

```
project/
├── wildcat-demo.tex          # Main presentation file
├── README.md                 # This file
├── agh_znk_ngt_cmyk.eps     # AGH University logo
├── imgs/                     # Image directory
│   ├── finel_versions_nigmare.png
│   ├── collaboration.png
│   ├── git-purpose.png
│   └── workflow.png
├── nodes/
│   └── nodes.tex            # TikZ node definitions
└── wildcat/                 # Beamer theme files
    ├── beamerthemewildcat.sty
    ├── beamerfontthemewildcat-overleaf.sty
    └── other theme files...
```

## Prerequisites

### Required LaTeX Distribution
- **TeX Live 2020** or newer (recommended: TeX Live 2023)
- **LuaLaTeX** engine

### Required Packages
The presentation uses the following LaTeX packages:
- `beamer` - Presentation framework
- `minted` - Code highlighting (requires Python Pygments)
- `tikz` - Graphics and diagrams
- `hyperref` - Links and URLs
- `unicode-math` - Unicode math support
- `fontenc` - Font encoding
- Standard math packages: `amsmath`, `amsfonts`, `amssymb`

### External Dependencies
- **Python with Pygments** (for minted package)
  ```bash
  pip install Pygments
  ```
- **Shell escape enabled** (for minted compilation)

## Compilation Instructions

### Method 1: Command Line

```bash
# Navigate to the presentation directory
cd /path/to/presentation

# Compile with LuaLaTeX (recommended)
lualatex -shell-escape wildcat-demo.tex
lualatex -shell-escape wildcat-demo.tex  # Run twice for references


```

### Method 2: Overleaf
1. Upload all files to Overleaf project
2. Set compiler to **LuaLaTeX** in project settings
3. Ensure shell escape is enabled (usually automatic)
4. Compile

### Method 3: TeXstudio/TeXmaker
1. Open `wildcat-demo.tex`
2. Configure build command:
   - **LuaLaTeX:** `lualatex -shell-escape %.tex`
3. Build twice for proper references

### Method 4: VS Code with LaTeX Workshop
Add to `.vscode/settings.json`:
```json
{
    "latex-workshop.latex.recipes": [
        {
            "name": "lualatex-minted",
            "tools": ["lualatex-minted", "lualatex-minted"]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "lualatex-minted",
            "command": "lualatex",
            "args": [
                "-shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        }
    ]
}
```

## Troubleshooting

### Common Issues

**1. "Package minted Error: You must invoke LaTeX with the -shell-escape flag"**
- **Solution:** Add `-shell-escape` flag to compilation command
- **Overleaf:** Should work automatically, contact support if not

**2. "Package minted Error: The package option 'cache=false' does not exist"**
- **Solution:** Update `minted` package or remove cache options

**3. Missing images**
- **Solution:** Ensure all images are in the `imgs/` directory
- Check image file extensions match exactly (case-sensitive on Linux/Mac)

**4. Font issues with LuaLaTeX**
- **Solution:** Ensure you have the required fonts installed
- Alternative: Switch to PDFLaTeX if fonts are problematic

**5. TikZ compilation errors**
- **Solution:** Ensure `nodes/nodes.tex` file exists
- Check TikZ library imports in preamble

## Customization

### Changing Colors
The presentation uses the "wildcat" theme. To customize colors:
```latex
% Uncomment and modify these lines in the preamble:
% \definecolor{wcprimary}{RGB}{0,53,107}      % Main color
% \definecolor{wcalerted}{RGB}{189,83,25}     % Alert color
% \definecolor{wcexample}{RGB}{95,113,45}     % Example color
```

### Adding/Modifying Content
- Main content is in clearly marked `\begin{frame}...\end{frame}` blocks
- Code examples use `\verb|command|` for inline code
- TikZ workflow diagram can be found in the "Git Workflow" frame


## Image Credits

All images are from Allison Horst's excellent Git/GitHub educational materials:
- Source: https://allisonhorst.com/git-github
- License: Creative Commons (check original source for specific license)

## Author Information

**Presenter:** Karol Bednarz  
**Supervisor:** prof. dr hab. inż. Zbigniew Galias  
**Assistant Supervisor:** dr inż. Bartłomiej Garda  
**Institution:** AGH University (based on logo)  
**Date:** June 2025

## License

This presentation template and content are provided for educational use. Please check individual component licenses (theme, images, etc.) for specific usage rights.

## Contributing

To improve this presentation:
1. Fork/copy the project
2. Make your improvements
3. Test compilation thoroughly
4. Share improvements back to the community

## Support

For technical LaTeX issues:
- Check TeX.StackExchange.com
- Consult your institution's LaTeX support
- Ensure all dependencies are properly installed

For Git learning resources mentioned in the presentation:
- GitHub Skills: https://skills.github.com/
- Git tutorials: See final slide of presentation