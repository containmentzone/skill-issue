---
name: review-style
description: A skill for reviewing technical writing and code comments.
user-invocable: true
---

# style-filter

A revision pass for technical writing and code comments

## When to run it

On every draft of prose you wrote: chat replies, design docs, specs, READMEs, commit bodies, code comments.

Run it on the lines you wrote in this change, not on the whole file. Reflowing untouched paragraphs makes 
the diff unreadable, which is the thing this pass is for.

## When not to run it

On code, command output, quoted text, error messages, the user's own words, and prose you are not otherwise editing.

## The pass

Apply each check to a line, in order.

### Remember the audience

Write for technically-minded users, not executives. Do not optimize to convince or sell.

### Budget complexity

The more complex the topic, the less complex the language.

### Replace figurative words with the action

Before: an abandoned feature branch ages out on schedule
After: an abandoned feature branch is deleted once its expiry passes

Also: *lane*, *blast radius*, *rots*, *dead on arrival*, *let it ride*, *soak*, *straddle*, *bleed*, *costs a decode*.

Keep a figure only if you can say what it does that the plain phrase does not. Keep "blast radius" in a document that
states elsewhere how many objects are affected. Replace "lane" everywhere.

### Bold names, not arguments

Bold a field names, values, counts.

A bolded sentence you would have to defend is an argument. Unbold it, or cut it if the surrounding text already makes the
point.

Emphasis asserted in the abstract is the same failure without the markup: *has to be real*, *this matters*, *is critical*.
These claim importance without naming what is important. Emphasis must land on a concrete claim, and should be rare enough 
to mean something.


### Avoid anthropomorphizing

what reaches it -> its input  
the thing it hands back -> its return value  
everything the renderer needs -> the renderer's input  
a prefix earns its place -> a prefix is only useful where...  
the wrapper wants a name -> the wrapper requires a name  
helm stops deciding anything -> helm is a renderer and doesn't contain any logic

Say what the tool is, not what it wants. Code and prose do not earn, want, deserve, choose or decide:

Documents reference, cite, point to or list. They don't *name*, unless they're declaring a name.

### Requirements

When documenting technical requirements, use *must*, *should* and *can* and their negations *must not*,
*should not*, *can not*, in the RFC 2119 sense. Use best judgement to decide on casing.

### Omit fragmented frames

Two demands follow from that. The chart must… -> The chart must…

Also: *There are two consequences*, *This has implications*, *Consider the following*. The sentence counts the items below instead
of saying one of them. Delete it and start with the first item.

The escalating-number construction does it with digits: *rules that cost nothing at 2,600 lines keep it readable at 10,000*.
The numbers are invented and carry no information. Say *this will grow* and stop.

## Stop after one pass

Run the checks once and stop. A second pass starts rewriting content rather than wording, and the draft drifts away from what was approved.
