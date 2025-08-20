# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a professional LaTeX-based CV automation system with GitHub Actions CI/CD pipeline. The repository generates high-quality PDFs automatically and manages releases through GitHub's infrastructure.

## Repository Architecture

```
curriculum-vitae/
├── .github/workflows/build-cv.yml    # CI/CD pipeline
├── src/                              # LaTeX source files
│   ├── cv.tex                        # Main CV document
│   └── sections/                     # Modular sections
├── output/                           # Generated PDFs
├── assets/                           # Images and resources
└── documentation files
```

## Development Commands

### Local LaTeX Compilation
```bash
# Compile CV locally
cd src
pdflatex cv.tex

# Clean build artifacts
rm -f *.aux *.log *.out *.synctex.gz
```

### Testing GitHub Actions Locally
```bash
# Install act (GitHub Actions runner)
curl https://raw.githubusercontent.com/nektos/act/master/install.sh | sudo bash

# Test workflow locally
act push
```

### Git Workflow
```bash
# Standard workflow for updates
git add .
git commit -m "📝 Update CV content"
git push origin main

# Manual release trigger
gh workflow run build-cv.yml
```

## File Modification Patterns

### Personal Information Updates
- **Primary file**: `src/cv.tex` (header section)
- **Contact details**: Update `\name{}, \address{}, \phone{}, \email{}` commands
- **Social links**: Modify `\social{}` entries

### Content Section Updates
- **Experience**: Edit `src/sections/experience.tex`
- **Skills**: Edit `src/sections/skills.tex`
- **Education**: Edit `src/sections/education.tex`
- **Projects**: Edit `src/sections/projects.tex`

### Styling and Layout
- **Theme**: Change `\moderncvstyle{}` in main CV file
- **Colors**: Modify `\moderncvcolor{}` setting
- **Layout**: Adjust `\usepackage[scale=X]{geometry}` for margins

## GitHub Actions Workflow

### Trigger Events
- Push to main/master branch (on src/ changes)
- Pull requests (for validation)
- Manual dispatch (workflow_dispatch)

### Build Process
1. **Compilation**: Uses xu-cheng/latex-action@v3
2. **Validation**: PDF size and corruption checks
3. **Versioning**: Automatic semantic versioning
4. **Release**: GitHub release with PDF assets
5. **Quality Check**: Build performance monitoring

### Key Environment Variables
```yaml
CV_FILENAME: "JJay_Yabsley_CV"    # Output PDF name
LATEX_ROOT: "src"                 # Source directory
OUTPUT_DIR: "output"              # Build output location
```

## Quality Standards

### PDF Requirements
- **File size**: < 500KB optimized
- **Build time**: < 2 minutes with caching
- **Format**: Professional ATS-compatible layout
- **Validation**: Automated corruption checks

### Code Standards
- **LaTeX**: ModernCV package with professional styling
- **Structure**: Modular sections for maintainability
- **Documentation**: Comprehensive inline comments
- **Versioning**: Semantic release management

## Customization Guidelines

### Adding New Sections
1. Create new `.tex` file in `src/sections/`
2. Add `\input{sections/filename}` to main CV
3. Test compilation locally
4. Commit and push for automated build

### Workflow Customization
- **Build frequency**: Modify trigger conditions
- **Output formats**: Add additional compilation targets
- **Deployment**: Extend with GitHub Pages or custom deployment
- **Notifications**: Add Slack/email integration for build status

## Troubleshooting

### Common LaTeX Issues
- **Missing packages**: Check texlive-full installation
- **Compilation errors**: Review LaTeX syntax and escaping
- **Font issues**: Verify font availability in build environment
- **Size optimization**: Remove unnecessary packages or images

### GitHub Actions Debugging
- **Build failures**: Check Actions logs for detailed error messages
- **Permission issues**: Verify GITHUB_TOKEN has required scopes
- **Artifact problems**: Ensure paths and file permissions are correct
- **Cache issues**: Clear LaTeX dependency cache if needed

## Maintenance Tasks

### Regular Updates
- Monitor LaTeX package updates and security patches
- Review and update GitHub Actions versions
- Validate PDF generation quality periodically
- Update personal information as career progresses

### Performance Monitoring
- Track build times and optimize if exceeding 2 minutes
- Monitor PDF file sizes and compression effectiveness
- Review GitHub Actions usage and costs
- Assess workflow efficiency and identify improvements