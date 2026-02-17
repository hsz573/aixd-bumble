# AIXD Bumble - Project Documentation

## Tool Selection & Justification

### Selected Tool: Claude Code

**Claude Code** is the AI coding tool selected for this project, accessed through the VSCode extension.

### Why Claude Code?

1. **Native IDE Integration**
   - Seamless integration with VSCode, my primary development environment
   - Direct file access and editing without context switching
   - Built-in terminal integration for running commands

2. **Conversational Context Management**
   - Maintains conversation history and project context across sessions
   - Automatically compresses conversation as it approaches context limits
   - Persistent memory system (`.claude/memory/`) for learning patterns across conversations

3. **Specialized Frontend Design Capabilities**
   - Comes with the Impeccable design system plugin
   - Offers specialized skills like `/critique`, `/polish`, `/animate`, `/audit`
   - Aligns well with the Bumble dating app UI/UX focus of this project

4. **Safety & Control**
   - Permission-based tool execution gives me control over what changes are made
   - Clear distinction between local/reversible actions and risky operations
   - Git integration with safety protocols (no force pushes, no --no-verify)

5. **Multi-Step Task Management**
   - Built-in todo tracking for complex tasks
   - Can break down large features into manageable steps
   - Plan mode for getting approval before major implementations

## Project Definition

**Project:** Bumble: Crossed Paths

This project focuses on designing and implementing a user interface improvement for Bumble called Crossed Paths, which allows users to see potential matches after they leave a location in which they crossed paths.

**Design Brief:** [[Link to design brief document](https://docs.google.com/document/d/19csQiD_025vBT5wkUWzUcsdl-jukD0Yc2m0tIrqWkVA/edit?usp=sharing)]

### Project Goals
- Create production-grade frontend interfaces
- Implement responsive, accessible designs
- Focus on user delight and engagement
- Apply modern frontend design principles

## Version Control Strategy

### Tracking Changes

**Primary Tool:** Git with GitHub remote repository

**Branching Strategy:**
- `main` branch: production-ready, stable code
- Feature branches: `feature/[feature-name]` for new features

**Commit Practices:**
- Frequent, atomic commits with descriptive messages
- Follow conventional commit format when appropriate:
  - `feat:` for new features
  - `fix:` for bug fixes
  - `refactor:` for code refactoring
  - `docs:` for documentation changes

**Documentation:**
- This README is maintained and updated throughout the project
- Code changes are documented with clear commit messages
- Major decisions are tracked in conversation history with Claude Code

### Recovery Strategy

**If Something Goes Wrong:**

1. **Recent Changes (Not Yet Committed)**
   - Use `git status` to see what changed
   - Use `git diff` to review specific changes
   - Use `git restore [file]` to discard unwanted changes
   - Use `git stash` to temporarily save work-in-progress

2. **Bad Commits (Local Only)**
   - Use `git log` to identify the problematic commit
   - Use `git revert [commit-hash]` to create a new commit that undoes changes
   - Use `git reset --soft HEAD~1` to uncommit (if not pushed)
   - Never use `--hard` reset unless absolutely necessary

3. **Issues After Pushing**
   - Create a revert commit: `git revert [commit-hash]`
   - Push the revert to maintain clean history
   - Never force push to main branch

4. **Lost Code**
   - Use `git reflog` to find lost commits
   - Create recovery branch from reflog: `git checkout -b recovery [commit-hash]`
   - Cherry-pick specific commits if needed

5. **Merge Conflicts**
   - Carefully review both versions
   - Consult with Claude Code to resolve complex conflicts
   - Test thoroughly after resolution
   - Never blindly accept all incoming or current changes

6. **Prevention Measures**
   - Regular commits (at least after each complete feature/fix)
   - Push to remote frequently to have backup
   - Test before committing
   - Use branches for risky experiments
   - Keep main branch stable

**GitHub Safety Net:**
- Remote repository serves as backup
- All commits are pushed regularly
- Can clone fresh copy if local repository becomes corrupted
- GitHub history provides complete audit trail

## Prototype

**Live Demo:** [https://hsz573.github.io/aixd-bumble/](https://hsz573.github.io/aixd-bumble/)

**Tech Stack:** HTML, CSS, JavaScript (static site, no build step required)

**Figma Designs:** [AIXD Project 2](https://www.figma.com/design/I5ZpdUYMiBcSPUeH2jv6My/AIXD-Project-2)

### Screens Implemented

1. **Discover Entry** (`index.html`) — Main Bumble discover page with the Crossed Paths widget and horizontally scrollable recommended profiles
2. **Crossed Paths List View** (`crossed-paths.html`) — Shows matched and potential matched users you've crossed paths with, organized by Matches (clear photos) and Potential Matches (blurred photos with "Click to Reveal")
3. **Profile Overlay** (within `crossed-paths.html`) — Expanded profile view for a match (Mark), featuring interest tags, crossed paths location, and a Message button. Opens with a smooth slide-up animation

### Running Locally

Open `index.html` in any browser — no server or dependencies required.

## Project Status

**Current Phase:** Prototype Implementation

**Last Updated:** February 17, 2026

---

*This document is maintained as part of CMU AIXD coursework and will be updated throughout the project lifecycle.*