# Contributing Guide

Thank you for your interest in improving this LASSO and Ridge regression presentation!

## How to Contribute

### Reporting Issues

If you find any problems with the presentation:

1. Check if the issue already exists in the GitHub Issues
2. If not, create a new issue with:
   - Clear title describing the problem
   - Steps to reproduce (if applicable)
   - Expected vs actual behavior
   - Your environment (browser, Quarto version, etc.)

### Suggesting Enhancements

Have ideas to improve the presentation? Great!

1. Open an issue describing your enhancement
2. Explain why it would be valuable
3. Provide examples if possible

### Making Changes

#### Small Changes (Typos, Minor Fixes)

1. Fork the repository
2. Make your changes
3. Submit a pull request with a clear description

#### Large Changes (New Sections, Major Restructuring)

1. Open an issue first to discuss the change
2. Wait for feedback from maintainers
3. Fork and implement the change
4. Submit a pull request

## Development Setup

### Prerequisites

- Quarto (latest version recommended)
- Git
- Text editor (VS Code, RStudio, etc.)

### Local Development

```bash
# Clone your fork
git clone https://github.com/YOUR_USERNAME/mooc-penalized-regression-slides.git
cd mooc-penalized-regression-slides

# Preview the presentation
quarto preview index.qmd

# Make changes to index.qmd or other files

# Preview updates (auto-reload)
# Changes appear automatically in browser
```

### Testing Your Changes

Before submitting:

1. **Preview locally**: Ensure slides render correctly
2. **Test interactive code**: Run all webR code blocks
3. **Check timing**: Verify slide progression makes sense
4. **Review documentation**: Update README/USAGE if needed

## Contribution Guidelines

### Code Style

#### Markdown/Quarto

- Use consistent heading levels
- Keep lines under 80 characters when possible
- Use blank lines between sections
- Indent code blocks properly

#### R Code

- Follow tidyverse style guide
- Add comments for complex operations
- Keep examples simple and clear
- Use meaningful variable names

#### Math Notation

- Use LaTeX math notation
- Define variables clearly
- Keep equations readable
- Align multi-line equations

### Content Guidelines

#### New Slides

When adding new slides:

- **Relevance**: Directly related to LASSO/Ridge regression
- **Clarity**: Clear, concise explanations
- **Examples**: Include code or visual examples
- **Timing**: Consider overall presentation length

#### Interactive Examples

For new webR code blocks:

- **Self-contained**: Work without external dependencies
- **Clear output**: Produce meaningful results
- **Educational**: Demonstrate key concepts
- **Fast execution**: Complete quickly in browser

#### Mathematical Content

- **Accuracy**: Double-check all formulas
- **Notation**: Use standard notation
- **Explanation**: Provide context for equations
- **Progressive**: Build from simple to complex

### Documentation

Update documentation when changing:

- **Presentation content**: Update README
- **Usage**: Update USAGE.md
- **Configuration**: Document in README
- **Dependencies**: Note in _quarto.yml

## Commit Messages

Use clear, descriptive commit messages:

```
Good:
- "Add elastic net example to comparison section"
- "Fix typo in Ridge regression formula"
- "Update cross-validation visualization code"

Bad:
- "Update"
- "Fix stuff"
- "Changes"
```

## Pull Request Process

1. **Create PR** with clear title and description
2. **Describe changes** in detail
3. **Link issues** if applicable
4. **Preview link** if you've deployed to Quarto Pub
5. **Wait for review** from maintainers

### PR Checklist

- [ ] Code renders without errors
- [ ] All interactive examples work
- [ ] Documentation updated
- [ ] No typos or grammar errors
- [ ] Commits have clear messages
- [ ] PR description explains changes

## Types of Contributions Needed

We especially welcome:

### Content Improvements

- Additional examples and exercises
- Improved explanations
- Better visualizations
- Real-world case studies

### Technical Enhancements

- Performance improvements
- Better styling/design
- Accessibility improvements
- Mobile responsiveness

### Documentation

- Clearer instructions
- Additional use cases
- Troubleshooting guides
- Translation to other languages

### Interactive Features

- More webR examples
- Interactive visualizations
- Self-assessment quizzes
- Extended exercises

## Review Process

1. **Initial review** (1-3 days): Maintainer reviews PR
2. **Feedback**: Comments or requested changes
3. **Revision**: Make requested updates
4. **Approval**: PR approved by maintainer
5. **Merge**: Changes merged to main branch

## Recognition

Contributors will be:

- Listed in commit history
- Acknowledged in release notes
- Added to contributors list (if significant contribution)

## Questions?

- Open an issue for questions
- Tag with "question" label
- Maintainers will respond as soon as possible

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Accept constructive criticism
- Focus on what's best for the project
- Show empathy towards others

### Unacceptable Behavior

- Harassment or discrimination
- Trolling or insulting comments
- Public or private attacks
- Publishing others' private information

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.

## Getting Help

Need help contributing?

1. Read the README and USAGE guides
2. Check existing issues and PRs
3. Open a new issue with "help wanted" label
4. Reach out to maintainers

## Thank You!

Every contribution, no matter how small, helps improve this educational resource. We appreciate your time and effort!

---

*Last updated: 2025-10-24*
