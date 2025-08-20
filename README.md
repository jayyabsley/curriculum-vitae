# 🎓 J'Jay Yabsley - Professional CV

[![Build CV](https://github.com/jay-yabsley/curriculum-vitae/actions/workflows/build-cv.yml/badge.svg)](https://github.com/jay-yabsley/curriculum-vitae/actions/workflows/build-cv.yml)
[![Latest Release](https://img.shields.io/github/v/release/jay-yabsley/curriculum-vitae)](https://github.com/jay-yabsley/curriculum-vitae/releases/latest)
[![PDF Download](https://img.shields.io/badge/PDF-Download%20Latest-blue?logo=adobeacrobatreader)](https://github.com/jay-yabsley/curriculum-vitae/releases/latest/download/JJay_Yabsley_CV_latest.pdf)

> **Personal CV Repository** - Automated LaTeX CV generation with GitHub Actions pipeline.

## 📋 Quick Access

| Resource | Link |
|----------|------|
| **📄 Latest PDF** | [Download CV](https://github.com/jay-yabsley/curriculum-vitae/releases/latest/download/JJay_Yabsley_CV_latest.pdf) |
| **🚀 All Releases** | [View Releases](https://github.com/jay-yabsley/curriculum-vitae/releases) |
| **🔧 Build Status** | [GitHub Actions](https://github.com/jay-yabsley/curriculum-vitae/actions) |
| **📝 Source LaTeX** | [src/cv.tex](src/cv.tex) |

## ✨ Features

### 🎯 Professional Quality
- **Modern LaTeX Template**: Based on proven Overleaf professional templates
- **ATS Optimized**: Applicant Tracking System compatible formatting
- **Print Ready**: High-quality typography optimized for both digital and print
- **Modular Structure**: Easy maintenance with separated sections

### 🤖 Automation Excellence
- **GitHub Actions CI/CD**: Automatic compilation on every commit
- **Multi-trigger Support**: Push, PR, and manual dispatch workflows
- **Semantic Versioning**: Automated version management
- **Release Automation**: Auto-generated GitHub releases with assets
- **Quality Assurance**: Built-in PDF validation and size optimization
- **Performance Optimized**: Cached LaTeX dependencies for ~1-2 minute builds

### 🔧 Technical Specifications
- **Build Time**: < 2 minutes
- **Output Size**: Optimized PDFs under 500KB
- **Multi-format**: Standard and web-optimized versions
- **Error Handling**: Comprehensive build failure reporting
- **Artifact Management**: 90-day retention with automatic cleanup

## 🚀 Usage

### Updating CV Content

1. **Edit CV Sections**
   ```bash
   # Edit the main CV file
   vim src/cv.tex
   
   # Update individual sections
   vim src/sections/experience.tex
   vim src/sections/skills.tex
   vim src/sections/education.tex
   vim src/sections/projects.tex
   ```

2. **Build and Deploy**
   ```bash
   git add .
   git commit -m "Update CV content"
   git push origin main
   ```

Your CV will automatically build and be available as a release!

### Local Development

1. **Local Development Setup**
   ```bash
   # Install LaTeX (Ubuntu/Debian)
   sudo apt-get update
   sudo apt-get install texlive-full
   
   # Install LaTeX (macOS with Homebrew)
   brew install --cask mactex
   
   # Install LaTeX (Windows)
   # Download and install MiKTeX from https://miktex.org/
   ```

2. **Local Build**
   ```bash
   cd src
   pdflatex cv.tex
   # Output will be generated as cv.pdf
   ```

3. **Test GitHub Actions Locally** (Optional)
   ```bash
   # Install act (GitHub Actions local runner)
   # https://github.com/nektos/act
   act push
   ```

## 📁 Repository Structure

```
curriculum-vitae/
├── 📁 .github/
│   └── 📁 workflows/
│       └── 🔧 build-cv.yml          # Main CI/CD pipeline
├── 📁 src/                          # LaTeX source files
│   ├── 📝 cv.tex                    # Main CV document
│   ├── 📁 sections/                 # Modular CV sections
│   │   ├── 💼 experience.tex        # Work experience
│   │   ├── 🎓 education.tex         # Educational background
│   │   ├── 🛠️  skills.tex           # Technical skills
│   │   └── 🚀 projects.tex          # Projects and products
│   └── 📁 styles/                   # Custom styling (optional)
├── 📁 assets/                       # Images, logos, etc.
├── 📁 output/                       # Generated PDFs (auto-managed)
├── 📋 README.md                     # This documentation
├── 🔒 .gitignore                    # Git ignore patterns
└── ⚖️  LICENSE                      # MIT License
```

## 🔧 Customization Guide

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

### Styling Customization
- **Colors**: Change `\moderncvcolor{blue}` in `cv.tex`
- **Theme**: Change `\moderncvstyle{banking}` in `cv.tex`
- **Layout**: Modify `\usepackage[scale=0.85]{geometry}` for margins

### Workflow Customization
Key variables in `.github/workflows/build-cv.yml`:
```yaml
env:
  CV_FILENAME: "Your_Name_CV"        # Output filename
  LATEX_ROOT: "src"                  # LaTeX source directory
  OUTPUT_DIR: "output"               # PDF output directory
```

## 🚀 Deployment Options

### GitHub Releases (Default)
- Automatic releases on every push to main
- Semantic versioning with date stamps
- Professional release notes generation
- Asset management with PDF attachments

### GitHub Pages (Optional)
Add to your workflow for web deployment:
```yaml
- name: Deploy to GitHub Pages
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./output
```

### Custom Deployment
The workflow can be extended to deploy to:
- Personal websites
- Cloud storage (AWS S3, Google Cloud)
- Content management systems
- Portfolio platforms

## 🔍 Quality Assurance

### Automated Checks
- **PDF Validation**: Size and corruption checks
- **Build Verification**: LaTeX compilation success
- **Performance Monitoring**: Build time optimization
- **Artifact Management**: Retention and cleanup policies

### Manual Quality Checks
Before major updates, verify:
- [ ] All sections render correctly
- [ ] Contact information is current
- [ ] Links are functional and professional
- [ ] Formatting is consistent across sections
- [ ] PDF size is reasonable (< 500KB)

## 📞 Troubleshooting

### Common Issues

**Build Failures**
- Check LaTeX syntax in your `.tex` files
- Ensure all `\input` files exist
- Verify special characters are properly escaped

**PDF Not Generating**
- Check GitHub Actions logs for compilation errors
- Ensure repository has Actions enabled
- Verify file permissions and paths

**Large PDF Size**
- Optimize images in `assets/` directory
- Remove unnecessary LaTeX packages
- Check for embedded fonts issues

### Resources
- 📖 **LaTeX Help**: [Overleaf Documentation](https://www.overleaf.com/learn)
- 🔧 **ModernCV Documentation**: [CTAN ModernCV](https://ctan.org/pkg/moderncv)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**📝 Built with LaTeX** | **⚡ Automated with GitHub Actions**

*Last updated: Automatically on every commit*

</div>