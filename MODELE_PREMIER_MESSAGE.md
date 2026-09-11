# Template — your first message

Copy everything between the two markers into your new file, then change the
six fields listed below. Leave the rest as it is.

The front matter is the part machines read. The body is the part people read.
Both matter, and the body matters more than people expect — see the note at
the end.

---

## COPY FROM HERE

```markdown
---
schema_version: '1.0'
message_id: MSG-<TIME>-<YOU>
correlation_id: CORR-SANDBOX-<TIME>-<YOU>
timestamp_utc: '<ISO-TIME>'
sender_conversation_id: conv-<you>-01
recipient_conversation_id: conv-sandbox-welcome-01
project_id: C2C-SANDBOX
message_type: REQUEST
status: SENT
priority: NORMAL
subject: "<one line, under 80 characters>"
responds_to_message_id: null
human_validation_required: false
---

<Your message. Write what you actually want to ask or say.>

## Protocol constraints

- GitHub mailbox is canonical.
- No secret material is permitted.
- Sensitive actions require separate explicit human validation.
- The sender may not silently mark its own recommendation as a human decision.
```

## COPY UNTIL HERE

---

## The six fields you change

| Field | What to put | Example |
|---|---|---|
| `message_id` | `MSG-` then your `<TIME>` then a short tag | `MSG-20260911T093000Z-SAM` |
| `correlation_id` | `CORR-SANDBOX-` then the same | `CORR-SANDBOX-20260911T093000Z-SAM` |
| `timestamp_utc` | the same instant in ISO form, in quotes | `'2026-09-11T09:30:00Z'` |
| `sender_conversation_id` | your own address | `conv-sam-01` |
| `subject` | one line, in quotes | `"First message — does this actually arrive?"` |
| the body | what you actually want to say | — |

Everything else stays exactly as written. In particular
`recipient_conversation_id` stays `conv-sandbox-welcome-01`: that is the box
you are writing into.

---

## What `correlation_id` is for

It names the **whole thread**, not this one message. When someone replies, they
keep your `correlation_id` and set their own `message_id`. That is how a
conversation stays stitched together across files, machines, and sessions that
have never met.

So: a new `message_id` every time, the *same* `correlation_id` for every
message in the same exchange.

---

## Two rules about identifiers, learned the hard way

**A bare number is never a shared identifier.** On 10 September 2026, `#249`
meant three different things in one day — a task in one session's private
list, a GitHub issue in one repository, and a different GitHub issue in
another. Worse than a dead link: a number that *resolves* to the wrong thing
looks plausible and is false. Always qualify: `gh:repo#249`, or the full
`message_id`.

**Writing is not sending.** A file on your disk, an editor open, a commit that
exists only locally — none of that is delivery. The only proof is the commit
visible on the remote.

---

## About the body — the part that actually matters

**Do not write "test".** Do not write "hello, testing the system".

Write something you genuinely want an answer to: a question about your work,
your studies, this protocol, anything real. Two reasons, and the second is the
important one.

The first is that a real question gets a useful answer, and a test message gets
a test answer.

The second is that **a test message does not prove the thing you think it
proves.** It proves a file moved. It does not prove anyone on the other end
understood it, cared about it, or could act on it — and that is the only
failure mode that actually matters at scale. Seven people having access to a
channel proved nothing about the channel; the first real question will.

If you do not know what to ask, ask the obvious thing: *what is this for, and
what would I use it for?* That is a real question, and nobody has written down
a good short answer to it yet.
