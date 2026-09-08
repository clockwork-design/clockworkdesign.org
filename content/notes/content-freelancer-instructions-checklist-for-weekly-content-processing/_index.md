---
layout: single-page
stags: 
title: "Content freelancer instructions: Checklist for weekly content processing"
---

This page describes the weekly content workflow that myself and the freelancer directly helping me with content (i.e., summaries, subject tags, review questions, and so on) will follow. At present, I use this process for content from two weekly Bible studies, but it would generalize just fine to other sorts of content too.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

This page describes the weekly content workflow that myself and the freelancer directly helping me with content (i.e., summaries, subject tags, review questions, and so on) will follow. At present, I use this process for content from two weekly Bible studies, but it would generalize just fine to other sorts of content too.

<!-- summary -->

{{% content %}}

## Content {#content}

### Before recording (pre-processing)

1. Steven: scaffold new section(s) in the `content-page` file (plus a new `content-page` itself, if it is going to be a new discussion source entirely)
1. Steven: Specify start and stop points for next week's source clip(s) (either the full transcript text if it is available = [Ichthys](https://ichthys.com/) is the source, or the points around the transitions with the exact words **bolded** = some YouTube video is the source)
1. Steven: Message content freelancer that content is ready to pre-process
1. Content freelancer: Fill in exact timestamps for start and stop points of source clips
1. Content freelancer: If source clip has full transcript, convert it to proper Markdown format (including `scripture` shortcodes and `ichthys-translation` shortcodes)
1. Content freelancer: Message Steven that content pre-processing is done
1. Steven: If source clip has full transcript, add slide breaks
1. Steven: Write content for summary points and follow-on topics

The deadline for weekly pre-processing to be done is Saturday afternoon at 12:00 PM Eastern Time.

I will make sure you get the content to pre-process no later than mid-day the Sunday before, which will give you ballpark six days to finish the pre-processing. If a week will not have pre-processing, I will make sure to still message you and let you know that.

### During recording

1. Steven: Add the current timestamp just before starting a new recording segment (on the end of the `date` frontmatter property), so that things will get ordered properly on Bible study list pages.
1. Steven: If recording a Group Discussion recording segment, un-mute the 8-channel wireless mic system (and then re-mute it after finishing). This prevents unwanted noise during the recording of wider introductions, overviews, summary points, follow-on topics, etc. (basically, anything that is not group discussion).
1. Steven: Delete Group Discussion sections from the Markdown content file if they don't end up happening in practice.

### After recording (post-processing)

1. Steven: Organize video segments in Dropbox folder
1. Steven: Update freelancing Google Sheet
1. Steven: Message content freelancer that content is ready to post-process
1. Content freelancer: [Add embedded video clips for Dropbox recording segments](content-freelancer-instructions-add-embedded-video-clips-for-dropbox-recording-segments)
1. Content freelancer: [Add properly-formatted scripture shortcodes during post-processing, if `outline-content` or `live-content`](/notes/content-freelancer-instructions-add-properly-formatted-scripture-shortcodes-during-post-processing-if-outline-content-or-live-content)
1. Content freelancer: [Add slide breaks during post-processing, if `outline-content` or `live-content`](/notes/content-freelancer-instructions-add-slide-breaks-during-post-processing-if-outline-content-or-live-content)
1. Content freelancer: [Add/update summaries](content-freelancer-instructions-rolling-up-summaries-tags-and-review-questions)
1. Content freelancer: [Add/update subject tags](content-freelancer-instructions-rolling-up-summaries-tags-and-review-questions)
1. Content freelancer: [Add/update passage tags](content-freelancer-instructions-rolling-up-summaries-tags-and-review-questions)
1. Content freelancer: [Add/update review questions](content-freelancer-instructions-rolling-up-summaries-tags-and-review-questions)
1. Content freelancer: Message Steven that content post-processing is done
1. Steven: Add `short-title` and `thumbnail-description` properties where appropriate
1. Steven: Run pre-processor Python application, check over git diff, commit, push
1. Steven: Update Bible study Google Sheets
1. Steven: Message group chats letting folks know content for the week is live

The deadline for weekly post-processing to be done is Friday afternoon at 5:00 PM Eastern Time. I want to send out the "content is live" message to Bible study attendees sometime Friday evening, so that anybody who wants or needs to watch last week's content has enough time to do so before the Saturday meetings. (Note that the post-processing for the last week is actually due *before* the pre-processing for the next week. So in terms of how you prioritize what you work on first, keep that in mind).

