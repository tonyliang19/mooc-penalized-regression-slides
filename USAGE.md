# Usage Guide

## Viewing the Presentation

### Online (Recommended)

Once published to GitHub Pages or Quarto Pub, the presentation can be viewed directly in any modern web browser. All interactive R code will run using webR without requiring local R installation.

### Local Preview

If you have Quarto installed locally:

```bash
# Preview with live reload
quarto preview index.qmd

# Or render to HTML
quarto render index.qmd
```

Then open `index.html` in your browser.

## Interactive Features

### Navigation

- **Arrow keys**: Navigate between slides
- **Space**: Next slide
- **Overview mode**: Press `Esc` or `O`
- **Fullscreen**: Press `F`
- **Speaker notes**: Press `S`

### Chalkboard

- Click the chalkboard icon to draw on slides
- Useful for annotations during presentation

### Interactive R Code

All code blocks with `{webr-r}` are executable:

1. **Run code**: Click the "Run Code" button in each code block
2. **Edit code**: Modify the code directly in the block
3. **Re-run**: Click "Run Code" again to see updated results

### Example Uses

- Experiment with different lambda values
- Try different sample sizes
- Modify coefficients to see effects
- Test your understanding with custom data

## Presentation Flow

**Estimated timing (60 minutes total):**

1. **Introduction** (5 min)
   - Welcome and overview
   - Learning objectives

2. **OLS Review** (10 min)
   - OLS basics and assumptions
   - Problems with OLS
   - Interactive examples

3. **Penalized Regression Intro** (5 min)
   - Why penalization?
   - Bias-variance tradeoff

4. **Ridge Regression** (12 min)
   - L2 penalty definition
   - Key properties
   - Interactive examples
   - Cross-validation

5. **LASSO Regression** (12 min)
   - L1 penalty definition
   - Variable selection
   - Interactive examples
   - Comparison of coefficient paths

6. **Comparison** (8 min)
   - Ridge vs LASSO
   - Elastic Net
   - When to use each

7. **Practical Considerations** (5 min)
   - Standardization
   - Cross-validation tips
   - Common pitfalls

8. **Hands-on Exercise** (3 min)
   - Complete example
   - Interactive exploration

9. **Q&A** (remaining time)

## Customization Tips

### For Instructors

1. **Add your information**: 
   - Edit the `author` field in the YAML header
   - Add contact info on the final slide

2. **Adjust timing**:
   - Remove slides for shorter sessions
   - Add more examples for longer workshops

3. **Customize data**:
   - Replace dummy data with domain-specific examples
   - Add real-world case studies

4. **Modify exercises**:
   - Create discipline-specific problems
   - Add guided practice sessions

### For Learners

1. **Pace yourself**: Take time with interactive examples
2. **Experiment**: Modify code to test understanding
3. **Take notes**: Use the chalkboard feature
4. **Ask questions**: Pause and clarify concepts

## Troubleshooting

### WebR Not Loading

- Ensure internet connection (webR loads from CDN)
- Try refreshing the page
- Check browser console for errors

### Code Not Running

- Wait for webR to initialize (first load may take 30-60 seconds)
- Check for syntax errors in modified code
- Reload the page to reset

### Styling Issues

- Clear browser cache
- Try a different browser (Chrome, Firefox, Safari recommended)
- Check that `custom.scss` is in the same directory

## Publishing Options

### GitHub Pages

```bash
quarto publish gh-pages
```

### Quarto Pub

```bash
quarto publish quarto-pub
```

### Netlify

```bash
quarto render
# Then deploy the _site directory
```

## Additional Resources

- [Quarto Reveal.js Documentation](https://quarto.org/docs/presentations/revealjs/)
- [WebR Documentation](https://docs.r-wasm.org/webr/latest/)
- [glmnet Package Documentation](https://glmnet.stanford.edu/)
- [Reveal.js Keyboard Shortcuts](https://revealjs.com/keyboard/)

## Support

For issues or questions:

1. Check this guide
2. Review the README.md
3. Open an issue on GitHub
4. Contact the presenter (if viewing during a live session)
