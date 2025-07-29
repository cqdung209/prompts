# VS Code Copilot Chat Modes, Instructions & Prompts Setup

A comprehensive collection of custom chat modes, instruction files, and prompts for GitHub Copilot in Visual Studio Code, designed to enhance AI-assisted development workflows with specialized domain expertise.

## Overview

This repository contains three types of Copilot customizations that extend GitHub Copilot's capabilities in VS Code:

- **Chat Modes**: Specialized AI assistants with custom behavior and context
- **Instructions**: Reusable instruction templates for consistent AI guidance  
- **Prompts**: Pre-defined prompts for common development tasks

These specialized configurations provide domain-specific guidance for database development, debugging, code reviews, and other specialized tasks.

## Types of Copilot Customizations

### 🤖 Chat Modes
Custom instruction sets that modify how GitHub Copilot behaves in specific contexts. They allow you to:
- Create specialized AI assistants for different domains (SQL, debugging, architecture, etc.)
- Define specific tools and models to use
- Set consistent behavior patterns for repetitive tasks
- Maintain context-aware conversations

### 📋 Instructions
Reusable instruction templates that provide consistent guidance across different contexts:
- Define coding standards and best practices
- Set up domain-specific rules and constraints
- Create templates for code reviews and documentation
- Establish consistent output formats

### 💡 Prompts
Pre-defined prompts for common development scenarios:
- Quick access to frequently used questions
- Standardized request formats
- Template prompts for specific tasks
- Shareable prompt collections for teams

## Quick Setup Guide

### 1. Creating a New Chat Mode

1. **Open VS Code**
2. **Open Command Palette**: `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
3. **Run Command**: Type and select `Chat: New Mode File`
4. **Choose Location**: Select `User Data Folder` (recommended for personal use) or `Workspace` (for project-specific modes)
5. **Name Your Mode**: Enter a descriptive name (e.g., `debug-sp`, `sql-optimizer`, `code-reviewer`)
6. **Edit the File**: Paste your custom instructions in the generated `.chatmode.md` file

### 2. Creating Instructions

1. **Open VS Code**
2. **Open Command Palette**: `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
3. **Run Command**: Type and select `Chat: New Instruction File`
4. **Choose Location**: Select `User Data Folder` (recommended for personal use) or `Workspace` (for project-specific instructions)
5. **Name Your Instruction**: Enter a descriptive name (e.g., `T-SQL-Rules`, `Code-Review-Standards`, `API-Documentation`)
6. **Edit the File**: Paste your instruction content in the generated `.instructions.md` file

### 3. Creating Prompts

1. **Open VS Code**
2. **Open Command Palette**: `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
3. **Run Command**: Type and select `Chat: New Prompt File`
4. **Choose Location**: Select `User Data Folder` (recommended for personal use) or `Workspace` (for project-specific prompts)
5. **Name Your Prompt**: Enter a descriptive name (e.g., `SQL-Performance-Check`, `Code-Optimization`, `Bug-Analysis`)
6. **Edit the File**: Write your prompt content in the generated `.prompt.md` file

### Chat Mode File Structure

A chat mode file follows this basic structure:

```markdown
---
description: 'Brief description of what this mode does'
tools: [tool1, tool2]  # Optional: specific tools to enable
model: 'Model Name'    # Optional: specific model to use
---

