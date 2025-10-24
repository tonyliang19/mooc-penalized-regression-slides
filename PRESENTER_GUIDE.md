# Presenter's Guide

## Pre-Presentation Checklist

### One Week Before

- [ ] Review all slides and understand the flow
- [ ] Test all interactive R code examples
- [ ] Decide on presentation length (30, 45, or 60 minutes)
- [ ] Adjust content based on time available
- [ ] Practice transitions between sections
- [ ] Prepare answers to common questions

### One Day Before

- [ ] Test internet connection (required for webR)
- [ ] Open presentation in browser and test navigation
- [ ] Verify all code blocks execute correctly
- [ ] Check that visualizations render properly
- [ ] Test screen sharing/projection
- [ ] Have backup plan if internet fails

### 30 Minutes Before

- [ ] Open presentation in browser
- [ ] Test audio/video setup
- [ ] Have pen/stylus ready for chalkboard annotations
- [ ] Close unnecessary browser tabs
- [ ] Set browser to full screen (press F)
- [ ] Test first few interactive code blocks

## Presentation Tips

### General Guidelines

**Pacing:**
- Don't rush through mathematical formulas
- Give audience time to absorb concepts
- Pause after running interactive code
- Allow time for questions throughout

**Interactive Code:**
- Run code blocks live, don't skip them
- Explain what code does before running
- Point out key results after execution
- Encourage audience to think about output
- Modify parameters to show different results

**Engagement:**
- Ask questions to check understanding
- Use chalkboard for additional notes
- Encourage participants to experiment
- Relate concepts to real-world examples

### Timing Guide

#### 30-Minute Version (Fast)

- Introduction: 2 min
- OLS Review: 5 min (skip some examples)
- Why Penalized: 3 min
- Ridge: 6 min (focus on key concepts)
- LASSO: 6 min (focus on key concepts)
- Comparison: 4 min
- Practical: 2 min (mention briefly)
- Q&A: 2 min

#### 45-Minute Version (Standard)

- Introduction: 3 min
- OLS Review: 8 min
- Why Penalized: 5 min
- Ridge: 10 min
- LASSO: 10 min
- Comparison: 5 min
- Practical: 4 min
- Q&A: flexible

#### 60-Minute Version (Comprehensive)

- Introduction: 5 min
- OLS Review: 10 min (all examples)
- Why Penalized: 5 min
- Ridge: 12 min (all examples)
- LASSO: 12 min (all examples)
- Comparison: 8 min (including Elastic Net)
- Practical: 5 min
- Exercise: 3 min
- Q&A: flexible

## Section-by-Section Guide

### Introduction (Slides 1-2)

**Key Points:**
- Set expectations for session
- Mention interactive nature
- Encourage participation

**Tips:**
- Start with enthusiasm
- Quick poll: "Who has used regularization before?"
- Set ground rules for questions

### Part 1: OLS Review (Slides 3-8)

**Key Points:**
- Review basics but don't dwell
- Emphasize limitations
- Set up need for regularization

**Tips:**
- "Quick refresher for those new to regression"
- Ask: "What problems have you encountered with OLS?"
- Run the simple example to test webR works

**Common Questions:**
- Q: "Why does OLS fail with p > n?"
  A: Matrix $(X^TX)$ is not invertible
- Q: "What is multicollinearity?"
  A: When predictors are highly correlated

### Part 2: Why Penalized Regression (Slides 9-11)

**Key Points:**
- Overfitting is a real problem
- Bias-variance tradeoff is fundamental
- Penalties control complexity

**Tips:**
- Use intuitive explanations before math
- Draw analogy to Occam's razor
- Emphasize this motivates next sections

### Part 3: Ridge Regression (Slides 12-18)

**Key Points:**
- L2 penalty shrinks but doesn't eliminate
- Good for correlated predictors
- Always use cross-validation

**Tips:**
- Run the correlated predictor example
- Show coefficient path plot
- Emphasize CV is crucial for choosing λ
- Point out no coefficients reach exactly zero

**Interactive Demo Ideas:**
- Change lambda values manually
- Show what happens with different correlations
- Compare to OLS results

**Common Questions:**
- Q: "Why squared penalty?"
  A: Differentiable, mathematical convenience, Bayesian interpretation
- Q: "How to choose lambda?"
  A: Always use cross-validation

### Part 4: LASSO Regression (Slides 19-24)

**Key Points:**
- L1 penalty can eliminate variables
- Automatic feature selection
- Sparse models are interpretable

**Tips:**
- Emphasize difference from Ridge
- Show coefficient paths hitting zero
- Explain geometric intuition if time allows
- Highlight selected variables

**Interactive Demo Ideas:**
- Run LASSO and count non-zero coefficients
- Compare with Ridge on same data
- Show how lambda affects selection

**Common Questions:**
- Q: "Why does L1 give exact zeros?"
  A: Geometric shape of constraint region (corners)
- Q: "What if LASSO picks wrong variable?"
  A: Use stability selection or Elastic Net

