# Nested Claude Skills
This repo demonstrates a strategy to keep Claude on task when it comes to long plans or instructions.
## The Problem
Oftentimes, I have found that Claude skips or mishandles tasks that come during the review/publishing phase of its workflow since by that point it has accumulated a lot of context to keep track of.
## The Solution
By running Claude with an overarching 'parent' skill, it will add a predefined collection of specific skills to its todo list and put itself in a Ralph Loop that only terminates when all the todos have been completed.
## Example
In this particular example, I use the `plan-workflow` skill during the planning phase.

This skill ensures that "use the `workflow` skill" is part of the Agent's plan as the first step.

The `workflow` skill then lays out a todo list of specific skills that includes steps like QA, code simplification, and PR creation that Claude might skip on its own.

These skills are still independent enough to be called or used individually, but can be used as a collection in a set order by calling the parent skill:
```
  plan-workflow                                                                                                                                                                                                                    
  └── workflow                           
      ├── branch                                                                                                                                                                                                                   
      ├── implement-plan                 
      │   └── commit
      ├── qa
      ├── wealthbox:jp-code-review
      ├── simplify-pr
      │   └── fresh-start
      ├── linters
      ├── document
      ├── pr
      │   └── wealthbox:screenshot
      └── grill (optional - used after workflow completes)
```

With this particular workflow, I can give Claude a task to plan for, review the plan, then review the PR it creates. In only 3 interactions with the agent, I can expect code of a fairly high quality.

There are probably some improvements to be made to specific skills to increase code quality, but I've found this strategy to be pretty helpful so far as-is.

There are also improvements to be added in the form of new steps (ie calls to the Linear MCP to move tickets along/add comments). If added as new skills, Claude should follow these steps deterministically.
