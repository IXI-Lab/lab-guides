# Member Handbook: Daily Research Workflow

This handbook is your complete guide to contributing to research projects in the IXI Lab. It covers everything from the basic workflow to best practices for collaboration and code quality.

## The Golden Rule: Issues and Pull Requests

All work in this lab follows a simple but powerful principle: **Everything goes through Issues and Pull Requests.**

- **Issues:** Track tasks, report bugs, ask questions, propose ideas
- **Pull Requests:** Submit your work for review before it becomes part of the project

This system ensures:
- **Transparency:** Everyone can see what's being worked on
- **Quality:** All changes are reviewed before being accepted
- **Documentation:** Every change is tracked and documented
- **Collaboration:** Team members can work together effectively

## The Standard Workflow

Every piece of work, from fixing a typo to adding a new analysis, follows this five-step process:

### Step 1: Find or Create an Issue

1. **Go to your project repository's "Issues" tab**
2. **Look for existing issues** that match what you want to work on
3. **If no issue exists, create one:**
   - Click "New issue"
   - Choose the appropriate template (Bug Report, Feature Request, etc.)
   - Fill out the template completely
   - Add relevant labels
   - Assign the issue to yourself

**Example Issue Title:** "Add correlation analysis to the exploratory data analysis module"

### Step 2: Create a Branch

1. **From the repository's main page, click "main" and select "New branch"**
2. **Name your branch descriptively:**
   - Include the issue number
   - Use descriptive words
   - Use hyphens to separate words

**Example Branch Names:**
- `feature/12-add-correlation-analysis`
- `bugfix/15-fix-data-loading-error`
- `docs/8-update-readme-instructions`

### Step 3: Do the Work & Commit

