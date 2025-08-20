# Generated CV Output Directory

This directory contains automatically generated PDF versions of the CV.

## 📄 File Naming Convention

- `JJay_Yabsley_CV_latest.pdf` - Always the most recent version
- `JJay_Yabsley_CV_v{version}.pdf` - Specific version releases

## 🤖 Automated Management

This directory is automatically managed by GitHub Actions:
- PDFs are generated on every commit to main branch
- Files are automatically committed back to the repository
- Versions are tagged and released automatically
- Old versions are retained for historical reference

## 📥 Download Options

1. **Latest Version**: Always download the `*_latest.pdf` file
2. **Specific Version**: Choose a specific timestamped version
3. **GitHub Releases**: Access via the Releases tab for organized downloads

## 🔧 Manual Updates

If you need to manually update this directory:
1. Ensure you have write access to the repository
2. Build the PDF locally using `pdflatex src/cv.tex`
3. Copy the generated PDF to this directory with appropriate naming
4. Commit and push changes

## 📊 Quality Guidelines

Generated PDFs should meet these criteria:
- **File Size**: Under 500KB for optimal loading
- **Quality**: High-resolution for both digital and print use
- **Compatibility**: Works across all major PDF readers
- **Accessibility**: Proper text selection and searchability

---

*This directory is automatically managed by GitHub Actions - manual changes may be overwritten*