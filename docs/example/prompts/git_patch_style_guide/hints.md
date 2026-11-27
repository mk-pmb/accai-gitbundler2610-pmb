
* I considered adding thresholds for the vague gut-feeling criteria, but
  constant numbers that override context-aware reasoning could cause more
  bugs than help. Would be bad to waste tokens on guessing what "many" in
  "saves many tokens" means, but also bad if you start wasting thought on
  math to determine whether savings will meet a 10% threshold.
  My hope is that the training data gives a good enough virtual gut-feeling
  to rely on first impression. But even stating that might prevent the model
  from detecting mid-way that it took the wrong route.
  * The word "only" (as in "if the change is only deletions or only
    replacements without context lines") will likely become a strict 0%
    threshold, with its own "threshold vs. context-aware" risks.
* The binary upload rule is added only if the UI checkbox "includes binary
  files" is unchecked, so we know it's an accident. Training data doesn't
  know we have that checkbox, and the LLM probably doesn't need to know.
* The fuzz-encouragement is there because you sometimes drafted an entire
  patch in reasoning, then had doubts about the line numbers, and used more
  reasoning tokens to rewrite the entire patch again, just to doubt again.
  We need optimisms here: We actually have output filter stages that include
  `git-why-does-patch-not-apply --fix` and if that fails, the watchdog will
  automatically re-invoke you with the error message that will include likely
  fixes. But explaining that for every invocation would also waste tokens.
  We need to give short but strong reassurance that fuzz is ok.
  * The word "style" in "git-am style" is meant to relax the implication that
    a proper git-am patch should have proper line numbers.
  * "use minimal context" is a bad idea. Too few context can complicate human
    review and can impede autofixing. Training is good about the amound of
    context, we only need to avoid over-thinking the line numbers.
* Earlier when we had "If instructions like…", you usually understood the word
  "instruction" to mean "from LLM to user" in your first reply.
  However, in follow-up questions, you often confused it for examples of
  user instruction to the LLM. Looks like we need to keep some kind of
  clarification to make your understanding persist beyond the first reply.
