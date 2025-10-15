# 1. Workshop

**Source:** [Confluence Page](https://confluence.doclerholding.com/pages/viewpage.action?pageId=509739313)
**Space:** AI Transformation (AITT)
**Version:** 19

---

## Topics

### Claude Code basics

* Terminal vs GUI
  + Command line
  + Native VSCode GUI extension
  + Native JetBrains extension (beta)
* Model - Models
  + `/model`
  + Sonett 4.5
    - To code
    - 200k vs 1m tokens
  + Opus
    - Thinking model
    - To plan - default in plan mode
    - More expensive and slower
  + Modes:
    - `Tab key`
    - Thinking/normal
* Commands
  + Where to put them
  + Parameterization
  + Usage `/my-command`
* Subagents
  + `/agents`
  + Orchestrated by main agent
  + Isolated from main context
  + Example:
    - Gather requirements where you can use Context7
    - Commit message subagent to make commits
* Hooks
  + Enforce test, linter, etc execution with 100% pass
  + Prevent editing what's locked, ie integration tests
* Tool usage
  + Bash commands
  + MCP Servers
    - claude mcp add --transport http sentry <https://mcp.sentry.dev/mcp>
    - Manually edit `.claude/.mcp.json`
* Permission rules
  + `/permission`
  + `Manually edit``.claude/settings.json or ~/.claude.json`

### Basic Prompting

* Action + Location + Detail
* Information Dense Keywords:
  + Keywords:
    - Create
    - Update
    - Mirror
    - Search
  + Video link
* Mid-level prompt (not too high, not too low)
  + Video link
* Provide Examples
  + Existing tests
  + Expercted transformation from → to
  + Starting of a list, 1, 3, 5, 7...
* Define Output Format
  + Defined json/yaml/etc syntax
  + Not always follow it - enforce with validation → later
* Further techniques:
  + Define edge cases
  + Ask the agent to improve your prompt
  + Ask to ask back questions to clarify
  + Deep research in ChatGPT
  + Keywords: think, think hard, think harder, ultrathink

### Basic Context Engineering

* Good Context
  + Small
  + Contains only what's in scope
  + Keep track of context usage
    - cli tool or gui
    - `/context`
* Context Management
  + Resuming previous
    - `/resume`
  + Compacting
    - `/compact`
    - What it does
    - Avoid it
  + Clearing / Starting new
    - `/clear`  or `start new claude`
    - When to create new context
    - What to add to the new context from the previous one
* Model focus
  + Beginnging and especially end of context
* Memory
  + [CLAUDE.md](https://www.anthropic.com/engineering/claude-code-best-practices)
  + Common bash commands
  + Core files and utility functions
  + Coding standards&rules
  + Bulding&Testing instructions
  + Repository etiquette (e.g., branch naming, merge vs. rebase, etc.)
  + Developer environment setup (e.g., pyenv use, which compilers work)
  + Any unexpected behaviors or warnings particular to the project
  + Other information you want Claude to remember
  + API References and dependency documentation links
  + Add CLAUDE.md to important subfolders also
* Referencing files
  + `@filename.md`
  + Needed on bigger projects with lot of files
* Adding folders to scope
  + `/add-dir`
* Don't change by hand if possible
  + Let it fix the issue
  + Let it execute the bash script it wrote
  + If you really need to, tell about the changes (ie link files) and reasons
* RAG - Retrieve Augment Generate
  + File based
  + MCP servers - later

### Workflow

* Plan
  + Iterative planning in markdown
  + Involve AI in plan generation
  + Define
    - High-Level Objective
      * Describe what the feature or system does — the outcome or purpose.
    - Mid-Level Breakdown
      * Break the high-level goal into concrete, deliverable components — the building blocks.
    - Implementation Notes
      * These define technical details, rules, and constraints for how the work should be done.
    - Context (Input (starting point) + Output)
      * Define the boundaries of the codebase visible to the AI — what it can read and should modify.
  + Request to clarify questions (multiple iterations)
  + Human review
* Low-level tasks
  + The step-by-step implementation plan — ordered, explicit tasks that the reasoning model can execute.
    - Built in vs markdown based
      * Built in for small task, few steps
      * Markdown for bigger
    - Reasonable, demoable size for each task -
      * ??????????????
    - Execution order
    - Human review
* Execute
  + One task at a time
  + Separate context when possible
  + Optional improvement: Write tests first (TDD) OR write tests and code together
* Validation
  + Best if it can be done by the model itself (ie test running, script execution, etc)
  + Reflection
    - test runs
    - linters
    - type check
    - build result
    - Static analysis reports
    - screenshots
    - error logs
    - diffs
    - HTTP response codes
    - load times
    - HAR file diffs
    - Dataset shape or schema mismatches
    - CSV/JSON parse errors
  + Ask for a Demo (even partial results)
    - Self-evaluated demos are the best
    - Quick human evaluation
  + Hooks - later
  + Larger tasks:
    - Ask to Double check if the implementation meets the requirements
* Code Review
  + Automatic review
    - PromptCollection `/code-review`  command
    - `/review`  - only for Github
  + Human review
    - Never trust AI generated code especially in production
* Commit/rewind
  + If good, commit after each task
  + If not, ask to modify or `/rewind`  to previous checkpoint

### Overcoming hallucinations

* Restart when went nuts

### Use cases



### Advanced techniques

* Debugging techniques
  + Explain before fix: explain before implement
  + Diff-based debugging
* Parallel working
  + Git worktree

## Methodology

* Enforce attention:
  + Randomly guys showing their examples
  + Random guys show bigger task results
* Micro learning
* Homeworks

## Ways of educating

* Find materials
  + Existing IndyDevDan videos
  + Udemy
* Frontal education
* Workshops
* Delegate to guild members
