
# Slide Group: Claude Code basics

## Slide subtitle: Terminal vs GUI
### Slide Item: Command line
### Slide Item: Native VSCode GUI extension
### Slide Item: Native JetBrains extension (beta)
## Slide subtitle: Model - Models
### Slide Item: `/model`
### Slide Item: Sonett 4.5
#### subitem To code
#### subitem 200k vs 1m tokens
### Slide Item: Opus
#### subitem Thinking model
#### subitem To plan - default in plan mode
#### subitem More expensive and slower
### Slide Item: Modes:
#### subitem `Tab key`
#### subitem Thinking/normal
## Slide subtitle: Commands
### Slide Item: Where to put them
### Slide Item: Parameterization
### Slide Item: Usage `/my-command`
## Slide subtitle: Subagents
### Slide Item: `/agents`
### Slide Item: Orchestrated by main agent
### Slide Item: Isolated from main context
### Slide Item: Example:
#### subitem Gather requirements where you can use Context7
#### subitem Commit message subagent to make commits
## Slide subtitle: Hooks
### Slide Item: Enforce test, linter, etc execution with 100% pass
### Slide Item: Prevent editing what's locked, ie integration tests
## Slide subtitle: Tool usage
### Slide Item: Bash commands
### Slide Item: MCP Servers
#### subitem claude mcp add --transport http sentry <https://mcp.sentry.dev/mcp>
#### subitem Manually edit `.claude/.mcp.json`
## Slide subtitle: Permission rules
### Slide Item: `/permission`
### Slide Item: `Manually edit``.claude/settings.json or ~/.claude.json`

# Slide Group: Basic Prompting

## Slide subtitle: Action + Location + Detail
## Slide subtitle: Information Dense Keywords:
### Slide Item: Keywords:
#### subitem Create
#### subitem Update
#### subitem Mirror
#### subitem Search
### Slide Item: Video link
## Slide subtitle: Mid-level prompt (not too high, not too low)
### Slide Item: Video link
## Slide subtitle: Provide Examples
### Slide Item: Existing tests
### Slide Item: Expercted transformation from → to
### Slide Item: Starting of a list, 1, 3, 5, 7...
## Slide subtitle: Define Output Format
### Slide Item: Defined json/yaml/etc syntax
### Slide Item: Not always follow it - enforce with validation → later
## Slide subtitle: Further techniques:
### Slide Item: Define edge cases
### Slide Item: Ask the agent to improve your prompt
### Slide Item: Ask to ask back questions to clarify
### Slide Item: Deep research in ChatGPT
### Slide Item: Keywords: think, think hard, think harder, ultrathink

# Slide Group: Basic Context Engineering

## Slide subtitle: Good Context
### Slide Item: Small
### Slide Item: Contains only what's in scope
### Slide Item: Keep track of context usage
#### subitem cli tool or gui
#### subitem `/context`
## Slide subtitle: Context Management
### Slide Item: Resuming previous
#### subitem `/resume`
### Slide Item: Compacting
#### subitem `/compact`
#### subitem What it does
#### subitem Avoid it
### Slide Item: Clearing / Starting new
#### subitem `/clear`  or `start new claude`
#### subitem When to create new context
#### subitem What to add to the new context from the previous one
## Slide subtitle: Model focus
### Slide Item: Beginnging and especially end of context
## Slide subtitle: Memory
### Slide Item: [CLAUDE.md](https://www.anthropic.com/engineering/claude-code-best-practices)
### Slide Item: Common bash commands
### Slide Item: Core files and utility functions
### Slide Item: Coding standards&rules
### Slide Item: Bulding&Testing instructions
### Slide Item: Repository etiquette (e.g., branch naming, merge vs. rebase, etc.)
### Slide Item: Developer environment setup (e.g., pyenv use, which compilers work)
### Slide Item: Any unexpected behaviors or warnings particular to the project
### Slide Item: Other information you want Claude to remember
### Slide Item: API References and dependency documentation links
### Slide Item: Add CLAUDE.md to important subfolders also
## Slide subtitle: Referencing files
### Slide Item: `@filename.md`
### Slide Item: Needed on bigger projects with lot of files
## Slide subtitle: Adding folders to scope
### Slide Item: `/add-dir`
## Slide subtitle: Don't change by hand if possible
### Slide Item: Let it fix the issue
### Slide Item: Let it execute the bash script it wrote
### Slide Item: If you really need to, tell about the changes (ie link files) and reasons
## Slide subtitle: RAG - Retrieve Augment Generate
### Slide Item: File based
### Slide Item: MCP servers - later

# Slide Group: Workflow

## Slide subtitle: Plan
### Slide Item: Iterative planning in markdown
### Slide Item: Involve AI in plan generation
### Slide Item: Define
#### subitem High-Level Objective
##### sub-subitem: Describe what the feature or system does — the outcome or purpose.
#### subitem Mid-Level Breakdown
##### sub-subitem: Break the high-level goal into concrete, deliverable components — the building blocks.
#### subitem Implementation Notes
##### sub-subitem: These define technical details, rules, and constraints for how the work should be done.
#### subitem Context (Input (starting point) + Output)
##### sub-subitem: Define the boundaries of the codebase visible to the AI — what it can read and should modify.
### Slide Item: Request to clarify questions (multiple iterations)
### Slide Item: Human review
## Slide subtitle: Low-level tasks
### Slide Item: The step-by-step implementation plan — ordered, explicit tasks that the reasoning model can execute.
#### subitem Built in vs markdown based
##### sub-subitem: Built in for small task, few steps
##### sub-subitem: Markdown for bigger
#### subitem Reasonable, demoable size for each task -
##### sub-subitem: ??????????????
#### subitem Execution order
#### subitem Human review
## Slide subtitle: Execute
### Slide Item: One task at a time
### Slide Item: Separate context when possible
### Slide Item: Optional improvement: Write tests first (TDD) OR write tests and code together
## Slide subtitle: Validation
### Slide Item: Best if it can be done by the model itself (ie test running, script execution, etc)
### Slide Item: Reflection
#### subitem test runs
#### subitem linters
#### subitem type check
#### subitem build result
#### subitem Static analysis reports
#### subitem screenshots
#### subitem error logs
#### subitem diffs
#### subitem HTTP response codes
#### subitem load times
#### subitem HAR file diffs
#### subitem Dataset shape or schema mismatches
#### subitem CSV/JSON parse errors
### Slide Item: Ask for a Demo (even partial results)
#### subitem Self-evaluated demos are the best
#### subitem Quick human evaluation
### Slide Item: Hooks - later
### Slide Item: Larger tasks:
#### subitem Ask to Double check if the implementation meets the requirements
## Slide subtitle: Code Review
### Slide Item: Automatic review
#### subitem PromptCollection `/code-review`  command
#### subitem `/review`  - only for Github
### Slide Item: Human review
#### subitem Never trust AI generated code especially in production
## Slide subtitle: Commit/rewind
### Slide Item: If good, commit after each task
### Slide Item: If not, ask to modify or `/rewind`  to previous checkpoint
