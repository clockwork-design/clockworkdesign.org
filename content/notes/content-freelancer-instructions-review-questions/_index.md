---
layout: single-page
stags: 
title: "Content Freelancer instructions: Review questions"
---

This page describes the format of review questions, which get added as part of content post-processing.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

This page describes the format of review questions, which get added as part of content post-processing.

<!-- summary -->

{{% content %}}

## Content {#content}

### Overview

You will specify review questions within `quizdown` shortcodes:

```markdown=
{{</* quizdown */>}}

{{</* /quizdown */>}}
```

There is a specific format the questions have to show up in. I'll go over each of the possible types below, and then which ones you should actually use in practice.

But first, what should you even make review questions?

### Do's and don'ts in question selection

In terms of what you make review questions, you should aim to figure out what the most important topics/takeaways from the page are, and then make review questions for those, and basically only those. The number of review questions can vary as necessary, but there is no need to be hesitant of making too many, so long as all of them are *actually* related to important concepts/topics.

As a rule of thumb, we want to avoid making review questions for trivial details that are not big picture. That tends to mean that you should avoid making review questions for:

- Specific people who did X
- Specific dates that X occurred
- Specific places that X occurred
- Etc.

For example, is it truly useful to know the name of the exact pope that launched the Second Crusade, so long as you know that the pope at the time did it (as opposed to secular government authority, say)?

And what about what exact year Edessa fell to the Muslims? Does knowing that it was 1148 specifically (rather than sometime in the mid 12th century, say) really benefit us much?

And actually do we *really* care that it was the Crusader State of Edessa specifically that fell (or just that one of the Crusader States fell, leaving the remaining ones feeling threatened and vulnerable)?

This is the sort of thing you should think about. Especially for history-focused content (rather than theology-focused content), avoiding low-level specifics is usually the right answer. Not always, but usually.

So what kind of questions should we prioritize in practice then? Making the questions focus on *why X happened* is usually a pretty good path to take (as opposed to the specifics of who/what/where/when), and then also *what effects/impact/importance X had*. If you make questions along these lines, they will inherently tend to stay more big picture, tracing high-level causes and effects. And that just tends to be more useful for overall understanding and comprehension.

### Possible types of review questions

