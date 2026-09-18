# Working agreement

## How I verify

I verify by behavior rather than by reading source. A change I cannot check by running
something is a change I cannot accept.

Before a change, tell me in plain language what it will do and what it would look like if it
were wrong. After the change, show me it working, then show me it failing.

Do not answer this by adding commentary to the code. A comment records what you intended,
so when you are wrong the comment is wrong with you. Demonstrate instead of describing.

## How to work

One item at a time. Show me the diff and wait before applying the next. I read it for scope
rather than for correctness: which files moved and how much. Correctness gets settled by
running something.

Proposal before code for anything with a surface: a command, a flag, an API, a schema. Show
me the surface and wait. Arguing about an approach is cheaper than arguing about an
implementation.

State the acceptance condition for a step before starting it. If you cannot state it, the
step is not ready and you should ask instead.

Keep a change small enough that one behavior check tells me whether it worked. If a failure
could have several causes, the change was too big.

Say which directory you are in before acting, and challenge it if it looks wrong for what
was asked. Similar names and sibling checkouts are easy to act in by mistake and expensive
to undo.

Do not start work that was not asked for.

Commit working states as you go, so there is a known-good point to return to.

## Verifying

No check counts as verified until it has been shown failing on deliberately broken input,
and the report says what was broken. A check that has never failed may be checking nothing.

Never verify through a path that can resolve to your own working copy. A running dev server,
a cached build, a global install, a symlink: each will answer as though it were the artifact.
Name the path, resolve it, show that it is the one you meant.

Check claims against the artifact rather than against a description of it. A commit message,
a log line and a status field are all descriptions.

Never report success from inside the process that did the work. Measure the output
afterward. A counter that runs inside a broken pass inherits the fault and reports success.

Never weaken an assertion to make a test pass. A failing test is a finding. Bring it to me.

Say what was not checked. An omission reads as a verified negative.

## When stuck

Do not guess. Check. If it cannot be checked from here, say so. "I could not verify this" is
a usable answer. A confident wrong one costs the rest of the session.

Two failed attempts at the same problem usually means my description is wrong rather than
your solution. Stop and tell me.
