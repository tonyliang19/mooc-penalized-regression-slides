# Penalized Regression: LASSO and Ridge

A comprehensive Quarto reveal.js presentation explaining LASSO and Ridge regression methods, designed for a 30-60 minute session with interactive R code examples.

## Overview

This presentation covers:

- **OLS Review**: Quick introduction to Ordinary Least Squares regression
- **Why Penalized Regression**: Understanding overfitting and the bias-variance tradeoff
- **Ridge Regression**: L2 penalty and its properties
- **LASSO Regression**: L1 penalty and automatic variable selection
- **Comparison**: When to use Ridge vs LASSO
- **Practical Considerations**: Best practices and common pitfalls
- **Hands-on Exercise**: Interactive examples with real code

## Features

- **Interactive R Code**: Uses webR to run R code directly in the browser - no installation needed!
- **Live Examples**: Experiment with Ridge, LASSO, and Elastic Net on dummy data
- **Visual Explanations**: Coefficient paths, cross-validation plots, and more
- **Comprehensive Coverage**: From basics to advanced topics

## Prerequisites

Audience should have:

- Basic understanding of statistics
- Familiarity with linear regression concepts
- (Optional) Some R programming experience

## How to Use

### Online Viewing

Once published, you can view the presentation directly in a web browser. The interactive R code will run using webR without any local installation.

### Local Development

1. **Install Quarto** (if not already installed):
   - Download from [quarto.org](https://quarto.org/docs/get-started/)

2. **Clone the repository**:
   ```bash
   git clone https://github.com/tonyliang19/mooc-penalized-regression-slides.git
   cd mooc-penalized-regression-slides
   ```

3. **Preview the presentation**:
   ```bash
   quarto preview index.qmd
   ```

4. **Render to HTML**:
   ```bash
   quarto render index.qmd
   ```

### Publishing

To publish on GitHub Pages or Quarto Pub:

```bash
# GitHub Pages
quarto publish gh-pages

# Quarto Pub
quarto publish quarto-pub
```

## Customization

### Modify Content

Edit `index.qmd` to customize:

- Slide content and examples
- Add your contact information
- Adjust code examples
- Add more sections as needed

### Styling

Edit `custom.scss` to change:

- Colors and theme
- Font sizes
- Layout preferences

### Configuration

Edit `_quarto.yml` to modify:

- Presentation settings
- Navigation options
- Theme and appearance

## Structure

```
.
├── index.qmd          # Main presentation file
├── _quarto.yml        # Quarto configuration
├── custom.scss        # Custom styling
└── README.md          # This file
```

## Interactive Code

The presentation uses the `webr` filter to enable browser-based R execution. Attendees can:

- Run all code examples in real-time
- Modify parameters and see results
- Experiment with different data
- Learn by doing!

No R installation required - everything runs in the browser!

## Topics Covered

1. **OLS Review** (5-10 min)
   - Basic concepts and assumptions
   - Problems with OLS

2. **Penalized Regression Introduction** (5 min)
   - Overfitting problem
   - Bias-variance tradeoff

3. **Ridge Regression** (10-15 min)
   - L2 penalty definition
   - Properties and use cases
   - Interactive examples

4. **LASSO Regression** (10-15 min)
   - L1 penalty definition
   - Variable selection
   - Interactive examples

5. **Comparison & Elastic Net** (5-10 min)
   - When to use each method
   - Combining both approaches

6. **Practical Considerations** (5-10 min)
   - Standardization
   - Cross-validation
   - Common pitfalls

7. **Hands-on Exercise** (5-10 min)
   - Complete example from scratch

## Contributing

Feel free to:

- Add more examples
- Improve explanations
- Fix typos or errors
- Suggest new topics

Submit a pull request or open an issue!

## License

[Add your license here]

## Acknowledgments

This presentation uses:

- [Quarto](https://quarto.org/) for document generation
- [Reveal.js](https://revealjs.com/) for presentation framework
- [webR](https://docs.r-wasm.org/webr/latest/) for browser-based R execution
- [glmnet](https://glmnet.stanford.edu/) R package for penalized regression

## Additional Resources

- **Statistical Learning with Sparsity** by Hastie, Tibshirani, and Wainwright
- **An Introduction to Statistical Learning** by James, Witten, Hastie, and Tibshirani
- **Elements of Statistical Learning** by Hastie, Tibshirani, and Friedman
- [glmnet vignette](https://glmnet.stanford.edu/articles/glmnet.html)