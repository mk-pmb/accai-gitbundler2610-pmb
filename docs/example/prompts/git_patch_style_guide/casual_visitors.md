
Background info for casual visitors
===================================

This directory shows an example of using an AI to help refine a system prompt
snippet for teaching the AI to output patches instead of full files.

<!-- Bonus detail for enthusiasts reading comments (Hi!):
This example is a small exercise in iteratively refining a system prompt,
which is one of many techniques of [prompt engineering][wp-prompt-eng].
The more you know! -->

  [wp-prompt-eng]: https://en.wikipedia.org/wiki/Prompt_engineering


### AI tends to give full files

You've probably worked with AI (artificial intelligence) by now.
Most AIs are trained to be helpful to average people.
So when you ask an AI to edit files for you, it tends to give you the full
result, the new version of that file, so you can easily copy or download it.


### Programmers prefer patches

Programmers often want to track so-called _patches_.
A patch is a record of who changed what and when, often with a helpful
description that explains why it was changed the way it was.
If you keep a machine-readable historical record of patches,
and you then discover a problem, that historical record can help your
detective software investigate which patch caused the problem.
With a bit of luck, you can even have software undo that bad patch and
still keep all the later improvements.


### Version control, git, and git-am

Software that helps track and manage patches is called
_[version control](https://en.wikipedia.org/wiki/Version_control) software_,
and one popular variety of that is called _Git_.
In Git, the standard file format for sharing patches is the git email
patch format. But that's a long name, so it's often shortened to
"git-am format", because "git am" (am = apply mail)
is the command to apply (receive, accept, import) such a patch.

<!-- Actually, am = "apply mailbox", but may confuse casual readers. -->

Those patches are easy to review because they show only what changed:
Old lines (to be deleted) start with a minus sign,
and new lines (to be added) start with a plus sign.
Here's an example: [A simple git patch.][git-util-d6c21df]

  [git-util-d6c21df]: https://github.com/mk-pmb/git-util-pmb/commit/d6c21dfa389c


### Files in this directory

The [`guide.md`](guide.md) file is an example of a prompt file:
A file that tells an AI how to help the user.
In this example, the task is to help write a style guide that tells an AI
to produce patches instead of giving full files.
The prompt file also declares two extra files to be submitted,
[`draft.md`](draft.md) and [`hints.md`](hints.md).

(There's also a prompt file [`sae.md`](sae.md) that shows how to ask
for feedback on this explainer that you're just reading.)

The style guide will become part of the so-called _system message_.
The system message is usually invisible to AI users:
It's the secret instructions that the AI service provider uses to tell its
AI how to behave, e.g., what kinds of tasks it is allowed to help you with,
what tone to use (formal? casual? polite? concise? reassuring?), etc.

An AI must always remember and adhere to the system message,
so that alone consumes some part of the AI's thought capacity.
(The "token cost" mentioned in the prompt is a measure of AI thought effort.)
The shorter and easier the system message is (fewer tokens consumed),
the more thought capacity remains available for solving the actual task.
So writing a good system message is a tricky balance between
giving enough guidance and minimizing distraction.






