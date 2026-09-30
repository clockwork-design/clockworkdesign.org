---
date: 2026-09-21T09:10:00
layout: content-page
stags: 
title: "2026-09-21: Working on a more detailed weekly procedure"
---

So that we can start using the new process ASAP, I worked on hammering out the main weekly steps.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

So that we can start using the new process ASAP, I worked on hammering out the main weekly steps.

<!-- summary -->

{{% content %}}

## Content {#content}

### Progress made on the weekly procedure

In the second week of reworking on stuff for the content process, I focused on (mostly) finalizing the weekly procedure, in all its messy glory:

- [Content Freelancer instructions: Checklist for weekly content processing · ClockworkDesign](https://www.clockworkdesign.org/notes/content-freelancer-instructions-checklist-for-weekly-content-processing/)

It is now pretty thorough, albeit probably still not perfect. For now, I have all the stuff about the Content Freelancer Google Sheet left in TODOs (and therefore not posted), because I need to finish fully documenting all the new page layouts before that can happen. I started doing that on a notes page last week, but I will probably move it onto the page for the `spartan` project, once I get it built. Since this is really documentation relating to `spartan` content structure.

It may be a bit until I get all of that finalized. In the meantime, the Meeting Google Sheets will be getting updated according to the new process, so it is a start.

### Another long Zoom meeting to go over all the things

My Content Freelancer friend and I had another long Zoom meeting this week, so that I could go over the details of the new weekly procedure I got a start on documenting.

Things we went over together, in no particular order:

- The much more comprehensive weekly process write up
  - Now there are three distinct phases to post processing, not just one or two
- A couple sections from last week still have to-dos, because I hadn't formatted the shortcodes properly initially
- Leave blank lines between parameters in `properties` shortcodes
- Adding `parent` parameter to `group-discussion-video-page` section `properties` shortcodes
- How `content-short-title` ought to be formatted (=using square brackets at end of title to specify source for follow-on topic videos, and discussion for group discussion videos).
  - You may need to go reformat the short titles you specified last week
- Taking notes when watching video clips as part of post-processing. Doing it upfront when organizing content (i.e., as part of the first post-processing phase, when specifying thumbnail descriptions), and then using these notes to specify rest of the metadata later too.
- Replacing Bible passage references with scripture shortcodes. (I just forgot to mention this last week).
- More stuff when setting up Meeting Google Sheet rows
  - Renamed columns to Study and Page
  - Linking to webpage sections for Page column
  - Linking to source clip sections on webpages as video link for source clip segments
- A more formal description of roll-up summaries, subject tags, passage tags, and review questions
- Playlist metadata: `playlist-short-title` and `playlist-thumbnail-description`
- When and when not to use different types of review questions (particularly fill-in-the-blank questions)
  - Optional words in fill-in-the-blank answers: specify answers using regular expression syntax, using `()` and `|`.
  - So `(The Holy Spirit|Holy Spirit)` will match either `The Holy Spirit` or `Holy Spirit`.

{{% /content %}}

{{% section-navigation %}}