I will make sure you get the content to post-process no later than mid-day the Sunday before, which will give you ballpark five days to finish the post-processing. If a week will not have post-processing, I will make sure to still message you and let you know that.

## Changelog

### 2026-09-04

The process was modified in several primary overarching ways:

1. Weekly deadlines were established for me (mid-day Sunday) and you = the content freelancer (Friday afternoon; mid-day Saturday), to ensure that we consistently complete all pre-processing and post-processing every week, so nothing piles up and requires future adjustments.
2. The way content is organized was updated substantially, to split out every recording segment (be that a summary points section, follow-on topic section, or group discussion section) into its own video, with corresponding split-out summaries, subject tags, passage tags, review questions, etc. This much-more-split-out structure will require a lot of additional work on our part, but will lead to content that is *much* more bite-size overall, and therefore much easier to consume. Think videos that are under 30 minutes (and sometimes even under 15 minutes), rather than videos that are multiple hours long.
3. For the time being, after you finish catching up on review questions for the remaining BibleDocs Ichthys Bible Study weeks like we've discussed, I am going to have you only focus on keeping up with new content week-by-week. It will take me some time to get the content backlog updated to be in the new split-out format, at which point we will have to revisit all of it to add/update summaries, subject tags, passage tags, review questions, etc. to everything that has been split out. That will be quite an effort, but we will worry about that later. First, let's just focus on getting all our new content following the desired long-term structure.

Here is a more full list of changes:

- What studies had previously been labeled `live-content` have now been renamed to be `outline-content`. I did this because these studies ended up not being truly live, but well, based off of outlines. The `live-content` content type will probably be used eventually if and when I do true Live Q&As, but what we have been doing recently just isn't that. Not really.
- Content file structure has changed substantially. See [Content freelancer instructions: Content file structure](content-freelancer-instructions-content-file-structure).
  - The new more-split-out content file structure will mean that another dimension has been added to post-processing: figuring out how to "roll up" summaries, tags, and review questions, if necessary. Since every piece of content in the new structure has its own summary, subject tags, passage tags, and review questions, it will be necessary to figure out what things are shared, and what things should stay separated. Since this is a bit confusing, I wrote up a page explaining it in detail: [Content freelancer instructions: Rolling up summaries, tags, and review questions](content-freelancer-instructions-rolling-up-summaries-tags-and-review-questions).
- The structure of the Content Freelancing Google Sheet has changed substantially, to account for the more-split-out structure. See [Content freelancer instructions: Content Freelancing Google Sheet](content-freelancer-instructions-content-freelancing-google-sheet). Different types of sections require different things in terms of pre-processing and post-processing (some of these being completely new relative to what we were doing before), but what needs to be done will always be made clear in the Content Freelancing Google Sheet, so you will never have to guess.
  - Independent from the structure changes in the Content Freelancing Google Sheet related to having more-split-out sections, I also removed the columns to track how many hours you spent on specific tasks, and decided to switch to a fixed weekly amount, paid monthly. That way you won't have to waste time trying to keep up with exactly what amount of time you spent on what. I trust you unconditionally (unlike freelancers whom I do not know in my personal life), so we can get away with less bookkeeping in this way, which will save you time and admin overhead overall. We can talk about what weekly rate is fair as part of me going over all this with you.
  - I also changed the title of the checkbox column to open files in VSCode to just "C", standing for "Content freelancer" (rather than your initial, as previously).
- The structure of the Bible Study Google Sheets have changed substantially, to account for the more-split-out structure. See [Meeting Google Sheets](meeting-google-sheets).
- I will now pause for group discussion during the Bible studies after every summary point section and every individual follow-on topic, rather than only having one single group discussion time after going through everything in a section. This will keep group discussion segments more separated and focused, leading to shorter group discussion videos overall.
- I will now add parameters called `short-title` and `thumbnail-description` to every recording segment that will become a video of its own, to keep up week-by-week with content design decisions. (These parameters will eventually be used when the YouTube videos and podcast episodes are actually made).
- Rather than having a single link to a Dropbox folder containing recording segments, recording segments will now show up as embedded videos directly on the pages (just like the embedded YouTube video source clips, except that these are our own recording segments hosted on Dropbox).

<!--

How things will change after split script is written:

- Before the pre-process/check/commit/push step, run the split script
- Add Update freelancing Google Sheet step at the end, to make the individual page links correct

How things will change when videos are actually going to be generated:

- After running the split script, generate the videos, and check them over. Then push them live

-->

{{% /content %}}

{{% section-navigation %}}
