# J'Jay Yabsley - Professional CV

[![Build CV](https://github.com/jayyabsley/curriculum-vitae/actions/workflows/build-cv.yml/badge.svg)](https://github.com/jayyabsley/curriculum-vitae/actions/workflows/build-cv.yml)
[![Latest Release](https://img.shields.io/github/v/release/jayyabsley/curriculum-vitae)](https://github.com/jayyabsley/curriculum-vitae/releases/latest)
[![PDF Download](https://img.shields.io/badge/PDF-Download%20Latest-blue?logo=adobeacrobatreader)](https://github.com/jayyabsley/curriculum-vitae/releases/latest/download/JJay_Yabsley_CV_latest.pdf)

LaTeX-based CV with automated builds via GitHub Actions.

## Quick Links

| Resource | Link |
|----------|------|
| Latest PDF | [Download CV](https://github.com/jayyabsley/curriculum-vitae/releases/latest/download/JJay_Yabsley_CV_latest.pdf) |
| All Releases | [View Releases](https://github.com/jayyabsley/curriculum-vitae/releases) |
| Build Status | [GitHub Actions](https://github.com/jayyabsley/curriculum-vitae/actions) |
| Source | [src/cv.tex](src/cv.tex) |

## Usage

### Updating the CV

1. Edit the LaTeX files in `src/`:
   - `src/cv.tex` - Main document and personal info
   - `src/sections/experience.tex` - Work experience
   - `src/sections/education.tex` - Education
   - `src/sections/skills.tex` - Technical skills
   - `src/sections/projects.tex` - Projects

2. Commit and push:
   ```bash
   git add .
   git commit -m "Update CV content"
   git push origin main
   ```

The CV will be automatically built and released.

### Building Locally

Install LaTeX, then:

```bash
cd src
pdflatex cv.tex
```

Output will be generated as `cv.pdf`.

For Ubuntu/Debian:
```bash
sudo apt-get update
sudo apt-get install texlive-full
```

For macOS:
```bash
brew install --cask mactex
```

## Repository Structure

```
curriculum-vitae/
├── .github/
│   └── workflows/
│       └── build-cv.yml          # CI/CD pipeline
├── src/                          # LaTeX source files
│   ├── cv.tex                    # Main CV document
│   └── sections/                 # Modular CV sections
│       ├── experience.tex
│       ├── education.tex
│       ├── skills.tex
│       └── projects.tex
├── assets/                       # Images and resources
├── output/                       # Generated PDFs
└── README.md
```

## Customization

### Personal Information

Edit the header section in `src/cv.tex`:

```latex
\name{Your}{Name}
\address{Your Address}{}{}
\phone[mobile]{Your Phone}
\email{your.email@domain.com}
\social[github]{your-github}
\social[linkedin]{your-linkedin}
```

### Adding New Sections

1. Create a new `.tex` file in `src/sections/`
2. Add the section to the main CV:
   ```latex
   \input{sections/your-new-section}
   ```

### Styling

- **Colors**: Change `\moderncvcolor{blue}` in `cv.tex`
- **Theme**: Change `\moderncvstyle{banking}` in `cv.tex`
- **Layout**: Modify `\usepackage[scale=0.85]{geometry}` for margins

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