1. **Clone the repository** (if you haven't already):
   ```bash
   git clone https://github.com/IXI-Lab/your-project.git
   cd your-project
   ```

2. **Switch to your branch:**
   ```bash
   git checkout feature/12-add-correlation-analysis
   ```

3. **Make your changes** following the lab's coding standards

4. **Commit frequently with clear messages:**
   ```bash
   git add .
   git commit -m "feat: Add correlation analysis function"
   git commit -m "test: Add unit tests for correlation analysis"
   git commit -m "docs: Update README with correlation analysis usage"
   ```

**Commit Message Format:**
```
type(scope): description

[optional body]

[optional footer]
```

**Types:** `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

### Step 4: Open a Pull Request

1. **Push your branch to GitHub:**
   ```bash
   git push origin feature/12-add-correlation-analysis
   ```

2. **Create a Pull Request:**
   - GitHub will prompt you to create a PR when you push a new branch
   - Click "Compare & pull request"

3. **Fill out the PR template:**
   - **Summary:** What does this PR do?
   - **Type of Change:** Select the appropriate category
   - **Related Issues:** Link to the issue this PR resolves (e.g., "Closes #12")
   - **Testing:** Describe how you tested your changes
   - **Checklist:** Complete all items in the checklist

4. **Assign reviewers:**
   - Assign your Team Leader as a reviewer
   - Add any other team members who should review the code

### Step 5: Participate in the Review

1. **Respond to feedback:**
   - Read all comments carefully
   - Make requested changes
   - Push updates to your branch (the PR will update automatically)

2. **Address concerns:**
   - If you disagree with a suggestion, discuss it respectfully
   - Be open to learning and improving your code

3. **Get approval:**
   - Once approved, your Team Leader will merge the PR
   - Your changes become part of the main project

## Data Management Policy

### Never Commit These to Git

- **Large data files** (> 10MB)
- **Raw data** (unless it's small sample data for testing)
- **Credentials** (API keys, passwords, tokens)
- **Personal information** (names, addresses, etc.)
- **Generated results** (figures, tables, model outputs)

### What to Commit

- **Source code** and scripts
- **Configuration files** (without sensitive data)
- **Documentation** and README files
- **Small sample datasets** for testing
- **Environment files** (requirements.txt, environment.yml)

### Handling Sensitive Data

1. **Use environment variables:**
   ```python
   import os
   api_key = os.getenv('API_KEY')
   ```

2. **Create example files:**
   - `config.example.yml` (template with dummy values)
   - `config.yml` (actual config, added to .gitignore)

3. **Store data externally:**
   - University servers
   - Cloud storage (with proper access controls)
   - Lab data management system

## Best Practices for Research Code

### Code Quality Standards

1. **Documentation:**
   - Every function should have a clear docstring
   - Follow Google or NumPy docstring conventions
   - Update README files when adding new features

2. **Type Hints:**
   ```python
   def calculate_correlation(data: pd.DataFrame, 
                           columns: List[str]) -> Dict[str, float]:
       """Calculate correlation between specified columns."""
   ```

3. **Testing:**
   - Write unit tests for all functions
   - Aim for at least 80% test coverage
   - Test edge cases and error conditions

4. **Style:**
   - Follow PEP 8 style guidelines
   - Use `black` for code formatting
   - Use `flake8` for linting

### Reproducibility Standards

1. **Environment Management:**
   - Always include `environment.yml` or `requirements.txt`
   - Pin specific versions of packages
   - Document any system dependencies

2. **Random Seeds:**
   ```python
   import numpy as np
   np.random.seed(42)  # For reproducibility
   ```

3. **Version Control:**
   - Commit frequently with descriptive messages
   - Use meaningful branch names
   - Keep commits focused and logical

### Analysis Workflow

1. **Data Loading:**
   ```python
   from src.utils import load_data, save_data
   
   # Load data
   data = load_data("data/raw/survey_data.csv")
   
   # Process data
   processed_data = process_survey_data(data)
   
   # Save results
   save_data(processed_data, "results/processed_survey_data.csv")
   ```

2. **Results Management:**
   - Save all results to the `results/` directory
   - Use timestamps in directory names
   - Include code to regenerate all results

3. **Documentation:**
   - Update project README with new features
   - Create analysis reports in the `manuscript/` directory
   - Document any data processing steps

## Collaboration Guidelines

### Communication

1. **Be Respectful:**
   - Always be constructive in comments and discussions
   - Respect different perspectives and experience levels
   - Celebrate good work and contributions

2. **Ask Questions:**
   - If you're unsure about something, create an issue
   - Don't hesitate to ask for help or clarification
   - Share your knowledge with others

3. **Share Progress:**
   - Update issues with your progress
   - Let your team know if you're blocked
   - Share interesting findings or insights

### Code Reviews

1. **As a Reviewer:**
   - Be constructive and educational
   - Focus on the code, not the person
   - Suggest improvements, don't just point out problems
   - Praise good work and practices

2. **As an Author:**
   - Be open to feedback and suggestions
   - Respond to all comments
   - Make requested changes promptly
   - Ask questions if you don't understand feedback

## Common Commands and Workflows

### Setting Up a New Project

```bash
# Clone the repository
git clone https://github.com/IXI-Lab/project-name.git
cd project-name

# Set up the environment
conda env create -f environment.yml
conda activate project-name

# Install the project package
pip install -e .
```

### Daily Workflow

```bash
# Start working on a new feature
git checkout -b feature/issue-number-description

# Make changes and commit
git add .
git commit -m "feat: Add new analysis function"

# Push and create PR
git push origin feature/issue-number-description
```

### Updating Your Work

```bash
# Get latest changes from main
git checkout main
git pull origin main

# Update your feature branch
git checkout feature/your-branch
git rebase main
```

## Getting Help

### When to Ask for Help

- **Technical problems** with Git, GitHub, or your development environment
- **Workflow questions** about the proper process for a specific task
- **Code review feedback** you don't understand
- **Project management** questions about organizing your work

### How to Get Help

1. **Check Documentation:**
   - Review this handbook and project README files
   - Search existing issues for similar questions

2. **Ask Your Team Leader:**
   - For project-specific questions
   - For guidance on your work
   - For help with technical problems

3. **Create an Issue:**
   - Use the "Question" template
   - Provide clear details about your problem
   - Include any relevant error messages

4. **Lab Meetings:**
   - Bring up general questions during lab meetings
   - Share your progress and challenges

## Success Metrics

You're doing well if you:

- Follow the Issues and Pull Requests workflow consistently
- Write clear, well-documented code
- Participate actively in code reviews
- Help other team members when you can
- Keep your work organized and reproducible
- Communicate effectively with your team

## Additional Resources

- **GitHub Documentation:** [GitHub Guides](https://guides.github.com/)
- **Git Cheat Sheet:** [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- **Python Style Guide:** [PEP 8](https://www.python.org/dev/peps/pep-0008/)
- **Research Best Practices:** [The Good Research Code Handbook](https://goodresearch.dev/)

---

**Remember:** The goal is not just to use GitHub, but to use it effectively to make our research better, more collaborative, and more reproducible. Every contribution, no matter how small, helps build a stronger research community.

**Happy researching!**
