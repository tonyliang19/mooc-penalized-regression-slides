# Quick Reference Card

## Penalized Regression Cheat Sheet

### OLS Regression

**Objective:**
$$\hat{\beta}^{OLS} = \arg\min_{\beta} \sum_{i=1}^{n}(y_i - x_i^T\beta)^2$$

**Solution:**
$$\hat{\beta}^{OLS} = (X^TX)^{-1}X^Ty$$

**Issues:**
- Overfitting with many predictors
- Unstable with multicollinearity
- Fails when p > n

---

### Ridge Regression (L2)

**Objective:**
$$\hat{\beta}^{Ridge} = \arg\min_{\beta} \left\{ \sum_{i=1}^{n}(y_i - x_i^T\beta)^2 + \lambda \sum_{j=1}^{p}\beta_j^2 \right\}$$

**Solution:**
$$\hat{\beta}^{Ridge} = (X^TX + \lambda I)^{-1}X^Ty$$

**Properties:**
- Shrinks coefficients toward zero
- Never exactly zero
- Handles multicollinearity
- Works when p > n

**R Code:**
```r
library(glmnet)
ridge_model <- glmnet(X, y, alpha=0)
cv_ridge <- cv.glmnet(X, y, alpha=0)
coef(cv_ridge, s="lambda.min")
```

---

### LASSO Regression (L1)

**Objective:**
$$\hat{\beta}^{LASSO} = \arg\min_{\beta} \left\{ \sum_{i=1}^{n}(y_i - x_i^T\beta)^2 + \lambda \sum_{j=1}^{p}|\beta_j| \right\}$$

**Properties:**
- Shrinks coefficients toward zero
- Sets some exactly to zero
- Automatic variable selection
- Creates sparse models

**R Code:**
```r
library(glmnet)
lasso_model <- glmnet(X, y, alpha=1)
cv_lasso <- cv.glmnet(X, y, alpha=1)
coef(cv_lasso, s="lambda.min")
```

---

### Elastic Net

**Objective:**
$$\hat{\beta}^{EN} = \arg\min_{\beta} \left\{ \sum_{i=1}^{n}(y_i - x_i^T\beta)^2 + \lambda \left[\alpha \sum_{j=1}^{p}|\beta_j| + (1-\alpha) \sum_{j=1}^{p}\beta_j^2\right] \right\}$$

**Parameters:**
- α = 0: Pure Ridge
- α = 1: Pure LASSO  
- 0 < α < 1: Elastic Net

**R Code:**
```r
elastic_model <- glmnet(X, y, alpha=0.5)
cv_elastic <- cv.glmnet(X, y, alpha=0.5)
```

---

## Decision Guide

### Use Ridge When:
✓ All predictors potentially relevant  
✓ High multicollinearity  
✓ Want to keep all variables  
✓ Predictors are correlated  

### Use LASSO When:
✓ Many irrelevant predictors  
✓ Need variable selection  
✓ Want sparse model  
✓ Interpretability is key  

### Use Elastic Net When:
✓ Best of both worlds  
✓ Grouped variables  
✓ p >> n with correlation  

---

## Key Concepts

### Tuning Parameter (λ)

- **λ = 0**: No penalty (OLS)
- **λ → ∞**: Maximum penalty (all β → 0)
- **Optimal λ**: Found via cross-validation

### Cross-Validation

```r
# k-fold CV (typically k=5 or 10)
cv_model <- cv.glmnet(X, y, alpha=1, nfolds=10)

# Two important values:
# lambda.min: Minimum CV error
# lambda.1se: Largest λ within 1 SE (simpler model)
```

### Standardization

**Always standardize before penalized regression:**

```r
# glmnet does this automatically
# Manual:
X_scaled <- scale(X)
```

---

## Common R Functions

### Fitting
```r
# Fit model for sequence of λ values
model <- glmnet(X, y, alpha=α)

# With cross-validation
cv_model <- cv.glmnet(X, y, alpha=α, nfolds=k)
```

### Coefficients
```r
# At specific λ
coef(model, s=λ)

# At optimal λ
coef(cv_model, s="lambda.min")
coef(cv_model, s="lambda.1se")
```

### Predictions
```r
# Predict at specific λ
predict(model, newx=X_new, s=λ)

# Predict at optimal λ
predict(cv_model, newx=X_new, s="lambda.min")
```

### Visualization
```r
# Coefficient paths
plot(model, xvar="lambda")

# CV curve
plot(cv_model)
```

---

## Comparison Table

| Feature | OLS | Ridge | LASSO | Elastic Net |
|---------|-----|-------|-------|-------------|
| Penalty | None | L2 | L1 | L1 + L2 |
| Variable Selection | No | No | Yes | Yes |
| Sparse Model | No | No | Yes | Yes |
| Handles p > n | No | Yes | Yes | Yes |
| Multicollinearity | Poor | Good | Fair | Good |
| Interpretability | High | Medium | High | Medium |

---

## Best Practices

1. **Always standardize** predictors
2. **Use cross-validation** to choose λ
3. **Consider λ.1se** for simpler models
4. **Split data** into train/validation/test
5. **Check assumptions** (especially linearity)
6. **Visualize results** (coefficient paths, CV curves)
7. **Validate predictions** on test set

---

## Common Pitfalls

❌ Not standardizing variables  
❌ Using training data to select λ  
❌ Ignoring λ.1se option  
❌ Not testing on held-out data  
❌ Mixing categorical without proper encoding  
❌ Forgetting to check for outliers  

---

## Resources

- **R Package**: glmnet
- **Documentation**: https://glmnet.stanford.edu/
- **Books**: 
  - "Statistical Learning with Sparsity"
  - "An Introduction to Statistical Learning"
  - "Elements of Statistical Learning"

---

*For full presentation with interactive examples, see `index.qmd`*
