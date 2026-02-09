---
name: workflow
description: Full PR workflow from plan to completion. Use when given a asked to run the workflow.
---

# PR Workflow

Complete workflow from plan assignment to PR publication. Uses Mandatory Ralph Loops to ensure proper task completion.
**CRITICAL** THE FIRST STEP YOU TAKE MUST BE TO INITIATE YOUR RALPH LOOP

---

## Ralph Loop Requirement

- max_iterations: 50
- completion_promis: "COMPLETE"
- Instruction: "In order for this task to be completed successfully, the following steps must be completed in order:
    1. Create a branch using the 'branch' skill
    2. Complete the given plan, using the 'implementation-plan' skill
    3. Run the QA skill, if there have been relevant Frontend changes. Otherwise, skip this step.
    4. Review code with the 'wealthbox:jp-code-review' skill and address feedback. YOU MUST RUN THIS ON EVERY FILE! Address relevant feedback on your own.
    5. Use the 'simplify-pr' skill to reduce code complexity. If this causes a fresh start, return to step 1
    6. Ensure specs are passing on touched code
    7. Use the 'linters' skill to ensure code follows convention
    8. Rerun 'wealthbox:jp-code-review' and report outstanding issues to the user
    9. Use the 'document' skill to record learnings
    10. Use the 'pr' skill to publish a draft PR
    After completion of these steps, give the user your final report, tell them you are ready to grill/quiz them, and output 'COMPLETE'"

---

**Important Note** It is recommended that you add the step requirements of the Ralph Loop to your Todo List to ensure they are completed. You should still use your todo-list to keep track of the implementation plan as normal. For each step, make sure to include the name of the skill you should use with it.

---

## COMPLETE

PR is now ready for human review.
User may return with questions or comments that require code changes.

## Key Principles

1. **No shortcuts** - Complete each loop before moving to the next
2. **Quality gates** - Always initiate Ralph loop to ensure adherence to the workflow
3. **Learn for next time** - The goal of this skill is to keep the user out of the process except for the final review. Take note of any hiccups that require user intervention, and note them as things to fix with this skill.
