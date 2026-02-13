# Quick Start: Creating and Pushing Your First Skill

This is a quick guide to help you create and push your first skill to this repository.

## 5-Minute Setup

### Step 1: Clone the Repository
```bash
git clone https://github.com/trimagiccube/skills.git
cd skills
```

### Step 2: Create a New Branch
```bash
git checkout -b my-first-skill
```

### Step 3: Create Your Skill
```bash
# Create a new folder for your skill
mkdir skills/my-skill-name

# Copy the template
cp template/SKILL.md skills/my-skill-name/SKILL.md

# Edit the skill file
nano skills/my-skill-name/SKILL.md  # or use your preferred editor
```

### Step 4: Edit Your SKILL.md
Replace the template content with your skill:

```markdown
---
name: my-skill-name
description: A clear description of what this skill does and when to use it.
---

# My Skill Name

Your instructions and guidelines here...
```

### Step 5: Commit and Push
```bash
# Stage your changes
git add skills/my-skill-name/

# Commit with a clear message
git commit -m "Add my-skill-name skill"

# Push to GitHub
git push origin my-first-skill
```

### Step 6: Create a Pull Request
1. Go to https://github.com/trimagiccube/skills
2. Click "Compare & pull request"
3. Fill in the details and submit!

## Example Skill

Here's a complete example of a simple skill:

```markdown
---
name: meeting-notes
description: Help create structured meeting notes with action items and decisions.
---

# Meeting Notes Skill

This skill helps you create well-structured meeting notes.

## Instructions

When creating meeting notes, follow this structure:

1. **Meeting Header**
   - Title
   - Date and time
   - Attendees

2. **Agenda Items**
   - List each topic discussed

3. **Key Decisions**
   - Document important decisions made

4. **Action Items**
   - Who is responsible
   - What needs to be done
   - When it's due

5. **Next Steps**
   - Follow-up items
   - Next meeting date

## Example Output

```
# Marketing Strategy Meeting
**Date:** February 13, 2024
**Attendees:** Alice, Bob, Carol

## Agenda
1. Q1 campaign review
2. Q2 planning

## Key Decisions
- Approved $50K budget for Q2
- Will focus on social media channels

## Action Items
- [ ] Alice: Draft Q2 campaign plan (Due: Feb 20)
- [ ] Bob: Research competitor campaigns (Due: Feb 18)
- [ ] Carol: Update budget spreadsheet (Due: Feb 15)

## Next Meeting
February 27, 2024 at 2:00 PM
```

## Tips

- Keep your skill focused on one specific task
- Write clear, actionable instructions
- Include examples
- Test your skill before submitting
- Read the full [CONTRIBUTING.md](./CONTRIBUTING.md) for details

## Need Help?

- 📖 Full guide: [CONTRIBUTING.md](./CONTRIBUTING.md)
- 🇨🇳 中文指南: [CONTRIBUTING.zh-CN.md](./CONTRIBUTING.zh-CN.md)
- 📚 Browse [existing skills](./skills) for inspiration
- ❓ Open an issue if you have questions

Happy skill creating! 🚀
