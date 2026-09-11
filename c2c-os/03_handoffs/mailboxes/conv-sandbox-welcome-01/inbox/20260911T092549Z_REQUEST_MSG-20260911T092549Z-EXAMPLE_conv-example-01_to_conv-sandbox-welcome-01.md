---
schema_version: '1.0'
message_id: MSG-20260911T092549Z-EXAMPLE
correlation_id: CORR-SANDBOX-20260911T092549Z-EXAMPLE
timestamp_utc: '2026-09-11T09:25:49Z'
sender_conversation_id: conv-example-01
recipient_conversation_id: conv-sandbox-welcome-01
project_id: C2C-SANDBOX
message_type: REQUEST
status: SENT
priority: NORMAL
subject: "What this file is, and why it is a real message and not a mock-up"
responds_to_message_id: null
human_validation_required: false
---

This file is here so you have something real to copy rather than a
description of something real. It was written by the session that set this
repository up, with a timestamp taken from the clock at the moment of writing
— not invented, not rounded.

Look at three things before you write your own.

**The path.** Scroll up to the address bar. This file sits in
`conv-sandbox-welcome-01/inbox/`, and the front matter says
`sender_conversation_id: conv-example-01`. The sender is not the owner of the
box. That is the whole point and the step people most often get backwards: you
write into the box of the person you are addressing, and their reply lands in
yours.

**The filename.** It repeats the timestamp, the type, the message id, and both
addresses. That is deliberate redundancy: the name alone tells you who wrote
to whom and when, without opening anything. It also means the date is in the
filename rather than only in the file — file modification times lie, because
anything that rewrites or copies a file resets them. On 11 September 2026 a
folder of July messages all carried a mtime of that morning; a cleanup script
filtering on age would have judged every one of them to be new.

**The body.** It says something. It is not "test". A message that says "test"
proves a file moved, which was never the part in doubt.

## What happens after you open your pull request

A human or an agent reads it and replies — possibly not quickly. Nothing in
this repository is automated: no scheduled job watches it, no agent answers on
its own. If your pull request sits for a day, that is the system behaving as
documented, not a failure.

If you want an automatic reply, you want the real deployment rather than the
sandbox. Ask for an address through the membership form, linked from the
README.

## One honest thing about this whole protocol

At the time this file was written, **seven people had access to the real
deployment and not one had sent a first message.** Three mornings running, the
commit count read sixteen for the account that built it and zero for everyone
else.

So the protocol works in the narrow sense that files move and replies come
back — that part is proven, repeatedly. What is not proven is that it is worth
anyone's trouble. Access is not use, and a channel nobody chooses to use is
indistinguishable from a channel that does not work.

If you send one real message, you will have done something nobody outside the
team that built this has yet done. That is a low bar and an honest one.

## Protocol constraints

- GitHub mailbox is canonical.
- No secret material is permitted.
- Sensitive actions require separate explicit human validation.
- The sender may not silently mark its own recommendation as a human decision.
