# AI Utilization Patterns

This is a collection of generative AI utilization patterns found effective for improving productivity and quality.

## Create Manual Test Cases for Development Branches

### Objective

- Quickly create manual test cases for a local development branch.

### Assumed AI Tools

- Tools that can operate with code context, such as Claude Code or Gemini CLI.

### Procedure

Assuming a PR submission to `develop`:

1. Pull the latest from `develop`.
2. Checkout the target branch locally.
3. Ask the AI to create manual test patterns for the differences with the `develop` branch.
4. Discuss the manual test patterns.
    - If unit tests are already implemented, have the AI consider the coverage of unit tests to create a high-value manual test suite.
5. Have the AI organize them into a matrix, etc.

### Examples

(Actual examples where using AI was better than without, or conversely, cases where it didn't work well.)

## Code Review According to Your Own Perspectives

### Objective

- Perform a review of a submitted PR (or self-review before submission) according to the code review perspectives defined within the team.

### Assumed AI Tools

- Tools that can operate with code context, such as Claude Code or Gemini CLI.

### Preparation

- Describe code review perspectives in the project root's `GEMINI.md` (or a separately managed memory file) and mention to refer to them during code review.

### Procedure

Assuming a PR submission to `develop`:

1. Pull the latest from `develop`.
2. Checkout the review target branch locally and pull to ensure it's up to date if necessary.
3. Ask the AI to review the differences between the current branch and the `develop` branch.
    - It's convenient to create a custom slash command for code review requests or save the prompt in a snippet tool.
        - Since custom slash commands depend on the tool, I personally recommend using a general-purpose snippet tool.

#### Prompt Example

```
Please perform a code review on the committed differences between the current local branch and the develop branch.
```

*Note 1: ⭐️ By saying "on the committed differences," you can limit the review to only the PR content (if there are uncommitted differences locally, they might be included in the review even if they aren't part of the PR).*

*Note 2: (Gemini CLI) Although `GEMINI.md` states "review perspectives" and "review focusing on those perspectives when instructed," there were cases where it didn't look at the perspectives well. In that case, providing the path to the MD file containing the code review perspectives as shown above will make it refer to it properly.*

#### Tips

- ⭐️ If there's a Jira ticket or Confluence page describing requirements or specifications, providing that URL as well allows the AI to review based on that context.
    - In this case, Atlassian MCP server configuration is required.

### Examples

(Examples of quick and good reviews or cases where the AI made points you hadn't thought of.)

## Brushing Up Documents for Better Clarity

### Objective

- Review documents written in Confluence (self-review is also possible).
- Perform reviews according to document review perspectives defined within the team.

### Assumed AI Tools

- Tools that can operate with code context, such as Claude Code or Gemini CLI.

### Preparation

- Describe document review perspectives in `GEMINI.md`, etc.

### Procedure

1. Provide the URL of the target Confluence page and ask for a document review.
    - It's convenient to save the prompt in a snippet tool for document review requests.

### Examples

(Examples where brushed-up materials were actually shown to others and the message was conveyed successfully.)

## Output Knowledge Gained from Tasks

After having an AI tool perform a task, if the content is useful enough to record, it's good to output it as knowledge upon completion.  
Request it like: `Please output what we just discussed in a general-purpose form in Markdown format.`

You can save it in your Obsidian as knowledge or summarize it in Confluence to share with the team.

## Ticket-Driven Development

Write tickets with well-organized requirements, etc., provide them to AI tools, and have conversations for catching up or implementation.

## Use AI for Design

### Tips

Design cannot be completed only at a desk; there is feedback from implementation to design.
Therefore, if you use Gemini for design, it's better to do it on Gemini CLI, which can access the code, rather than the browser version of Gemini.
For example, a design proposal that looks good at first glance might be inconvenient when considering the current code and could require significant man-hours.

On the other hand, since browser Gemini is easy to handle, you can use it for brainstorming and then use Gemini CLI for evaluating the implementation side of each proposal.

## Prevent Rework by Self-Reviewing Specifications

### Objective

- Prevent rework by performing a self-review before having the team or supervisors review specifications.

### Assumed AI Tools

- Tools that can operate locally, such as Claude Code or Gemini CLI.

### Preparation

- Create a memory file containing specification review perspectives.

### Procedure

- Use a tool like Gemini CLI that can refer to the above memory file, provide the document containing the specifications, and execute a prompt requesting a review.
    - For example, if you wrote specifications in Confluence, you can refer to the document just by giving the URL via Atlassian MCP.

### Examples

Example of improving the specification perspective memory file:

- It wasn't pointed out within the team, but when shared with higher-ups, comments came out about perspectives that should be considered, leading to a change in direction as a result of the consideration.
- Later, checking the memory file for specification perspectives revealed those perspectives were missing, so after adding them and having Gemini CLI review the old specification document, it was able to point out those perspectives.

## Quickly Understand Existing Code

### Objective

- Quickly understand unfamiliar existing code.

### Assumed AI Tools

- Tools that can operate locally, such as Claude Code or Gemini CLI.

### Preparation

- None in particular.

### Procedure

- Just ask about the code appropriately.
    - (Are there any particularly effective prompts?)

### Examples
