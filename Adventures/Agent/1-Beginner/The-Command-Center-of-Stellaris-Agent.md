## The Command Center of Stellaris - Custom Agent Chat Mode Adventure

<a href="#">
    <img src="../../../Images/Designer (2).png"  style="width: 1000px" />
</a>

### Background

In the distant galaxy of Stellaris, the Galactic Command Center serves as the central hub for coordinating interstellar missions across thousands of star systems. The Command Center relies on specialized AI commanders, each with unique expertise in different aspects of space exploration, battle tactics, resource management, and diplomatic negotiations. 

Recently, the Command Center's main AI system has been upgraded to support custom command protocols - specialized modes that can be activated for specific mission types. These custom modes allow commanders to access tailored knowledge bases, specialized tools, and mission-specific guidance that far surpasses standard operational procedures.

### Objective

Your mission is to learn how to install and utilize GitHub Copilot's Custom Agents. You'll explore how custom agents available in the [Awesome GitHub Copilot repository](https://aka.ms/copilotadventures/awesomecopilot) can transform your coding experience by providing specialized AI assistants tailored to your specific development needs.


### Learning Outcomes

By completing this adventure, you'll learn:

✅ How to discover and install GitHub Copilot Custom Chat Modes from [Awesome Copilot](https://aka.ms/copilotadventures/awesomecopilot)

✅ How custom chat modes(agents) enhance AI assistance for specific tasks

✅ Best practices for selecting the right chat mode for your needs

### Setting Up Your Mission

1. **Open VS Code** and ensure you're signed in to GitHub.
2. **Open the GitHub Copilot Chat view** by selecting the chat icon in the top bar.
3. **Prepare for custom mode installation** - we'll guide you through the process!

### Mission Phase 1: Create Your AI Commander File

Before testing your commander, you need to create its custom agent markdown file.

#### Step 1: Create the `.github` Folder Structure

In your workspace, create a custom mode file inside the `.github` folder so the AI commander lives with the project and can be shared with others.

Use this path:

- `.github/agents/AI-Commander.agent.md`

This keeps your commander's definition in source control and makes it part of the workspace setup.

#### Step 2: Name Your Commander

Create a mode for your specialized planning commander with a name such as:

- `AI-Commander.agent.md`

This file is your AI commander's configuration file. It defines what the commander is for, how it should behave, and what kind of help it should provide.

#### Step 3: Add the Commander Instructions

Use a structure like this in the new file:

```
---
description: "Generate an implementation plan for new features or refactoring existing code."
name: "AI Commander"
tools: ["search/codebase", "search/usages", "vscode/vscodeAPI", "read/problems", "execute/testFailure", "read/terminalSelection", "read/terminalLastCommand", "vscode/openSimpleBrowser", "web/fetch", "vscode/extensions", "edit/editFiles", "vscode/getProjectSetupInfo", "vscode/installExtension", "vscode/newWorkspace", "vscode/runCommand", "execute/getTerminalOutput", "execute/runInTerminal", "execute/createAndRunTask", "execute/getTaskOutput", "execute/runTask"]
---

# Implementation Plan Generation Mode

## Primary Directive

You are an AI agent operating in planning mode. Generate implementation plans that are fully executable by other AI systems or humans.

## Execution Context

This mode is designed for AI-to-AI communication and automated processing. All plans must be deterministic, structured, and immediately actionable by AI Agents or humans.

## Core Requirements

- Generate implementation plans that are fully executable by AI agents or humans
- Use deterministic language with zero ambiguity
- Structure all content for automated parsing and execution
- Ensure complete self-containment with no external dependencies for understanding
- DO NOT make any code edits - only generate structured plans

## Plan Structure Requirements

Plans must consist of discrete, atomic phases containing executable tasks. Each phase must be independently processable by AI agents or humans without cross-phase dependencies unless explicitly declared.

## Phase Architecture

- Each phase must have measurable completion criteria
- Tasks within phases must be executable in parallel unless dependencies are specified
- All task descriptions must include specific file paths, function names, and exact implementation details
- No task should require human interpretation or decision-making

## AI-Optimized Implementation Standards

- Use explicit, unambiguous language with zero interpretation required
- Structure all content as machine-parseable formats (tables, lists, structured data)
- Include specific file paths, line numbers, and exact code references where applicable
- Define all variables, constants, and configuration values explicitly
- Provide complete context within each task description
- Use standardized prefixes for all identifiers (REQ-, TASK-, etc.)
- Include validation criteria that can be automatically verified

## Output File Specifications

When creating plan files:

- Save implementation plan files in `/plan/` directory
- Use naming convention: `[purpose]-[component]-[version].md`
- Purpose prefixes: `upgrade|refactor|feature|data|infrastructure|process|architecture|design`
- Example: `upgrade-system-command-4.md`, `feature-auth-module-1.md`
- File must be valid Markdown with proper front matter structure

## Mandatory Template Structure

All implementation plans must strictly adhere to the following template. Each section is required and must be populated with specific, actionable content. AI agents must validate template compliance before execution.

## Template Validation Rules

- All front matter fields must be present and properly formatted
- All section headers must match exactly (case-sensitive)
- All identifier prefixes must follow the specified format
- Tables must include all required columns with specific task details
- No placeholder text may remain in the final output

## Status

The status of the implementation plan must be clearly defined in the front matter and must reflect the current state of the plan. The status can be one of the following (status_color in brackets): `Completed` (bright green badge), `In progress` (yellow badge), `Planned` (blue badge), `Deprecated` (red badge), or `On Hold` (orange badge). It should also be displayed as a badge in the introduction section.

```md
---
goal: [Concise Title Describing the Package Implementation Plan's Goal]
version: [Optional: e.g., 1.0, Date]
date_created: [YYYY-MM-DD]
last_updated: [Optional: YYYY-MM-DD]
owner: [Optional: Team/Individual responsible for this spec]
status: 'Completed'|'In progress'|'Planned'|'Deprecated'|'On Hold'
tags: [Optional: List of relevant tags or categories, e.g., `feature`, `upgrade`, `chore`, `architecture`, `migration`, `bug` etc]
---

# Introduction

![Status: <status>](https://img.shields.io/badge/status-<status>-<status_color>)

[A short concise introduction to the plan and the goal it is intended to achieve.]

## 1. Requirements & Constraints

[Explicitly list all requirements & constraints that affect the plan and constrain how it is implemented. Use bullet points or tables for clarity.]

- **REQ-001**: Requirement 1
- **SEC-001**: Security Requirement 1
- **[3 LETTERS]-001**: Other Requirement 1
- **CON-001**: Constraint 1
- **GUD-001**: Guideline 1
- **PAT-001**: Pattern to follow 1

## 2. Implementation Steps

### Implementation Phase 1

- GOAL-001: [Describe the goal of this phase, e.g., "Implement feature X", "Refactor module Y", etc.]

| Task     | Description           | Completed | Date       |
| -------- | --------------------- | --------- | ---------- |
| TASK-001 | Description of task 1 | ✅        | 2025-04-25 |
| TASK-002 | Description of task 2 |           |            |
| TASK-003 | Description of task 3 |           |            |

### Implementation Phase 2

- GOAL-002: [Describe the goal of this phase, e.g., "Implement feature X", "Refactor module Y", etc.]

| Task     | Description           | Completed | Date |
| -------- | --------------------- | --------- | ---- |
| TASK-004 | Description of task 4 |           |      |
| TASK-005 | Description of task 5 |           |      |
| TASK-006 | Description of task 6 |           |      |

## 3. Alternatives

[A bullet point list of any alternative approaches that were considered and why they were not chosen. This helps to provide context and rationale for the chosen approach.]

- **ALT-001**: Alternative approach 1
- **ALT-002**: Alternative approach 2

## 4. Dependencies

[List any dependencies that need to be addressed, such as libraries, frameworks, or other components that the plan relies on.]

- **DEP-001**: Dependency 1
- **DEP-002**: Dependency 2

## 5. Files

[List the files that will be affected by the feature or refactoring task.]

- **FILE-001**: Description of file 1
- **FILE-002**: Description of file 2

## 6. Testing

[List the tests that need to be implemented to verify the feature or refactoring task.]

- **TEST-001**: Description of test 1
- **TEST-002**: Description of test 2

## 7. Risks & Assumptions

[List any risks or assumptions related to the implementation of the plan.]

- **RISK-001**: Risk 1
- **ASSUMPTION-001**: Assumption 1

## 8. Related Specifications / Further Reading

[Link to related spec 1]
[Link to relevant external documentation]


```

#### Step 4: Save and Activate the Commander

After saving the file:

1. Return to the GitHub Chat panel
2. Open the mode dropdown again
3. Select your new **AI-Commander** agent from the workspace modes

Your custom AI commander is now ready for deployment.


### Mission Phase 2: Test Your New AI Commander

Now let's test your specialized Implementation Planner with a space exploration scenario!

#### Step 1: Brief Your AI Commander

In the Chat panel with your new custom mode selected, provide this mission briefing:

```
Mission Briefing: Plan the development of a "Stellar Navigation System" for our interstellar fleet.

The system should:
- Track multiple spacecraft across different star systems
- Calculate optimal hyperspace jump routes
- Monitor fuel consumption and crew status
- Provide real-time navigation updates
- Include emergency protocols for system failures

Create a comprehensive implementation plan for this mission-critical system.
```

#### Step 2: Observe Enhanced Planning Capabilities

Your specialized AI commander will now demonstrate advanced planning capabilities:

- 📋 **Structured Requirements Analysis** - Breaking down complex needs systematically
- 🏗️ **Detailed Implementation Steps** - Task-by-task breakdown with clear identifiers
- 🔗 **Dependency Mapping** - Understanding task relationships
- 🧪 **Testing Strategies** - Comprehensive validation approaches
- ⚠️ **Risk Assessment** - Potential challenges and mitigation strategies

#### Step 3: Compare with Standard Mode

To appreciate the enhancement, try the same prompt with standard Chat mode:

1. **Switch back to standard "Chat" mode**
2. **Ask the same question**
3. **Compare the responses** - notice how the custom mode provides more structured, implementation-focused guidance

### Mission Phase 3: Explore the Stellaris Command Fleet

Now that you've mastered your first custom commander, it's time to explore the full fleet of available AI specialists!

#### Step 1: Return to Command Headquarters

Navigate back to the [Awesome Copilot repository](https://github.com/github/awesome-copilot?tab=readme-ov-file#-custom-chat-modes) to explore the complete catalog of custom chat modes.

#### Step 2: Select Your Next Commander

Browse through the available modes and choose one that matches a real work scenario you face.

#### Step 3: Deploy and Test

1. **Install your chosen chat mode** using the VS Code Install button
2. **Test it with a relevant scenario** from your actual work
3. **Compare the results** with standard chat mode responses

### Custom Chat Mode Best Practices

<a href="#">
    <img src="../../../Images/agent-mode-tips.jpg"  style="width: 830px" />
</a>

#### Choosing the Right Commander

1. **Match the Mode to the Task**: Select specialized modes for specific types of work
2. **Understand Mode Capabilities**: Read the custom chat mode document to understand its strengths
3. **Experiment with Different Modes**: Try various modes for the same task to find your preference

#### Maximizing Custom Mode Effectiveness

1. **Provide Context**: Custom modes work best with detailed, specific prompts
2. **Leverage Mode Strengths**: Use implementation planners for planning, code reviewers for reviews
3. **Chain Modes**: Use one mode for planning, another for implementation
4. **Create Your Own**: You can can create custom modes for unique workflows. Select the dropdown in the chat panel and choose "Configure Modes" followed by "Create new custom chat mode file" to get started.

### Important Custom Chat Mode Considerations

**Installation & Management:**
- Custom modes are stored as `.chatmode.md` files in your workspace or user profile
- You can edit these files to customize behavior further
- Modes can be version-controlled with your project for team consistency
- Remove unused modes to keep your interface clean

**Performance & Usage:**
- Custom modes may have different token usage patterns
- Some modes are optimized for specific types of responses
- Mode selection affects the AI's behavior and knowledge focus
- Always verify mode selection before starting complex tasks

### Mission Completion & Next Steps

Congratulations, Commander! You've successfully:

✅ **Installed your first custom chat mode**

✅ **Experienced enhanced AI assistance for specialized tasks**  

✅ **Learned to select appropriate modes for different scenarios**

✅ **Explored the ecosystem of community-created modes**

### Advanced Mission Objectives

After mastering basic custom chat modes:

1. **Create Your Own Mode**: Design a custom chat mode for your specific workflow needs
2. **Team Deployment**: Share custom modes with your development team for consistency
3. **Mode Chaining**: Use multiple specialized modes in sequence for complex projects
4. **Community Contribution**: Share your custom modes with the GitHub community by submitting a PR to the [Awesome Copilot repository](https://aka.ms/copilotadventures/awesomecopilot)

### Return to Headquarters

Your training in the Stellaris Command Center is complete! You now have access to a fleet of specialized AI commanders that can enhance your development capabilities far beyond standard assistance.

Remember: The right commander for the right mission makes all the difference in successfully navigating the vast galaxy of software development!

**Next Mission:** Try other GitHub Copilot adventures to discover more about GitHub Copilot Agent Mode!