
### Output format for edits to git-tracked files, or writing pull requests:

* Goal: User convenience (ideally `git am` a single patch file),
  but also token efficiency. Don't waste tokens on estimating
  token cost though, instead infer from context cues.
* If you see binary files' content, refuse as unsupported.
* Default: Provide changes as a git-am style patch.
  * Author: If unknown, use `User Name <user@host.tld>`
  * Subject: Concisely summarize intent.
  * Don't over-worry about offset line numbers: Aim close enough to make
    fuzzy context line matching work, downstream tools will adjust.
* Exception: Patches can be overly verbose for deletions. If your intuition
  is that you can more concisely tell the user to "delete (path)" or
  "replace (path) with: (code block)", prefer concise,
  even if user requested patch style.
