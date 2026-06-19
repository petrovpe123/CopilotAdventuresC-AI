## The Clockwork Town of Tempora - Agent Mode Adventure

<a href="#">
    <img src="../../../Images/Designer (1).png"  style="width: 1000px" />
</a>

### Background

In the mechanical town of Tempora, everything operates on clockwork and precise timing. At the heart of the town is the Grand Clock Tower, responsible for keeping time for all the town's activities. However, over the years, some smaller clocks in the town have started to drift away from the accurate time.

### Objective

Your task is to create a system that checks all the clocks in the town and synchronizes them with the Grand Clock Tower. You'll be given a list of times from various clocks around the town, and you must determine how many minutes each clock is ahead or behind the Grand Clock Tower's time.

### Learning Outcomes

By completing this adventure with Agent Mode, you'll learn:

- ✅ How to give high-level instructions to an AI agent
- ✅ How Agent Mode breaks down complex tasks autonomously
- ✅ How to iterate and refine solutions with an AI pair programmer
- ✅ The power of autonomous coding assistance for complete projects
- ✅ Best practices for prompting Agent Mode effectively

### Setting Up Agent Mode

1. **Open VS Code** and ensure you're signed in to GitHub.
3. **Open the Chat view** by selecting the chat icon in the top bar.
4. **Select "Agent" mode** from the dropdown at the bottom of the Chat panel.

### Specifications

Now let's define the requirements for the clock synchronization system so that you can start using Agent Mode effectively!

1. **Clock Data:**
    - The clock times are provided in a 24-hour format.
    - The Grand Clock Tower is at 15:00.
    - Clock times around town:
        - Clock 1: 14:45
        - Clock 2: 15:05
        - Clock 3: 15:00
        - Clock 4: 14:40

2. **Time Analysis and Output:**
    - You need to determine how many minutes each clock is ahead or behind the Grand Clock Tower.
    - The result should be an array of integers representing the time difference in minutes. Positive values indicate the clock is ahead, and negative values indicate it's behind.

### Using Agent Mode to Solve the Adventure

#### Step 1: Give Agent Mode a High-Level Task

In the Chat panel with "Agent" mode selected, provide a comprehensive prompt like:

```
Create a complete clock synchronization system for the town of Tempora. The system should firstly create a folder "Tempora" and then inside:

1. Create a console application in JavaScript (or your preferred language)
2. Define the Grand Clock Tower time as 15:00
3. Store clock times for 4 clocks around town: 14:45, 15:05, 15:00, 14:40
4. Calculate how many minutes each clock is ahead or behind the Grand Clock Tower
5. Display the results clearly, showing positive values for clocks ahead and negative for clocks behind
6. Include proper error handling and clear documentation
7. Make the code readable and maintainable

Please create the project structure, write the code, and test it.
```



#### Step 2: Extend the System with Your Own Custom Prompt

Now that the basic system works, write your own custom prompt that lets the user pass in any new clock times they want. This makes the exercise reusable because the same prompt can be rerun with different time lists.

Use this prompt in the Chat panel with "Agent" mode selected.

```
Extend the existing Tempora clock synchronization system by adding any new clock times I provide.

When adding new clocks, do not replace the original 4 clocks. Keep the original data, append the new clocks to the list in the order I provide them, and rerun the full analysis for every clock.

New clocks to add:
- 14:06
- 14:55

Requirements:
1. Keep the original 4 clocks and append the new clocks I provide
2. Recalculate the minute difference for every clock against the Grand Clock Tower time of 15:00
3. Calculate how many minutes each clock is ahead or behind the Grand Clock Tower
4. Display the results clearly, showing positive values for clocks ahead and negative for clocks behind
5. Keep everything in a single file
```

For example, if you add `14:06` and `14:55`, those should be treated as extra town clocks, included in the same output table, and counted in the final summary.

#### Step 2.1: Create a Reusable Prompt File for This Extension

Save your extended prompt as a reusable file in a new folder `.github/prompts/` so you or anyone else can rerun it with different time lists:

1. Create `.github/prompts/tempora-extend.prompt.md`
2. Add this content:

```markdown
---
agent: agent
description: Extend the Tempora clock synchronization system with extra clocks
argument-hint: Provide one or more clock times separated by commas
---

# Extend the Tempora Clock System

Your goal is to extend the existing Tempora clock synchronization system with the extra clock times provided by the user.

## Step 1: Read the New Clock Times

Read the extra clock times from: `$ARGUMENTS`

Treat `$ARGUMENTS` as a comma-separated list of new town clocks, for example:
- `14:06, 14:55`
- `13:30, 15:45, 16:10`

## Step 2: Update the Clock List

1. Do not remove or replace the original clocks
2. Append the extra clock times from `$ARGUMENTS` in the order provided

## Step 3: Recalculate the Analysis

1. Use Grand Clock Tower time
2. Calculate minute differences for all clocks after the new ones are added
3. For each clock, identify whether it is ahead, behind, or synchronized
4. Print results as a table with columns: `Clock`, `Time`, `Difference`, `Status`
5. End with a summary showing the updated totals for clocks ahead, behind, and synchronized
6. Keep everything in a single file

## Step 4: Validate the Input

If any value in `$ARGUMENTS` is not a valid 24-hour time in `HH:MM` format, report it clearly and skip that invalid entry
```

