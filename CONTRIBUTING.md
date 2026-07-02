# Contributing to ShopSphere E-Commerce Analytics Dashboard

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing to this project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Reporting Issues](#reporting-issues)
- [Submitting Changes](#submitting-changes)
- [Style Guidelines](#style-guidelines)
- [Questions?](#questions)

---

## 📜 Code of Conduct

This project adheres to the [Contributor Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to the maintainers.

---

## 🚀 Getting Started

### Prerequisites

- **Power BI Desktop** (Latest version recommended)
- **Git** installed on your machine
- **GitHub account** for fork and pull request
- **Basic understanding** of e-commerce analytics and Power BI

### Fork and Clone

1. **Fork the repository**
   ```bash
   Click "Fork" button on GitHub
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR-USERNAME/shopsphere-ecommerce-dashboard.git
   cd shopsphere-ecommerce-dashboard
   ```

3. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

---

## 🎯 How to Contribute

### Types of Contributions Welcome

✅ **Dashboard Improvements**
- New visualizations
- Enhanced interactivity
- Performance optimizations
- Improved user experience

✅ **Documentation**
- Better explanations
- Additional examples
- Tutorial guides
- Video documentation

✅ **Data & Analysis**
- Additional metrics
- New insights
- Deeper analysis
- Predictive models

✅ **Code & Scripts**
- Data preprocessing scripts
- SQL queries
- Python analysis
- Automation tools

✅ **Bug Fixes**
- Report and fix issues
- Data validation improvements
- Performance fixes

✅ **Features**
- New dashboard pages
- Additional filters
- Export functionality
- Mobile optimization

---

## 🐛 Reporting Issues

### Before Reporting

1. **Check existing issues** - Your issue may already be reported
2. **Review documentation** - The answer might be in README or guides
3. **Test thoroughly** - Ensure you can reproduce the issue

### How to Report a Bug

1. **Go to Issues tab** on GitHub
2. **Click "New Issue"**
3. **Use this template:**

```markdown
## Bug Description
Clear and concise description of the bug.

## Steps to Reproduce
1. Step 1
2. Step 2
3. Step 3

## Expected Behavior
What should happen?

## Actual Behavior
What actually happens?

## Screenshots
[If applicable, add screenshots]

## Environment
- Power BI Version: [e.g., 2.126.100]
- OS: [e.g., Windows 10]
- Browser (if web): [e.g., Chrome 120]

## Additional Context
[Any other relevant information]
```

### How to Suggest an Enhancement

1. **Go to Issues tab**
2. **Click "New Issue"**
3. **Use this template:**

```markdown
## Enhancement Description
Clear description of the suggested improvement.

## Motivation
Why is this enhancement needed? What problem does it solve?

## Proposed Solution
How would you implement this?

## Alternatives Considered
Other approaches you've thought about.

## Additional Context
[Screenshots, examples, or other relevant info]
```

---

## 📝 Submitting Changes

### Step 1: Make Your Changes

1. **Ensure your branch is up to date**
   ```bash
   git fetch origin
   git rebase origin/main
   ```

2. **Make your changes** following the style guidelines

3. **Test thoroughly** before submitting

### Step 2: Commit Your Changes

```bash
git add .
git commit -m "Brief description of changes"
```

**Commit Message Guidelines:**
- Use present tense: "Add feature" not "Added feature"
- Use imperative mood: "Move cursor to..." not "Moves cursor to..."
- Limit first line to 72 characters
- Reference issues when applicable: "Fixes #123"

**Example:**
```
Add monthly trend visualization to dashboard

Implements line chart showing profit and sales trends across
12 months. Helps identify seasonality patterns and business cycles.

Fixes #45
```

### Step 3: Push and Create Pull Request

1. **Push your branch**
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Go to GitHub** and create Pull Request

3. **Use this template for PR description:**

```markdown
## Description
Brief description of changes.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Dashboard improvement
- [ ] Performance improvement

## Related Issue
Fixes #(issue number)

## Changes Made
- Change 1
- Change 2
- Change 3

## Testing
How was this tested?

## Screenshots (if applicable)
[Before/After screenshots]

## Checklist
- [ ] My changes follow the style guidelines
- [ ] I have updated documentation
- [ ] I have tested these changes
- [ ] No new warnings generated
```

---

## 🎨 Style Guidelines

### Power BI Best Practices

1. **Naming Conventions**
   - Measures: PascalCase (e.g., `Total Sales`)
   - Columns: Clear and descriptive
   - Tables: Plural form (e.g., `Orders`, `Products`)

2. **DAX Coding Standards**
   ```dax
   -- Use meaningful variable names
   VAR NetProfit = SUM(Orders[Profit]) - SUM(Orders[Costs])
   
   -- Use line breaks for readability
   VAR Result = 
       CALCULATE(
           SUM(Orders[Amount]),
           Orders[Status] = "Completed"
       )
   
   RETURN Result
   ```

3. **Visual Design**
   - Use consistent color scheme (primary: blue, accent: orange)
   - Maintain alignment and spacing
   - Add clear titles and labels
   - Use appropriate chart types

4. **Documentation**
   - Comment complex DAX formulas
   - Document assumptions
   - Explain business logic

### Python/SQL Guidelines

1. **Python (PEP 8)**
   ```python
   # Clear variable names
   total_sales = df['sales'].sum()
   
   # Type hints where applicable
   def calculate_margin(sales: float, profit: float) -> float:
       return (profit / sales) * 100
   ```

2. **SQL**
   ```sql
   -- Use meaningful aliases
   SELECT 
       o.OrderID,
       o.OrderDate,
       SUM(od.Amount) AS TotalAmount
   FROM Orders o
   JOIN OrderDetails od ON o.OrderID = od.OrderID
   GROUP BY o.OrderID, o.OrderDate
   ```

### Markdown Guidelines

- Use proper heading hierarchy (H1 → H2 → H3)
- Include code blocks with language specification
- Add table of contents for long documents
- Use descriptive link text
- Keep lines under 80 characters

---

## 🔄 Review Process

1. **Automated Checks**
   - Code syntax validation
   - File format verification

2. **Manual Review**
   - Code quality assessment
   - Documentation review
   - Functionality testing

3. **Feedback**
   - Constructive comments
   - Suggestions for improvement
   - Questions for clarification

4. **Approval & Merge**
   - At least one approval required
   - All checks must pass
   - Branch is merged to main

---

## 💡 Development Tips

### Local Development Setup

```bash
# Clone repository
git clone https://github.com/YOUR-USERNAME/shopsphere-ecommerce-dashboard.git

# Navigate to project
cd shopsphere-ecommerce-dashboard

# Create feature branch
git checkout -b feature/your-feature

# Make changes and test
# ...

# Commit and push
git add .
git commit -m "Your commit message"
git push origin feature/your-feature
```

### Testing Your Changes

1. **Open dashboard file** in Power BI Desktop
2. **Test all visualizations** with sample data
3. **Verify filters** work correctly
4. **Check performance** - load times under 2 seconds
5. **Validate calculations** against source data
6. **Test on different screen sizes** (responsive design)

---

## 🏆 Recognition

Contributors will be:
- ⭐ Listed in README contributors section
- 🎖️ Mentioned in release notes
- 🤝 Acknowledged in community discussions

---

## ❓ Questions?

If you have questions:

1. **Check existing discussions** in GitHub Discussions
2. **Open a new discussion** for questions
3. **Email maintainers** for sensitive issues
4. **Tag @sapana14** for urgent matters

---

## 📚 Additional Resources

- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Markdown Guide](https://www.markdownguide.org/)
- [Power BI Best Practices](https://docs.microsoft.com/en-us/power-bi/)
- [DAX Function Reference](https://dax.guide/)

---

**Thank you for contributing to ShopSphere! Your efforts help make this project better for everyone.** 🚀
