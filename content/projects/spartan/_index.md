---
layout: single-page
title: Spartan
weight: 
---

The `spartan` project is an automation framework aimed at helping content-first high-throughput content creators sustainably scale production volumes.

<!--more-->

{{% section-navigation %}}

## Summary

<!-- summary -->

The `spartan` project is an automation framework aimed at helping content-first high-throughput content creators sustainably scale production volumes.

<!-- summary -->

{{% content %}}

## Content

### YouTube video ending clip

Every video will end with 20 seconds of end cards being displayed

The AI text-to-speech tool should read out "Thanks for watching. Please remember to like and subscribe and share if you found this video to be useful, to feed the algorithms positive signals. You can also comment below. {Custom comment call to action}"

- The `{Custom comment call to action}` comes from the frontmatter parameter `content-comment-call-to-action`. For example, it might be something like "Had you ever heard of the People's Crusade before? Do you have examples of modern movements that share some of the same apocalyptic tendencies?"

There are three basic end card layouts. Which one is used depends upon the `content-end-card-next-video` and `content-end-card-suggestion` frontmatter parameters:

1. If `content-end-card-next-video` and `content-end-card-suggestion` are both blank, then the end card layout has a `Playlist` link. This end card format is very temporary, and will basically only exist until the next video gets posted so that the `Next Video` link can be used.
2. If `content-end-card-next-video` is non-blank but `content-end-card-suggestion` is blank, then the only change is basically that the `Playlist` link gets replaced with a `Next Video` link
3. If `content-end-card-next-video` and `content-end-card-suggestion` are both non-blank, then the end card template is switched to one with two slots for video links, rather than just one, and there are both `Suggestion` and `Next Video` links.

Regardless of which of the three end card templates is used to embed video links, the remaining elements that show up on the end cards (albeit perhaps in slightly different places depending upon the template) are always the same:

- There is a subscribe button and graphic
- There is a row of icon plus handle graphics, to let people know what to follow on other platforms:
  - Website: bibledocs.org
  - Facebook: BibleDocs
  - Twitter/X: @BibleDocs
  - Instagram:
  - TikTok:

### Podcast episode ending clip

Similar to YouTube end cards, but slightly different wording. What will the text say?

Maybe something like "Thanks for listening. Please remember to follow and share if you found this podcast episode to be useful, to feed the algorithms positive signals."

{{% /content %}}

{{% section-navigation %}}