Your detailed instructions and prompts go here...
```

## Available Customizations

### 🔧 Chat Modes

#### Debug SP (Stored Procedure Debugger)
**File**: `chatmodes/debug_sp.chatmode.md`

An enterprise-level SQL Server stored procedure debugging assistant that:
- Analyzes stored procedure dependencies recursively
- Performs logical, data, and performance analysis
- Generates comprehensive debug reports with fix suggestions
- Safely handles data modifications with transaction wrapping

**Usage**: Use when debugging complex SQL Server stored procedures or investigating performance issues.

## Setup Instructions

### Method 1: Using VS Code Command Palette (Recommended)

#### For Chat Modes:
1. Open VS Code
2. Press `Ctrl + Shift + P` to open Command Palette
3. Type and select `Chat: New Mode File`
4. Choose storage location:
   - **User Data Folder**: Available across all VS Code workspaces
   - **Workspace**: Only available in current project
5. Enter mode name (e.g., `debug-sp`)
6. VS Code creates a `.chatmode.md` file
7. Replace the template content with your custom instructions

#### For Instructions:
1. Open VS Code
2. Press `Ctrl + Shift + P` to open Command Palette
3. Type and select `Chat: New Instruction File`
4. Choose storage location:
   - **User Data Folder**: Available across all VS Code workspaces
   - **Workspace**: Only available in current project
5. Enter instruction name (e.g., `T-SQL-Rules`)
6. VS Code creates a `.instructions.md` file
7. Add your instruction content following the recommended structure

#### For Prompts:
1. Open VS Code
2. Press `Ctrl + Shift + P` to open Command Palette
3. Type and select `Chat: New Prompt File`
4. Choose storage location:
   - **User Data Folder**: Available across all VS Code workspaces
   - **Workspace**: Only available in current project
5. Enter prompt name (e.g., `SQL-Performance-Check`)
6. VS Code creates a `.prompt.md` file
7. Add your prompt collection following the recommended structure

### Method 2: Manual File Creation

#### File Locations:
Navigate to your VS Code user data folder:
- **Windows**: `%APPDATA%\Code\User\`
- **macOS**: `~/Library/Application Support/Code/User/`
- **Linux**: `~/.config/Code/User/`

#### Create Folders:
1. Create folders if they don't exist:
   - `chatmodes/` for chat mode files
   - `instructions/` for instruction files
   - `prompts/` for prompt files
2. Create files with appropriate extensions:
   - `.chatmode.md` for chat modes
   - `.instructions.md` for instructions
   - `.prompt.md` for prompts

### Method 3: Workspace-Specific Setup

1. In your project root, create a `.vscode` folder
2. Inside `.vscode`, create subfolders:
   - `chatmodes/` 
   - `instructions/`
   - `prompts/`
3. Add your files with appropriate extensions
4. These customizations will only be available in this workspace

## File Organization

```
📁 prompts/
├── 📁 chatmodes/          # Custom chat mode definitions
│   └── debug_sp.chatmode.md
├── 📁 instructions/       # Reusable instruction templates
└── 📁 prompts/           # General purpose prompts
```

## Best Practices

### Writing Effective Chat Modes

1. **Clear Description**: Start with a concise description in the frontmatter
2. **Specific Instructions**: Be explicit about expected behavior and output format
3. **Context Setting**: Define the role and expertise level clearly
4. **Safety Measures**: Include safeguards for destructive operations
5. **Output Format**: Specify desired response structure (Markdown, code blocks, etc.)

### Naming Conventions

- Use lowercase with hyphens: `debug-sp.chatmode.md`
- Be descriptive: `sql-performance-analyzer.chatmode.md`
- Include domain: `frontend-code-reviewer.chatmode.md`

### Version Control

- Keep chat modes in version control for team sharing
- Document changes in commit messages
- Consider branching for experimental modes

## Usage Examples

### Activating Chat Modes

1. Open Copilot Chat panel (`Ctrl + Shift + I`)
2. Click the mode selector (usually shows "General")
3. Select your custom mode from the dropdown
4. Start chatting with your specialized assistant

### Sample Interactions

**With Debug SP Mode**:
```
@copilot /debug-sp dbo.GetCustomerOrders
```

**General Chat with Mode Active**:
```
Can you analyze this stored procedure for performance issues?
[paste your SQL code]
```

## Troubleshooting

### Chat Mode Not Appearing
- Ensure file has `.chatmode.md` extension
- Check frontmatter syntax (YAML between `---` markers)
- Restart VS Code to reload modes
- Verify file location (User Data vs Workspace)

### General Issues
- **Mode/Instruction Not Working as Expected**:
  - Review instruction clarity and specificity
  - Check for conflicting instructions
  - Test with simpler examples first
  - Validate YAML frontmatter syntax (for chat modes)

- **Files Not Loading**:
  - Check file extensions are correct
  - Verify folder structure matches expectations
  - Ensure no syntax errors in file content
  - Try moving files to User Data folder instead of workspace

- **Performance Issues**:
  - Limit number of active customizations
  - Keep instruction files concise and focused
  - Remove unused or duplicate files

## Contributing

When adding new customizations:

### For Chat Modes:
1. Follow the established file structure with proper frontmatter
2. Include comprehensive documentation and examples
3. Test thoroughly with various inputs and scenarios
4. Add usage examples and expected behaviors
5. Update this README with new modes

### General Guidelines:
- Follow established naming conventions
- Keep files focused on single purposes
- Document dependencies and requirements
- Include version information when relevant
- Test across different VS Code configurations

## Related Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [VS Code Copilot Chat](https://code.visualstudio.com/docs/copilot/copilot-chat)
- [Prompt Engineering Best Practices](https://platform.openai.com/docs/guides/prompt-engineering)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For issues or questions:
- Create an issue in this repository
- Check existing chat modes for examples
- Refer to VS Code Copilot documentation
