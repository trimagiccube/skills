# Contributing to Skills Repository

Thank you for your interest in contributing to the Skills repository! This guide will help you set up the repository locally, create new skills, and push your code.

## Table of Contents
- [Getting Started](#getting-started)
- [Repository Setup](#repository-setup)
- [Creating a New Skill](#creating-a-new-skill)
- [Testing Your Skill](#testing-your-skill)
- [Submitting Your Contribution](#submitting-your-contribution)
- [Git Workflow](#git-workflow)

## Getting Started

### Prerequisites
- Git installed on your local machine
- A GitHub account
- Basic understanding of markdown and YAML

## Repository Setup

### 1. Fork the Repository (Optional)
If you want to contribute to the main repository, fork it first:
1. Visit https://github.com/trimagiccube/skills
2. Click the "Fork" button in the top right
3. This creates a copy under your GitHub account

### 2. Clone the Repository

Clone the repository to your local machine:

```bash
# If you forked the repository
git clone https://github.com/YOUR_USERNAME/skills.git

# Or clone the main repository directly
git clone https://github.com/trimagiccube/skills.git

# Navigate into the directory
cd skills
```

### 3. Set Up Remote (if forked)

If you forked the repository, set up the upstream remote:

```bash
git remote add upstream https://github.com/trimagiccube/skills.git
```

Verify your remotes:

```bash
git remote -v
```

You should see:
```
origin    https://github.com/YOUR_USERNAME/skills.git (fetch)
origin    https://github.com/YOUR_USERNAME/skills.git (push)
upstream  https://github.com/trimagiccube/skills.git (fetch)
upstream  https://github.com/trimagiccube/skills.git (push)
```

## Creating a New Skill

### 1. Create a Branch

Always create a new branch for your work:

```bash
git checkout -b my-new-skill
```

### 2. Create Your Skill Folder

Create a new folder in the `skills` directory:

```bash
mkdir skills/my-skill-name
```

### 3. Create SKILL.md File

Every skill requires a `SKILL.md` file with YAML frontmatter. Use the template:

```bash
cp template/SKILL.md skills/my-skill-name/SKILL.md
```

### 4. Edit Your Skill

Edit `skills/my-skill-name/SKILL.md` with your skill content:

```markdown
---
name: my-skill-name
description: A clear, complete description of what this skill does and when Claude should use it.
---

# My Skill Name

## Purpose
[Explain what this skill helps accomplish]

## Instructions
[Detailed step-by-step instructions that Claude will follow]

## Examples
- Example usage 1
- Example usage 2

## Guidelines
- Important guideline 1
- Important guideline 2

## Best Practices
- Best practice 1
- Best practice 2
```

### 5. Add Additional Resources (Optional)

You can include additional files in your skill folder:
- Scripts (Python, JavaScript, etc.)
- Configuration files
- Example data
- Documentation

Example structure:
```
skills/my-skill-name/
├── SKILL.md
├── examples/
│   └── example.md
└── scripts/
    └── helper.py
```

## Testing Your Skill

### Manual Testing

1. **In Claude Code:**
   - Register the local repository as a marketplace
   - Test your skill with various prompts

2. **In Claude.ai:**
   - Upload your skill folder
   - Test the skill with different scenarios

3. **Via API:**
   - Use the Skills API to test your skill
   - See the [Skills API Quickstart](https://docs.claude.com/en/api/skills-guide)

### Validation Checklist

- [ ] YAML frontmatter is valid
- [ ] `name` is lowercase with hyphens
- [ ] `description` clearly explains what the skill does
- [ ] Instructions are clear and actionable
- [ ] Examples demonstrate typical use cases
- [ ] Skill follows the patterns in [existing skills](./skills)

## Submitting Your Contribution

### 1. Check Your Changes

Review what you've changed:

```bash
git status
git diff
```

### 2. Stage Your Changes

Add your new skill to git:

```bash
# Add specific files
git add skills/my-skill-name/

# Or add all changes
git add .
```

### 3. Commit Your Changes

Write a clear commit message:

```bash
git commit -m "Add my-skill-name: brief description of what it does"
```

### 4. Push to GitHub

Push your branch to GitHub:

```bash
# If working on a fork
git push origin my-new-skill

# If working directly on the main repository
git push origin my-new-skill
```

### 5. Create a Pull Request

1. Go to the repository on GitHub
2. Click "Compare & pull request" button
3. Fill in the PR template with:
   - Clear title describing your skill
   - Description of what the skill does
   - Any testing you've performed
   - Screenshots or examples (if applicable)
4. Submit the pull request

## Git Workflow

### Basic Workflow

```bash
# 1. Create a new branch
git checkout -b feature/my-skill

# 2. Make your changes
# ... edit files ...

# 3. Stage changes
git add .

# 4. Commit changes
git commit -m "Descriptive commit message"

# 5. Push to remote
git push origin feature/my-skill

# 6. Create pull request on GitHub
```

### Keeping Your Fork Updated

```bash
# Fetch the latest changes from upstream
git fetch upstream

# Switch to main branch
git checkout main

# Merge upstream changes
git merge upstream/main

# Push updated main to your fork
git push origin main
```

### Making Changes After Review

If you receive feedback on your PR:

```bash
# Make the requested changes
# ... edit files ...

# Stage and commit
git add .
git commit -m "Address review feedback: specific changes made"

# Push to the same branch
git push origin my-new-skill
```

The pull request will automatically update with your new commits.

## Common Git Commands

### Viewing Status and History
```bash
git status              # See what's changed
git log                 # View commit history
git log --oneline       # Condensed history
git diff                # See unstaged changes
git diff --staged       # See staged changes
```

### Branch Management
```bash
git branch              # List local branches
git branch -a           # List all branches (including remote)
git checkout -b name    # Create and switch to new branch
git checkout name       # Switch to existing branch
git branch -d name      # Delete local branch
```

### Undoing Changes
```bash
git checkout -- file    # Discard changes to a file
git reset HEAD file     # Unstage a file
git reset --hard        # Discard all local changes (use carefully!)
```

## Tips for Success

1. **Read existing skills**: Browse the [skills folder](./skills) to understand patterns and best practices

2. **Start simple**: Begin with a straightforward skill before tackling complex ones

3. **Test thoroughly**: Ensure your skill works as expected in different scenarios

4. **Write clear descriptions**: The skill description is crucial for Claude to know when to use it

5. **Follow conventions**: Match the style and structure of existing skills

6. **Ask for help**: If you're stuck, open an issue or ask in discussions

## Resources

- [What are skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Using skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [How to create custom skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Agent Skills Specification](./spec)
- [Skill Template](./template)

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (Apache 2.0 for most skills, unless otherwise specified).

## Questions?

If you have questions about contributing, please:
- Check the [README.md](./README.md)
- Review [existing skills](./skills)
- Open an issue for discussion
- Refer to the [Agent Skills specification](./spec)

Thank you for contributing to make Skills better for everyone! 🎉