### Part 5: Comparison (Slides 25-29)

**Key Points:**
- Ridge vs LASSO have different use cases
- Elastic Net combines both
- Choose based on problem characteristics

**Tips:**
- Reference comparison table frequently
- Run Elastic Net example
- Discuss when to use each

**Decision Framework:**
- Many predictors likely relevant? → Ridge
- Few predictors relevant? → LASSO
- Unsure? → Elastic Net

### Part 6: Practical Considerations (Slides 30-34)

**Key Points:**
- Standardization is critical
- Use proper CV procedure
- Avoid common mistakes

**Tips:**
- Share real-world experience
- Mention these are easy mistakes to make
- Emphasize validation importance

**Common Pitfalls to Emphasize:**
- Not standardizing
- Using training data for all steps
- Ignoring lambda.1se
- Not testing on held-out data

### Part 7: Hands-on Exercise (Slides 35-38)

**Key Points:**
- Complete end-to-end example
- Encourages active participation
- Tests understanding

**Tips:**
- Walk through step by step
- Pause for audience to run code
- Compare results
- Encourage experimentation

**Modifications for Different Audiences:**
- Beginners: Walk through together
- Advanced: Let them try independently first
- Mixed: Pair programming approach

### Summary (Slides 39-42)

**Key Points:**
- Recap main concepts
- Provide resources for learning more
- Encourage application to own problems

**Tips:**
- Ask what surprised people
- Collect questions for later
- Provide contact information

## Keyboard Shortcuts

Essential shortcuts to know:

- **F**: Enter fullscreen mode
- **S**: Open speaker notes
- **O**: Overview mode (see all slides)
- **Esc**: Exit overview/fullscreen
- **Arrow keys**: Navigate slides
- **Space**: Next slide
- **B**: Blank screen (useful for breaks)

## Handling Questions

### During Presentation

**Good Questions to Pause For:**
- Clarification requests
- Quick conceptual questions
- Technical issues with code

**Questions to Defer:**
- Very specific to someone's problem
- Would take >2 minutes to answer
- Off-topic or too advanced

### Q&A Session

**Techniques:**
- Repeat question for whole audience
- Check if others have same question
- Be honest if you don't know
- Offer to follow up individually

**Common Questions:**

1. **"When should I use Ridge vs LASSO?"**
   - See comparison table
   - Depends on problem characteristics
   - Try both, use CV to compare

2. **"What about other penalties?"**
   - SCAD, MCP exist
   - More advanced topic
   - Elastic Net usually sufficient

3. **"Does this work for classification?"**
   - Yes! Logistic regression version
   - glmnet supports it
   - family='binomial' in glmnet

4. **"How to handle categorical variables?"**
   - One-hot encoding
   - glmnet does this automatically
   - Be careful with interpretation

5. **"What about deep learning?"**
   - Also uses regularization (dropout, L2)
   - Same principles apply
   - Different scale and complexity

## Troubleshooting

### WebR Issues

**Code not running:**
- Check internet connection
- Wait 30-60 seconds on first load
- Refresh page
- Check browser console for errors

**Plots not showing:**
- webR may still be loading
- Try re-running code block
- Check if packages loaded

### Technical Issues

**Presentation not displaying correctly:**
- Try different browser (Chrome recommended)
- Clear cache
- Check zoom level (should be 100%)

**Slow performance:**
- Close other applications
- Close browser tabs
- Restart browser

## Post-Presentation

### Immediately After

- [ ] Thank audience
- [ ] Share link to slides
- [ ] Collect feedback
- [ ] Answer remaining questions
- [ ] Share additional resources

### Follow-Up

- [ ] Send presentation link via email
- [ ] Share additional resources mentioned
- [ ] Address unanswered questions
- [ ] Collect and incorporate feedback
- [ ] Update slides if needed

## Customization Tips

### For Different Audiences

**Industry Practitioners:**
- Emphasize practical applications
- Add business context examples
- Discuss computational considerations
- Show real-world case studies

**Academic Students:**
- Include more mathematical derivations
- Discuss theoretical properties
- Add references to papers
- Assign homework problems

**Data Science Bootcamp:**
- Focus on when to use each method
- Emphasize coding practice
- Compare with other ML methods
- Build portfolio project

### For Different Durations

**15-Minute Lightning Talk:**
- Skip OLS review
- One example each for Ridge/LASSO
- Focus on when to use what
- Q&A at end only

**90-Minute Workshop:**
- Add more exercises
- Include breakout activities
- Deeper mathematical treatment
- Applied project

**Multi-Day Course:**
- Add theoretical derivations
- More extensive exercises
- Real datasets
- Assessment/grading

## Additional Resources to Share

- Quarto documentation
- glmnet package vignette
- Statistical Learning books
- R Markdown resources
- Your contact information

## Notes Section

Use this space for your own notes:

- 
- 
- 
- 

---

**Good luck with your presentation!** 🎉

Remember: The goal is for the audience to understand when and how to use penalized regression, not to memorize every formula. Focus on intuition and practical application.
