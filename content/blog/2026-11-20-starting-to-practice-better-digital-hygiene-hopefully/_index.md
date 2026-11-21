---
date: 2026-11-20T09:10:00
layout: content-page
stags: 
title: "2026-11-20: Starting to practice better digital hygiene... hopefully"
---

I have a bad habit of having way too many tabs open, and dumping my research notes in scattered disorganized files. I'd like to start to hold myself to higher standards.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

I have a bad habit of having way too many tabs open, and dumping my research notes in scattered disorganized files. I'd like to start to hold myself to higher standards.
<!-- summary -->

{{% content %}}

## Content {#content}

### Some background context about what the problems are

To get a sense of what I am trying to change, my current count of open tabs is something like:

- 635 tabs from personal computer Chrome
  - Go to chrome://inspect/#pages
  - Open devtools and run this: `document.getElementById("pages-list").childElementCount`
- 326 tabs from work laptop Chrome (many relating to things I've looked up on the clock, and so on)
- 17 tabs from work laptop Edge

That is 635 + 326 + 17 = 978 tabs total.

These range from AI chatbot conversations about a wide variety of topics, to news articles that I found interesting, to "how-to" type pages, and so on. Some of these I definitely want to write up in detail; some I'm OK just saving so I can search back through them later.

The problem is, to date, I've never really had a structured system to do this. Don't get me wrong, I've used session manager browser extensions, and so on. But simply saving lists of tabs doesn't really help me understand the *context* of what I was doing with them open. If they were recent enough or self-explanatory enough I can oftentimes figure it out simply by glancing through the list, and looking at what my search queries were. But oftentimes it is really hard to piece together after-the-fact.

### The basic plan

So why have I never been better about keeping up with having things organized? To be honest, I think a lot of it is just that I've always had grand dreams about building a formal PKM = a system of properly tagged, interrelated personal notes in the fashion of Zettelkasten, but... well, shooting for that from the get-go means the cliff is too steep, and so nothing gets done at all. The perfect is made the mortal enemy of the good.

We can go ahead and forget "perfect". That word doesn't belong even near what I am going to start trying to do. Even "good" is probably too charitable for how mercenary and brutal I'm going to try to be in enforcing a "close to tab zero" mentality. For now, my only goal is going to be to jot down bullet-point type context with collections of links, and get them all into Markdown files that can be effectively full-text searched. Forget subject tagging. Forget coming back and updating posts over time to make them pretty or even just moderately readable. Forget content summaries. All of that is too much work for not enough benefit. Instead, I just want to get everything down and out of my head and my browser tabs.

How I draw the lines on how to group stuff is going to be pretty arbitrary, but generally speaking, I'm going to shoot for organizing things by research topic. Clearly, research topics at times branch. So do the branches count as part of the original topic, yes or no? It's going to depend how I'm feeling in the moment, and I'm going to intentionally make peace with it being utterly arbitrary and probably inconsistent in practice. Whatever. Filename search (cf. [Everything Search](https://www.voidtools.com/faq/)) and full-text search (cf. [AnyTXT](https://anytxt.net/)) will take care of 99% of finding things needs, so it doesn't really matter how things get split, since I'll probably be able to find what I want without too much hassle anyway.

### AI chatbot conversations too

Up until now, I confess I've mostly been using the Gemini interface built into Google Search, because it has been so simple to turn to (assuming you already use Google as your search engine). However, this interface's "copy" feature does *not* copy as clean Markdown. It's not proper plain text either, so I'm not entirely certain what it is. To be honest, the copy feature for this interface is pretty shoddy overall (at least at time of writing), and so shame on me for putting up with it until now. Fortunately, I've only just recently started saving a lot of deep AI-assisted research responses---so I don't have *too* much stuff saved in this decidedly subpar copy format---but I have enough saved that it still hurts.

But, as they say, when you find yourself in the bottom of a hole, first thing to do is to stop digging. So I've decided to move to a chatbot interface that lets you save individual responses as plain Markdown. I say individual responses, because while you technically can saved entire conversations at a time (at least with certain tools), I really do think it makes sense to always do an editing pass at the same time you are digesting chatbot responses, to trim out any info the chatbots spit back that you actually don't care about (which is very common). To keep the saved conversations most focused and useful, you actually want to save a version of the conversation that *omits* a bunch of returned information. How much exactly can vary by how specific your prompts were, how difficult the topic is in general for chatbots to infer what you are really asking/interested in, etc., but the general idea is that you should basically only ever save the relevant bits (whatever exactly those turn out to be), and that requires response-by-response editing anyway. So the ability to export entire chat histories to Markdown (rather than just individual responses) actually isn't particularly important, in my opinion. At least, not for this specific workflow.

To avoid getting sucked into a research black hole right upfront, I decided to go with either Anthropic's Claude or OpenAI's ChatGPT (two of the commercial market leaders). I suppose you could also look into Google Gemini and Microsoft Copilot, but when I saw that the former two both allow for exporting responses to clean Markdown, I was good with sticking with one of them. I am not that worried about privacy at the moment, because what I am using these for right now is heavy research tasks that I don't care if they track (so having a maximally-capable frontier model is more important to me in this usage than good privacy safeguards). YMMV. You might look into something like [Lumo](https://lumo.proton.me/) if you want a privacy-focused chatbot. Or run offline models locally. Etc.

For my heavy research workflow (all I care about at the moment---doing a deep dive on agentic AI coding is on my to-do list), I decided to go with ChatGPT, because based on my 5 minutes of research, sometimes Claude can completely lock you out until you wait for your rolling usage window to reset, whereas that is harder to do with ChatGPT, which allows almost unlimited basic text chats (and will only throttle other heavier interaction paradigms once you exceed your usage limits). YMMV, since this depends upon current circumstances and rate limits that seem to change rapidly, and so on.

At any rate, by shifting my normal chatbot from Google-Search-adjacent-Gemini to webapp-OpenAI-ChatGPT, I am actually going to start posting a log of all my AI chatbot research conversations. They will basically only be edited to remove the bits of chatbot responses I found irrelevant. I may also intersperse personal commentary between prompt/response pairs, as I see fit.

A lot of this information will eventually end up incorporated into much more polished notes pages... someday. But for now, I am just going to be dumping all my research logs as-is, with minimal editing or cleanup. I am tired of remembering I had come to specific conclusions about something or remembering specific facets relating to that thing, only to not be able to find it, since it is still stuck in a browser session somewhere, rather than in full-text-searchable plaintext. This is the fundamental problem I am trying to solve at the moment.

After I solve this problem, then we'll see. One step at a time.

I should note that I *do* use AI to assist in research for the Bible study content I write every week for [BibleDocs](https://www.bibledocs.org/). Most of the content really is hand-written by me (so AI use in terms of direct wording is quite minimal, except when I decide to copy-paste some scattered clauses or sentences from the AI tools here and there). However, I *do* make pretty heavy usage of the AI tools in research tasks, particularly in tracking down sources or getting a feel for scholarly consensus on various things. It is very useful to be able to ask the tools things like "do scholars typically buy the chroniclers' narratives that X" and then go check some sources. The AI tools make this *way* faster than manually looking up all the information would.

At any rate, I am bringing this up here just to note that I do *not* save research logs from these BibleDocs-related AI-assisted research sessions, because I am actually directly writing final production content with those research sessions. It is an apples and oranges sort of usage compared to the content that gets saved into research logs proper, which is much less polished and finalized overall.

### What all of this actually means

To get through my backlog of 900+ current links and also document my AI-assisted research sessions, I will be dumping content into date-marked posts within a new content type called `research-logs` (See [here](/research-logs)). This is going to be kept separate from `blog` so that I don't spam the main blog content stream with all my random research logs.

Topics will be over all the place, and in no particular order. To be honest, while all of this is going to be made public because why not, this may prove to be of interest to a pretty small subset of people in practice, since it is going to be extremely rough and unpolished. Treat this as a directory you full-text search on, not something you typically spend time reading all the way through, and you will probably find it to be of more use. (At least, if you are interested in similar topics to me, which you may well not be. As always, YMMV).

{{% /content %}}

{{% section-navigation %}}
