
<!--
THIS IS A CARRY-OVER SLOT, not a new hole. You wrote this guide in
week 2 and carried it through week 3; paste your filled voice-guide.md
here, whole. It is not re-authored and it is not graded as new work
this week.

Then reread it with the PR in mind. Your comments promised, reported,
and committed to an approach; a PR title and description ask a
maintainer to spend review time on your work. If your rules do not
cover that register (for example: how a title earns its thirty
seconds, how a description promises exactly what the diff contains,
how a disclosed shortfall is worded so it reads as honesty rather
than apology), extend the guide with what it needs. Extending is
allowed and encouraged; starting over is not required.

Live mode reads this file and holds your draft PR title and
description against it, reporting any rule your draft breaks. Eval
mode ignores it entirely, because your voice is yours and carries no
gold labels.
-->


# Voice guide: how I talk upstream

## Who I am in threads

I am a freshman computer science and math undergraduate student with about a year of self-taught programming experience. I am working in this repo to investigate and reproduce reported bugs. Readers can expect factual, straightforward technical notes focused strictly on evidence.

## Rules I write by

### Rule: Claim Only Investigation

Never assert a fix or state what the root cause is before you have reproduced the issue and verified the code path. State only what you are going to look into next.

* Wrong: "I found the bug in the parser function and I am going to fix it by tomorrow."
* Right: "I am claiming this issue to set up the reproduction environment and test the reported behavior."

### Rule: Evidence Over Confidence

Never state that a bug exists or does not exist without providing exact command outputs, steps, or logs from your test run. Keep assertions strictly tied to observed data.

* Wrong: "This bug definitely happens on every machine because the logic is completely broken."
* Right: "Running node test.js on commit a1b2c3d produced the following error log: [paste log]."

### Rule: Zero Timeline Promises

Never promise delivery dates, turnaround times, or fixed schedules for your investigation or pull requests. State your intent to work on it without locking yourself into a calendar deadline.

* Wrong: "I will have a patch ready for review by Tuesday morning."
* Right: "I am actively investigating this behavior and will post updates here as I find them."

## Things I never post

* Promises of timelines, deadlines, or fix delivery dates.
* Unproven assertions or definitive claims about bugs you haven't personally reproduced yet.
* Conversational filler, personal background stories, or emotional commentary.
* Dismissive or argumentative language toward issue reporters or maintainers.