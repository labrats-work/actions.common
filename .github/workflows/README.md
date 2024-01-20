As of the time of this writing, there are a few limitations around reusable workflows:

- While you can call a reusable workflow from another reusable workflow, you can only do this nesting to a depth of four calls.
- A caller workflow can call a maximum of 20 reusable workflows. Nested workflow calls count toward this limit as well.
- Environment variables set in an env context in the caller workflow are not propagated to the called workflow.
- You can’t reference a reusable workflow that’s in a separate private repository. Only workflows in the same private repository can reference a reusable workflow in that repository.