3. Run it from Copilot Chat like this:

```
/tempora-extend 10:06, 18:55
```

Rerun the same prompt with an invalid list of times, for example `/tempora-extend 13:399, 15:465, 16:10`. Anaylze the way the agent behaves. 

#### Step 3: Watch Agent Mode Work

Agent Mode will autonomously:
- 🔍 **Analyze** your workspace and determine what files to create
- 📁 **Create** the necessary project structure
- 💻 **Write** the complete application code
- 🧪 **Test** the application by running it
- 🔧 **Fix** any issues that arise automatically

You'll see each step in the UI, showing every tool invocation.

#### Step 4: Interact and Refine

As Agent Mode works, you can:
- **Approve or modify** proposed changes
- **Ask for improvements**: "Can you add visual clock representations?"
- **Request explanations**: "Explain how the time calculation works"
- **Add features**: "Add the ability to input custom clock times"

#### Step 5: Explore Advanced Features

Once your basic system works, try asking Agent Mode to:

```
Enhance the clock system with these features:
1. Add a visual ASCII representation of each clock
2. Create unit tests for the time calculation logic
3. Add error handling for invalid time formats
4. Generate documentation explaining the system
```

### Expected Output Example

When your Agent Mode implementation is complete, running the application should produce output similar to the following. For the repeatable prompt above, the calculated differences and PASS/FAIL validation should match exactly on each run.

```
🕐 Tempora Clock Synchronization System 🕐
Grand Clock Tower Time: 15:00

Clock Analysis Results:
Clock 1 (14:45): -15 minutes (behind)
Clock 2 (15:05): +5 minutes (ahead)
Clock 3 (15:00): 0 minutes (synchronized)
Clock 4 (14:40): -20 minutes (behind)

Summary: 3 clocks need adjustment

🏛️ Enhanced Tempora Clock Analysis 🏛️

🗼 Grand Clock Tower:
    ⏰ 15:00
     12
   9  |  3
     6
  (3:00)

🏘️ Town Clocks:
--- Clock 1 ---
    ⏰ 14:45
     12
   9  |  3
     6
  (2:45)
⏰ 15 min BEHIND
```

**Verification Checklist:**
- ✅ Correctly calculates time differences: [-15, +5, 0, -20]
- ✅ Identifies 3 clocks needing adjustment
- ✅ Includes ASCII clock visualizations
- ✅ Shows clockwork/steampunk themed output
- ✅ Handles time format validation
- ✅ Provides clear status for each clock

### Agent Mode Tips

<a href="#">
    <img src="../../../Images/agent-mode-tips.jpg"  style="width: 830px" />
</a>

#### Effective Prompting Strategies

1. **Be Comprehensive**: Give Agent Mode the full context and all requirements upfront
2. **Specify Preferences**: Mention your preferred programming language, frameworks, or patterns
3. **Set Clear Goals**: Define what "done" looks like for your project
4. **Ask for Best Practices**: Request clean, maintainable, and well-documented code

#### Leverage Agent Mode's Autonomy

1. **Let it work**: Allow Agent Mode to complete multi-step tasks without interruption
2. **Review and approve**: Check the proposed changes before they're applied
3. **Iterate naturally**: Ask for improvements or modifications as needed
4. **Learn from the process**: Observe how Agent Mode structures and solves problems


### Important Agent Mode Considerations

**Tool Confirmation & Limits:**
- Agent Mode requires your confirmation before invoking tools or running commands
- You can interrupt or pause requests at any time
- Always review suggested edits before accepting

### Troubleshooting Agent Mode

If Agent Mode isn't working as expected:

**Common Issues & Solutions:**

🔧 **Agent not creating files**
- Check your workspace permissions
- Ensure you're in a valid project directory
- Approve file creation when prompted

🔧 **Incomplete implementation**
- Your prompt may need more detail - be more comprehensive
- Add specific success criteria and requirements
- Include examples of expected behavior

🔧 **Tool confirmation needed**
- Agent Mode requires your approval for tool usage
- Click "Allow" when prompted for file operations
- Review what tools will be used before approving

🔧 **Agent stops mid-task**
- May have hit the 128 tool limit per request
- Break complex tasks into smaller chunks
- Continue with a follow-up prompt

**Setup Verification:**
1. **Check VS Code version**: Ensure you're using a recent version of VS Code
2. **Verify settings**: Confirm `chat.agent.enabled` is checked
3. **Check mode selection**: Make sure "Agent" is selected in the Chat dropdown
4. **Sign in**: Ensure you're signed in to GitHub with Copilot access
5. **Tool Permissions**: Approve tool usage when prompted

**Pro Tips:**
- Start with smaller tasks to get familiar with Agent Mode
- Be very specific about what "done" looks like
- Include testing and validation requirements in your prompts

### What's Next?

After trying out Agent Mode with this adventure:

1. Try the **Intermediate adventures** using Agent Mode for more complex scenarios
2. Experiment with **custom tools and extensions** that integrate with Agent Mode
3. Use Agent Mode for **real projects** - it excels at creating complete applications
4. Share your experience and **provide feedback** to help improve Agent Mode

Remember: Agent Mode is your autonomous coding partner. Give it clear goals, let it work, and iterate together to build amazing software!