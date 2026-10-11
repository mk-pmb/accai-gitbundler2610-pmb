
<!--#echo json="package.json" key="name" underline="=" -->
accai-gitbundler2610-pmb
========================
<!--/#echo -->

<!--#echo json="package.json" key="description" -->
Share a git repo with the Academic Cloud Chat AI.
<!--/#echo -->


* "accai" = [☁️ Academic Cloud](https://www.academiccloud.de/) &rarr;
  [💬 Chat AI](https://chat-ai.academiccloud.de/)
* [Do I need an API key?](accloud/orga/api-key.obtain.md)



Prior work
----------

* In theory, the best way to share a git repo (or any files) with
  an LLM is via MCP ([Model Context Protocol][wp-mcp]).
* My current attempt to do so is
  [research-ai-mcp2605-pmb](https://github.com/mk-pmb/research-ai-mcp2605-pmb/)
  but it's currently stalled, waiting for another project I have to build first.
* An imperfect stopgap was to use [`git-export-repo-as-markdown`][git-repo2md]
  but since it uses markdown as the packaging format, there are limitations on
  properly encoding markdown files and HTML files.

  [wp-mcp]: https://en.wikipedia.org/wiki/Model_Context_Protocol
  [git-repo2md]: https://github.com/mk-pmb/git-util-pmb/blob/master/git-export-repo-as-markdown.sh



The new approach used here
--------------------------

With the old approach, I have to:

* Start a new conversation,
* upload the bundled file,
* copy¹ my prompt,
* verify/select the model,
* then copy my system prompt.

I think I can do better: Embrace the persona approach and enhance it with
not just [YAML capability](https://github.com/gwdg/chat-ai-personas/issues/21)
but also local file system access.

How? By using the "Import Chat" feature. I had totally underestimated its
flexibility. With the exact same effort as the file upload step would require,
it can do all of the above steps.


&nbsp;

<small>
(¹ Always pre-type your prompt in a text editor: It avoids the risk of wasting
energy on accidental submit, and the risk of unexpected session expiration.
With the UI as of 2026-10-10, auto-logout disrupts the workflow very harshly.)
</small>



Usage
-----

* In your git repo, run: `accai-gitbundler2610-pmb >~/tmp.accai.json`
* In accai, click "Import Chat" and select the file.
* Type or refine your prompt.
* Submit.



Known issues
------------

* Needs more/better tests and docs.





<!--#toc stop="scan" -->

&nbsp;


License
-------
<!--#echo json="package.json" key="license" -->
ISC
<!--/#echo -->
