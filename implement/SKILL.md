---
name: implement
description: "Implement a piece of work based on a spec or ticket."
disable-model-invocation: true
---

Implement the work described by the user in the spec or ticket.

Do NOT widen the scope: build exactly what the spec or ticket asks for, nothing more, nothing less.

If the user passes a ticket reference, read it and state its title before starting. If the reference is ambiguous, ask.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.