There are more types of review questions that are possible to use than those I actually want us to use. This section goes over all possible types, and [the next section](#which-types-of-review-questions-to-actually-use-in-practice-and-why) goes over which types of review questions you should actually use in practice (which is a smaller set).

#### True or false questions

Example:

```markdown
# True or False: The burning bush was a Christophany

In Exodus 3.

1. [x] True
1. [ ] False
```

The choice that is the correct one has an x in it.

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown
# True or False: The burning bush was a Christophany

1. [x] True
1. [ ] False
```

#### Pick between two options questions

```markdown
# Between the First Crusade and Second Crusade, which one proved to be a military success? 

From the perspective of the crusaders.

1. [x] The First Crusade
1. [ ] The Second Crusade
```

The choice that is the correct one has an x in it.

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown
# Between the First Crusade and Second Crusade, which one proved to be a military success? 

1. [x] The First Crusade
1. [ ] The Second Crusade
```

#### Basic multiple choice questions

```markdown
# Which prophet ran away from Jezebel?

In 1 Kings 19.

1. [ ] Moses
1. [x] Elijah
1. [ ] Elisha
1. [ ] Jeremiah
1. [ ] Isaiah
```

The choice that is the correct one has an x in it.

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown

# Which prophet ran away from Jezebel?
1. [ ] Moses
1. [x] Elijah
1. [ ] Elisha
1. [ ] Jeremiah
1. [ ] Isaiah
```

#### Roman numeral which of the following are true multiple choice questions

```markdown
# Which of the following statements about Jesus are true?

I. Jesus is fully God
II. Jesus is fully man
III. Jesus is co-eternal with the Father

1. [ ] I. alone
1. [ ] II. alone
1. [ ] I. and II.
1. [ ] II. and III.
1. [x] All of the above
```

The choice that is the correct one has an x in it.

#### All of the following are true except multiple choice questions

```markdown
# All of the following statements about Jesus are true except

1. [ ] Jesus possesses a divine nature
1. [ ] Jesus possesses a human nature
1. [ ] Jesus is co-eternal with the Father
1. [x] Jesus possesses an angel nature
1. [ ] Jesus is of one substance with the Father
```

The choice that is the correct one has an x in it.

#### Basic multiple select questions

In questions of this type, more than one choice needs to be selected for the question to be marked as correct.

Example:

```markdown
# Who are the two witnesses of Revelation?

Whose ministries run alongside the 144,000.

- [x] Moses
- [x] Elijah
- [ ] Elisha
- [ ] Jeremiah
- [ ] Isaiah
```

The choices that need to be selected for the question to be marked correct have x's in them.

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown
# Who are the two witnesses of Revelation?

- [x] Moses
- [x] Elijah
- [ ] Elisha
- [ ] Jeremiah
- [ ] Isaiah
```

#### All of the following are true except multiple select questions

Just like all of the following are true except multiple choice questions, but there is now more than one "except" thing.

```markdown
# All of the following books are part of the traditional 66 book biblical canon except

- [ ] Revelation
- [ ] Job
- [ ] Malachi
- [x] Tobit
- [ ] Galatians
- [x] Enoch
```

#### Sequence/order questions

These questions make the user order the choices. 

```markdown
# God took specific actions on each of the days in the "creation week". Put the creation days in order

As described in Genesis 1.

1. God created light, separating it from the darkness to establish day and night.
2. God created the expanse (sky/heaven), separating the waters above from the waters below.
3. God gathered the waters to reveal dry land, named the land and seas, and created vegetation (plants and trees).
4. God created the sun, moon, and stars to govern the day and night and to mark seasons, days, and years.
5. God created sea creatures and birds to fill the waters and the sky.
6. God created land animals and humanity (male and female) in His own image, giving them authority over the earth.
7. God rested from all His work.
```

The correct sequence is the one used to define the question. The answers are always shuffled when presented to the user.

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown
# God took specific actions on each of the days in the "creation week". Put the creation days in order

1. God created light, separating it from the darkness to establish day and night.
2. God created the expanse (sky/heaven), separating the waters above from the waters below.
3. God gathered the waters to reveal dry land, named the land and seas, and created vegetation (plants and trees).
4. God created the sun, moon, and stars to govern the day and night and to mark seasons, days, and years.
5. God created sea creatures and birds to fill the waters and the sky.
6. God created land animals and humanity (male and female) in His own image, giving them authority over the earth.
7. God rested from all His work.
```

##### Fill-in-the-blank questions (question form)

In these, the user needs to type in the text that answers the question.

The only thing that distinguishes questions of this type from multiple choice questions syntax-wise is that there is only one choice, which is always checked with an x.

When defining answers to fill-in-the-blank questions, you can make it so that there is more than one accepted answer, using regular expression syntax (`()` and `|`).

- So `(The Holy Spirit|Holy Spirit)` will match either `The Holy Spirit` or `Holy Spirit`.

Here is an example:

```markdown
# Which angel told Mary she was pregnant?

In Luke 1.

1. [x] Gabriel
```

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown
# Which angel told Mary she was pregnant?

1. [x] Gabriel
```

#### Fill-in-the-blank questions (blank form)

Rather than phrasing the prompt as a question, these are statements that have blanks. By convention, you should use six underscores in a row to specify the blanks.

```markdown
# The angel ______ told Mary she was pregnant.

In Luke 1.

1. [x] Gabriel
```

You don't have to have any subtext under the question header. So this would work equally fine as a question:

```markdown
# The angel ______ told Mary she was pregnant.

1. [x] Gabriel
```

### Which types of review questions to actually use in practice, and why

#### Types of questions we *avoid*, and why

We avoid true or false questions, because any of these that are false do not give the reader any useful information (i.e., because there are many ways something can be false, but only one way something can be true), but if you never allow for falses at all---such that all true or false questions are always true---then that is too predictable.

We avoid basic multiple choice questions because they have a very poor true content to false content ratio. Assuming your multiple choice question has five choices (A, B, C, D, and E), then you have to come up with four "bad" answers for every one "good" answer. Not only is that effort intensive on the part of the person making the review questions, but it also makes these questions proportionally less "information dense". What do I mean by information dense? If you compare five-choice basic multiple choice questions with five-choice all of the following are true except multiple choice questions, then the basic multiple choice questions only give you one true piece of information per question, whereas the all of the following are true except multiple choice questions give you four true pieces of information per question. That is much higher overall information density.

We avoid all of the following are true except multiple select questions for similar information density reasons. There is simply no need to ever dilute information density.

So the generalizable rule is this: because we *can* make it so that each question has at most one piece of false information (while still avoiding predictability, unlike with true or false questions), then that is what we will always do, since this maximizes information density.

#### Types of questions we *do use*, and why

That leaves the following question types left to use:

- Pick between two options questions
- Roman numeral which of the following are true multiple choice questions
  - Specifically, questions of this type that only have at most one false roman numeral statement. That is, all can be true or one can be false, but more than one cannot be false.
  - You can have more than one false multiple choice option (e.g., if II is false, then the multiple options "I and II", "II and III" and "All of the above" would be false); the point is that there is only at most one false roman numeral statement.
- All of the following are true except multiple choice questions
- Basic multiple select questions
  - Specifically, questions of this type that only have at most one false option.
- Sequence/order questions
  - These are going to be very rare in practice, but when you have a case for them, they are great.
- Fill-in-the-blank questions (question form)
- Fill-in-the-blank questions (blank form)

#### Any differing priorities within this smaller set? Yes: we should combine questions, where possible.

Generally speaking, wherever possible and it makes sense, you should combine questions. This helps keep the overall number of review questions more manageable, without really sacrificing the amount of information gone over.

So rather than stringing together a bunch of separate pick between two options questions or fill-in-the-blank questions (both of which are inherently question types where only one option is true), it makes sense to combine them into a single question that allows for multiple options. That would be any of these combined question types:

- Roman numeral which of the following are true multiple choice questions (with at most one false roman numeral)
- All of the following are true except multiple choice questions
- Basic multiple select questions (with at most one false option)

In practice, this means that *these three combined question types should compose the bulk of the questions you make*. It doesn't have to be all of them, but it should probably be most of them.

### Other usage guidelines

#### Fill-in-the-blank questions (question form) and fill-in-the-blank questions (blank form)

Put simply, any time you expect the user to type in an exact value, it needs to be a case that is highly deterministic (such that if they know the right answer, it is dead obvious what they should type in).

Here are some example questions where this is *not* true (or at least not sufficiently true):

```markdown
# The Crusader States (or Outremer) faced external pressures that threatened what?

1. [x] Their existence
```

In this one, here are some other things that would seem to work equally well in the blank:

- Their survival
- Their borders
- Etc.

So how is the reader supposed to know?

Another example:

```markdown
# As believers, what should we do when we sin? 

In 1 John 1:9.

1. [x] Confess our sins
```

This one is mostly OK, but I bet a lot of people would probably just enter "confess" and not "confess our sins". How are they supposed to know it is the latter not the former?

Some things that you could hypothetically make fill-in-the-blank questions should actually end up as pick between two options questions, since there is no need to make the user type in a value if we are just making them pick between A and B. So do *not* do this:

```markdown
# Which crusade had more people concerned with arguments of justification, the First Crusade or the Second Crusade?

1. [x] The First Crusade
```

But instead do:

```markdown
# Which crusade had more people concerned with arguments of justification, the First Crusade or the Second Crusade?

1. [x] The First Crusade
1. [ ] The Second Crusade
```

{{% /content %}}

{{% section-navigation %}}
