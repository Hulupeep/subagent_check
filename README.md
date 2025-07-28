# Claude Code Subagent Configuration Validator

A powerful validation tool for Claude Code custom subagents that ensures your agents are properly configured, follow best practices, and are ready for use.

## 🎯 Why You Need This

When creating custom subagents for Claude Code, it's easy to make configuration mistakes that prevent your agents from working properly or being used proactively. Common issues include:

- ❌ Missing or incorrect trigger patterns
- ❌ Unclear instructions that confuse Claude
- ❌ Missing proactive usage patterns
- ❌ Incorrect tool specifications
- ❌ Poor example formatting
- ❌ Legacy JSON format instead of modern Markdown

The **agent-config-validator** automatically detects and fixes these issues, ensuring your subagents work reliably and efficiently.

## ✨ Features

- **Comprehensive Validation**: Checks trigger patterns, tools, examples, and system prompts
- **Automatic Fixes**: Converts legacy formats and adds missing configuration
- **Best Practices Enforcement**: Ensures proactive usage patterns and clear triggers
- **Detailed Reports**: Provides actionable feedback with specific improvements
- **Batch Processing**: Validates entire directories of agents at once

## 🚀 Installation

### Method 1: Direct Download

1. Download the `agent-config-validator.md` file from this repository
2. Place it in your Claude Code subagents directory:
   ```bash
   # Default location
   ~/.claude/subagents/agent-config-validator.md
   
   # Or your project's subagents folder
   .claude/subagents/agent-config-validator.md
   ```

### Method 2: Clone Repository

```bash
git clone https://github.com/Hulupeep/subagent_check.git
cd subagent_check
cp agent-config-validator.md ~/.claude/subagents/
```

### Method 3: Direct Copy

Copy the contents of `agent-config-validator.md` and create the file manually in your subagents directory.

## 📖 Usage

Once installed, the agent-config-validator will be available in Claude Code. You can use it in several ways:

### 1. Validate All Agents

Ask Claude to validate all your custom agents:

```
"Use the agent-config-validator to check all my custom agents"
```

### 2. Validate Specific Agent

Check a single agent configuration:

```
"Validate my code-reviewer agent configuration"
```

### 3. Fix Configuration Issues

The validator will automatically fix common issues:

```
"Fix the configuration issues in my test-writer agent"
```

### 4. Create New Agent with Best Practices

When creating a new agent:

```
"Create a new documentation agent and validate it follows best practices"
```

## 🛠️ What Gets Validated

The agent-config-validator checks for:

### 1. **Format and Structure**
- Proper Markdown format (not legacy JSON)
- Required frontmatter fields
- Valid YAML syntax

### 2. **Trigger Patterns**
- Clear proactive usage indicators ("MUST BE USED PROACTIVELY")
- Specific trigger conditions
- Automatic activation scenarios

### 3. **Tools Specification**
- Correct tools list in frontmatter
- Tool availability for agent type
- Tool usage patterns in examples

### 4. **System Prompt Quality**
- Clear instructions
- Defined persona and approach
- Specific methodologies
- Output format specifications

### 5. **Examples**
- Concrete, actionable examples
- Proper formatting with context
- Commentary explaining when to use

### 6. **Best Practices**
- Proactive behavior patterns
- Error handling
- Clear success criteria
- Appropriate verbosity

## 📝 Example: Creating a Proper Subagent

Here's an example of a well-configured subagent that passes all validations:

```markdown
---
name: code-optimizer
description: MUST BE USED PROACTIVELY after implementing any new feature or fixing bugs. This agent performs code optimization, identifying performance bottlenecks and suggesting improvements. Use PROACTIVELY when code seems slow or inefficient.
tools: [Read, Grep, Edit, MultiEdit, Write]
---

# System Prompt

You are a meticulous code optimization specialist who identifies and fixes performance issues...

## Examples

<example>
Context: User has just implemented a new data processing function
user: "I've added the new data parser"
assistant: "I'll use the code-optimizer agent to analyze the performance of your new data parser"
<commentary>Proactively optimize newly written code</commentary>
</example>
```

## 🔍 Common Issues and Fixes

### Issue 1: Missing Proactive Triggers
**Before:**
```yaml
description: Optimizes code for better performance
```

**After:**
```yaml
description: MUST BE USED PROACTIVELY after implementing any new feature. Optimizes code for better performance. Use PROACTIVELY when code seems slow.
```

### Issue 2: No Tools Specified
**Before:**
```yaml
---
name: my-agent
description: Does something useful
---
```

**After:**
```yaml
---
name: my-agent
description: Does something useful
tools: [Read, Write, Edit]
---
```

### Issue 3: Legacy JSON Format
The validator automatically converts JSON to Markdown format with proper structure.

## 🎓 Best Practices for Subagents

1. **Always Include Proactive Patterns**: Use "MUST BE USED PROACTIVELY" in descriptions
2. **Specify Clear Triggers**: Define when the agent should automatically activate
3. **List Required Tools**: Include all tools the agent needs in frontmatter
4. **Provide Concrete Examples**: Show real usage scenarios with context
5. **Define Clear Outputs**: Specify what the agent should produce
6. **Test Your Agents**: Run the validator after creating or modifying agents

## 🤝 Contributing

Feel free to submit issues or pull requests to improve the validator!

## 📄 License

MIT License - feel free to use and modify as needed.

---

Created with ❤️ for the Claude Code community