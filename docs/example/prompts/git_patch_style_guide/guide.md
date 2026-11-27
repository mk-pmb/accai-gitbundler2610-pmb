
Prompt optimization for git patch style guide
=============================================

This is an example prompt document.
See [`../README.md`](../README.md) for how it works.

<details class="config" open><summary>Config</summary>

* preset: code-review
* files:  draft.md hints.md

</details>

<details class="human" open><summary>Human</summary>

We're refining the new addition to the system message about git patch style.
The goal is to express the style guide such that you can understand it
with least reasoning token cost.
I'll attach the current draft for the addition, and some hints.

The draft is what will be added to the system message.
We optimize (for token cost) only the draft.
The draft can only use characters from the "Basic Latin" Unicode block,
so accept the boring ASCII quotes.

The hints are my observations from your previous attempts. (We're in round 22.)
Treat the hints as guidance, because each hint is based on a regression you
had suggested earlier. The hints also serve to give you much more background
knowledge beyond what we can afford in the draft, because that background
knowledge can help you understand why some of the draft is worded as is.

With the current draft, we're probably close to your maximum optimization
capability already. Good for me (maybe my work is almost done), but it means
you have to think even harder about whether your new ideas really make sense,
and not introduce new bugs or risks just for the sake of suggesting any change.

</details>















