---
layout: single-page
stags: 
title: "Content freelancer instructions: Content file structure"
---

TODO: Summary

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

TODO: Summary

<!-- summary -->

{{% content %}}

## Content {#content}

### Overview

At present, we only have to deal with video content pages (since the only content I am currently putting out is coming from weekly recorded Bible studies; this may change later). So for now, either we will be going through someone elses's content by playing back source video/audio clips and discussing them (so-called discussion content), or else we will be going through some original content that I wrote myself. These two cases have slightly different structures: 

- Discussion content always has a source clip video page which contains discussion of the source clip, and often contains one or more follow-on topic video pages too, which go over original content I write that is designed to supplement and expand upon the topics gone over in the source.
- Original content does not have this extra layer of sub-organization.

Both discussion content and original content can end up being organized into shorter pages without any subdivision into sections (so-called "single pages"), or organized into longer pages that are composed of multiple different sections strung together in sequence (so-called "aggregation pages").

A final sort of distinction between pages is based upon their wider type:

- Content pages: pages that have the main text sections (like `content` and `transcript`). These are the pages where content actually lives.
- Roll-up pages: pages that roll up summary, video, and timestamp sections, so that the basics from multiple sub-pages can be seen all on one place. As you might expect, all aggregation pages are roll-up pages.
- List pages: pages that list other pages (i.e., display titles and summaries), without actually rolling anything up (like videos or timestamps).

### Content starts out all combined into one file (for ease of drafting), and is only later split out

Right now, despite being broadly structured in the manner we discuss here, all content is actually being drafted on single pages (that have the layout `content-page`). This is because it will be more efficient in the long-term to let a script handle the creation of nested pages automatically (rather than having to both manually type out a title and then also manually generate a folder or file with the same name except in `kabob-case`, and so on).

In the descriptions of the page layouts below, I go over both what the final form of each page layout will be (i.e., once everything is properly split-out onto separate pages), and what form it currently takes on the combined pages. Frontmatter for the pages that will be split out *is* specified on the combined pages, inside of `frontmatter` shortcodes.

On the combined pages, so that we don't get too deeply nested with respect to header levels (which only conventionally range from `h2` to `h6` for non-title page headers), the top level of headers on all content pages is collapsed (i.e., rather than having `Summary`, `Video`, `Timestamps`, `Content` etc. sub-headers, everything is all together at the same level). The added level of organization will be automatically added back when the pages actually get split out. The same thing is true for the display of roll-up pages on combined pages (so, for example, the page headers corresponding to `discussion-section-video-page` pages do not have `Summary`, `Content`, etc. sub-headers, but also have everything together at the same level).

Given that under this approach everything has been collapsed to be at the same level, summaries are made to be clearly distinguished from normal content by wrapping them in `summary` shortcodes. These `summary` shortcodes are only used on combined pages; once things get fully split out, summaries will be under `Summary` headers, like normal.

Also to avoid getting too deeply nested with respect to header levels, group discussion pages that fall under different sorts of content pages (like `original-content-single-video-page`, `source-clip-video-page`, `follow-on-topic-video-page`, etc. pages) are *not* actually nested under the pages they belong to in the combined page header hierarchy, but have instead been promoted to be at the same header level as the pages they belong to (i.e., have become their "siblings" with respect to header level). To make it clear which page they actually belong to, group discussion sections on the combined pages have an extra frontmatter parameter (that won't ultimately carry over into the frontmatter of the final split-out pages = this is a frontmatter parameter for group discussion pages only in the `frontmatter` shortcodes on combined pages) called `parent`. This parameter will be equal to the title of whatever page is their parent.

In short, there are a few special things done to support drafting content on combined pages that make the format look a bit different on these combined pages than what the final format will be once everything gets fully split out. I should be clear that everything can be cleanly mapped back and forth between the combined and split-out formats, meaning all things are supported either way (even if what that looks like in practice ends up being a bit different across the two).

{{% note %}}

Right at the moment, all content will be staying permanently in the combined format, and never split out. Why? Mostly just because I haven't coded it (or paid some else to code it) yet, and also do not yet have all the different page layouts supported in my website theme.

It is only very recently that I decided I wanted to have content be very split-out, and the codebase just has not yet had time to catch up with this new way of doing things. So in the short-term, I will continue having all content located on combined pages with the `content-page` page layout, just like before. Everything has been carefully arranged to work perfectly with that format (which is what the codebase currently expects), but in such a way that splitting things out will be still able to be automated and done programmatically at a later date, once the relevant script gets coded.

{{% /note %}}

### Content pages

All content pages share the same basic format, having these sub-headers:

- Summary
- Video
- Timestamps
- Transcript
- Content
- Review questions

When content pages show up in collapsed form on combined pages, they will not have videos, timestamps, and transcripts, since these things will only come about when the videos are actually built after content is split out.

Of all the content pages, `original-content-single-video-page` pages are the only ones that piggyback on the core structure of combined pages (i.e., rather than being header sections on the page, the combined page essentially "is" an `original-content-single-video-page`).

#### Layout: `original-content-single-video-page`

This layout represents the smallest normal unit of content organization for single-page original content. It can have a single child group discussion page (with layout `group-discussion-video-page`; see below). The equivalent of this layout for discussion content (i.e., `discussion-single-video-page`) is not actually a content page but a roll-up page, since discussion content is always inherently split into `source-clip-video-page` pages and `follow-on-topic-video-page` pages.

##### Format on combined pages

```markdown

---
category: 
date: 
layout: content-page
ptags: 
stags: 
short-title: 
thumbnail-description: 
title: "{original-content-single-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

TODO: Content

### Group Discussion: {title}

{{</* properties 

parent="{original-content-single-video-page-title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

{{%/* /content */%}}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: original-content-single-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "{original-content-single-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

## Content

TODO: Content

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

## [Group discussion: {title}](group-discussion-{title})

### Summary

TODO: Summary

### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

### Timestamps

TODO: Timestamps

```

#### Layout: `original-content-section-video-page`

This layout represents the smallest normal unit of content organization for aggregation-page original content. It can have a single child group discussion page (with layout `group-discussion-video-page`; see below). The equivalent of this layout for discussion content (i.e., `discussion-section-video-page`) is not actually a content page but a roll-up page, since discussion content is always inherently split into `source-clip-video-page` pages and `follow-on-topic-video-page` pages.

##### Format on combined pages

```markdown

### {original-content-section-video-page-title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="{original-content-section-video-page-title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}


## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: original-content-section-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "{original-content-section-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

## Content

TODO: Content

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

## [Group discussion: {title}](group-discussion-{title})

### Summary

TODO: Summary

### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

### Timestamps

TODO: Timestamps

```

#### Layout: `source-clip-video-page`

This layout represents one of the two smallest normal units of content organization for discussion content (with `follow-on-topic-video-page` being the other; see below). It can have a single child group discussion page (with layout `group-discussion-video-page`; see below).

##### Format on combined pages

If you are on a discussion aggregation page under a section header, relative to what is shown below, add a header level to every header.

```markdown

### {source}: {discussion-single-video-page-title OR discussion-section-video-page-title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{</* discussion-note src="{source}" text="{work-title}" url="{work-url}" */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

#### Overview

#### Source clip from {source}

{{</* properties 

srcmp3audiourl=""
srcyoutubevideoid=""
srctitle=""
srcstart=""
srcend=""

*/>}}

#### Summary points

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="{source}: {discussion-single-video-page-title OR discussion-section-video-page-title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: source-clip-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "{source}: {discussion-single-video-page-title OR discussion-section-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

{{</* discussion-note src="{source}" text="{work-title}" url="{work-url}" */>}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

## Content

### Overview

### Source clip from {source}

{{</* properties 

srcmp3audiourl=""
srcyoutubevideoid=""
srctitle=""
srcstart=""
srcend=""

*/>}}

### Summary points

TODO: Content

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

## [Group discussion: {title}](group-discussion-{title})

### Summary

TODO: Summary

### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

### Timestamps

TODO: Timestamps

```

#### Layout: `follow-on-topic-video-page`

This layout represents one of the two smallest normal units of content organization for discussion content (with `source-clip-video-page` being the other; see above). It can have a single child group discussion page (with layout `group-discussion-video-page`; see below).

##### Format on combined pages

If you are on a discussion aggregation page under a section header, relative to what is shown below, add a header level to every header.

```markdown

### Follow-on topic: {title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="Follow-on topic: {title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: follow-on-topic-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "Follow-on topic: {title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

## Content

TODO: Content

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

## [Group discussion: {title}](group-discussion-{title})

### Summary

TODO: Summary

### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

### Timestamps

TODO: Timestamps

```

#### Layout: `group-discussion-video-page`

This layout is for group discussion pages. By convention, we do not discuss the same thing more than once (so each content page can only ever have a single group discussion page under it). For all new content, group discussion can *only* fall under a content page (and never under a section page, for example). Some older content had group discussion at the section level, but that has now been deprecated, so that now group discussion is kept nice and split-out, just like everything else.

Most of the time, group discussion pages will have their own unique titles that correspond to what specifically was discussed (i.e., a narrower topic than the page they fall under). However, occasionally their title may match the page they are under, except with "Group Discussion:" pre-pended. This happens when the discussion is wide-ranging enough that it is difficult to pick a more focused title, because many different topics from the parent page were discussed, rather than just one or two.

##### Format on combined pages

If you are on an aggregation page (either a discussion aggregation page or an original content aggregation page) under a section header, relative to what is shown below, add a header level to every header.

```markdown

### Group Discussion: {title}

{{</* properties 

parent="{parent-title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: group-discussion-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "Group discussion: {title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

## Content

TODO: Content

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

#### Layout: `wider-introduction-video-page`

Aggregation pages (both discussion aggregation pages and original content aggregation pages) can optionally have wider introduction pages that outline what will be gone over. These cannot have any child group discussion pages belong to them, because they are always very short. They also do not have normal post-processing metadata like a summary, subject tags, passage tags, or review questions, again, because they are so short, and because they are themselves *already* summary content, without unique content of their own.

They will always show up as the first section on the aggregation page, before any content sections proper.

##### Format on combined pages

```markdown

### Wider introduction: {discussion-aggregation-video-page-title OR original-content-aggregation-video-page-title}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}


```

##### Format once fully split-out

```markdown

---
layout: wider-introduction-video-page
meeting-category: 
meeting-datetime: 
short-title: 
thumbnail-description: 
title: "Wider introduction: {discussion-aggregation-video-page-title OR original-content-aggregation-video-page-title}"
weight: 
---

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

```

#### Layout: `discussion-tangent-video-page`

Discussion aggregation pages can have optionally have discussion tangent pages that basically act as section pages that are all original content, rather than going over a section from the source content. These are used mostly if I want to go over something that the source content does not directly talk about, but still want it to end up organized within the same study as the source content sections. These are pretty uncommon, on the whole. A discussion tangent page can have a single child group discussion page (with layout `group-discussion-video-page`; see above).

##### Format on combined pages

If you are on a discussion aggregation page under a section header, relative to what is shown below, add a header level to every header.

```markdown

### Tangent: {title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="Tangent: {title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: discussion-tangent-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "Tangent: {title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

## Timestamps

TODO: Timestamps

{{%/* transcript */%}}

## Transcript

TODO: Transcript

{{%/* /transcript */%}}

## Content

TODO: Content

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

## [Group discussion: {title}](group-discussion-{title})

### Summary

TODO: Summary

### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

### Timestamps

TODO: Timestamps

```

### Roll-up pages

All roll-up pages share the same basic format, having these sub-headers:

- Summary
- Content (where the sub-pages roll up)
- Review questions

Of all the roll-up pages, `discussion-single-video-page` pages, `original-content-aggregation-video-page` pages, and `discussion-aggregation-video-page` pages all piggyback on the core structure of combined pages (i.e., rather than being header sections on the page, the combined page essentially "is" a `discussion-single-video-page` page, `original-content-aggregation-video-page` page, or `discussion-aggregation-video-page` page).

That leaves `discussion-section-video-page` pages as the only roll-up page that shows up in header form on combined pages. Everything works how you might expect, except that the `quizdown` shortcode for the `discussion-section-video-page` header is put immediately under the summary shortcode (i.e., essentially moved up to the top, before the `source-clip-video-page` header). This is so that there is no ambiguity with respect to what header these review questions go with. This is necessary because we collapse the base header level of roll-up pages (i.e., `Summary`, `Content`, etc.) on combined pages. These headers also don't have a `frontmatter` shortcode, because these discussion section pages don't have any of the three parameters that are specified on combined pages in `frontmatter` shortcodes (i.e., `meeting-datetime`, `short-title`, and `thumbnail-description`).

#### Layout: `discussion-single-video-page`

A `discussion-single-video-page` consists of a single `source-clip-video-page` page (and its associated group discussion page, if applicable), plus one or more `follow-on-topic-video-page` pages (and their associated group discussion pages, if applicable). In its split-out form, it looks basically identical to a `discussion-section-video-page` page. The difference is how it shows up on combined pages: combined pages corresponding to `discussion-aggregation-video-page` pages have multiple `discussion-section-video-page` headers strung together, but combined pages corresponding to `discussion-single-video-page` pages have no added sub-level of organization.

##### Format on combined pages

```markdown

---
category: 
date: 
layout: content-page
ptags: 
stags: 
short-title: 
thumbnail-description: 
title: "{discussion-single-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {source}: {discussion-single-video-page-title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{</* discussion-note src="{source}" text="{work-title}" url="{work-url}" */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

#### Overview

#### Source clip from {source}

{{</* properties 

srcmp3audiourl=""
srcyoutubevideoid=""
srctitle=""
srcstart=""
srcend=""

*/>}}

#### Summary points

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="{source}: {discussion-single-video-page-title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Follow-on topic: {title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="Follow-on topic: {title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

{{%/* /content */%}}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: discussion-single-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "{discussion-single-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {source}: {discussion-single-video-page-title}

#### Summary

TODO: Summary

#### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

#### Timestamps

TODO: Timestamps

#### Group Discussion: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

### Follow-on topic: {title}

#### Summary

TODO: Summary

#### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

#### Timestamps

TODO: Timestamps

#### Group Discussion: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

#### Layout: `discussion-section-video-page`

A `discussion-section-video-page` consists of a single `source-clip-video-page` page (and its associated group discussion page, if applicable), plus one or more `follow-on-topic-video-page` pages (and their associated group discussion pages, if applicable). In its split-out form, it looks basically identical to a `discussion-single-video-page` page. The difference is how it shows up on combined pages: combined pages corresponding to `discussion-aggregation-video-page` pages have multiple `discussion-section-video-page` headers strung together, but combined pages corresponding to `discussion-single-video-page` pages have no added sub-level of organization.

##### Format on combined pages

```markdown

### {discussion-section-video-page-title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### {source}: {discussion-section-video-page-title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{</* discussion-note src="{source}" text="{work-title}" url="{work-url}" */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

##### Overview

##### Source clip from {source}

{{</* properties 

srcmp3audiourl=""
srcyoutubevideoid=""
srctitle=""
srcstart=""
srcend=""

*/>}}

##### Summary points

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Group Discussion: {title}

{{</* properties 

parent="{source}: {discussion-section-video-page-title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Follow-on topic: {title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Group Discussion: {title}

{{</* properties 

parent="Follow-on topic: {title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: discussion-section-video-page
passage-tags: 
subject-tags: 
title: "{discussion-section-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {source}: {discussion-section-video-page-title}

#### Summary

TODO: Summary

#### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

#### Timestamps

TODO: Timestamps

#### Group Discussion: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

### Follow-on topic: {title}

#### Summary

TODO: Summary

#### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

#### Timestamps

TODO: Timestamps

#### Group Discussion: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

#### Layout: `original-content-aggregation-video-page`

An `original-content-aggregation-video-page` page consists of multiple `original-content-section-video-page` pages strung together in sequence, possibly prefixed with a `wider-introduction-video-page`.

##### Format on combined pages

```markdown

---
category: 
date: 
layout: content-page
ptags: 
stags: 
short-title: 
thumbnail-description: 
title: "{original-content-aggregation-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {original-content-section-video-page-title-1}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="{original-content-section-video-page-title-1}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### {original-content-section-video-page-title-2}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### Group Discussion: {title}

{{</* properties 

parent="{original-content-section-video-page-title-2}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

{{%/* /content */%}}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: original-content-aggregation-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "{original-content-aggregation-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {original-content-section-video-page-title-1}

#### Summary

TODO: Summary

#### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

#### Timestamps

TODO: Timestamps

#### Group Discussion: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

### {original-content-section-video-page-title-2}

#### Summary

TODO: Summary

#### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

#### Timestamps

TODO: Timestamps

#### Group Discussion: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

{{%/* /content */%}}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

#### Layout: `discussion-aggregation-video-page`

A `discussion-aggregation-video-page` page consists of multiple `discussion-section-video-page` pages strung together in sequence, possibly prefixed with a `wider-introduction-video-page` page. There may also be one or more `discussion-tangent-video-page` pages interspersed throughout.

##### Format on combined pages

```markdown

---
category: 
date: 
layout: content-page
ptags: 
stags: 
short-title: 
thumbnail-description: 
title: "{discussion-aggregation-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {discussion-section-video-page-title-1}

{{</* properties 

ptags=""
stags=""

*/>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### {source}: {discussion-section-video-page-title-1}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{</* discussion-note src="{source}" text="{work-title}" url="{work-url}" */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

##### Overview

##### Source clip from {source}

{{</* properties 

srcmp3audiourl=""
srcyoutubevideoid=""
srctitle=""
srcstart=""
srcend=""

*/>}}

##### Summary points

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Group Discussion: {title}

{{</* properties 

parent="{source}: {discussion-section-video-page-title-1}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Follow-on topic: {title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Group Discussion: {title}

{{</* properties 

parent="Follow-on topic: {title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

### {discussion-section-video-page-title-2}

{{</* properties 

ptags=""
stags=""

*/>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### {source}: {discussion-section-video-page-title-2}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{</* discussion-note src="{source}" text="{work-title}" url="{work-url}" */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

##### Overview

##### Source clip from {source}

{{</* properties 

srcmp3audiourl=""
srcyoutubevideoid=""
srctitle=""
srcstart=""
srcend=""

*/>}}

##### Summary points

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Group Discussion: {title}

{{</* properties 

parent="{source}: {discussion-section-video-page-title-2}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Follow-on topic: {title}

{{</* properties 

ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

#### Group Discussion: {title}

{{</* properties 

parent="Follow-on topic: {title}"
ptags=""
stags=""

*/>}}

{{</* frontmatter */>}}

meeting-datetime: 
short-title: 
thumbnail-description: 

{{</* /frontmatter */>}}

{{%/* summary */%}}

TODO: Summary

{{%/* /summary */%}}

TODO: Content

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

{{%/* /content */%}}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

##### Format once fully split-out

```markdown

---
layout: discussion-aggregation-video-page
meeting-category: 
meeting-datetime: 
passage-tags: 
short-title: 
subject-tags: 
thumbnail-description: 
title: "{discussion-aggregation-video-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

{{%/* content */%}}

## Content

### {discussion-section-video-page-title-1}

#### Summary

TODO: Summary

#### {source}: {discussion-section-video-page-title-1}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

##### Group discussion: {title}

###### Summary

TODO: Summary

###### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

###### Timestamps

TODO: Timestamps

#### Follow-on topic: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

##### Group discussion: {title}

###### Summary

TODO: Summary

###### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

###### Timestamps

TODO: Timestamps

### {discussion-section-video-page-title-2}

#### Summary

TODO: Summary

#### {source}: {discussion-section-video-page-title-2}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

##### Group discussion: {title}

###### Summary

TODO: Summary

###### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

###### Timestamps

TODO: Timestamps

#### Follow-on topic: {title}

##### Summary

TODO: Summary

##### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

##### Timestamps

TODO: Timestamps

##### Group discussion: {title}

###### Summary

TODO: Summary

###### Video

{{</* properties 

srcyoutubevideoid=""
srctitle=""

*/>}}

###### Timestamps

TODO: Timestamps

{{%/* /content */%}}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

### List pages

List pages list content in a condensed form, only showing titles and summaries. You can have multiple layers of list pages between the site home page and any page with actual content, depending upon how many levels of higher-level organization there are.

At a high level, list pages are not for consuming content, but for finding content to consume. This is why they do not even roll up videos and timestamps.

List pages live above all the other kinds of pages. For example, the list page for all Ryan Reeves discussion is located at `https://www.bibledocs.org/discussion/ryan-reeves`.

As the content freelancer, you will not have to touch list pages much. Only the very most top-level subject tags, passage tags, and review questions will go on list pages (see [Content freelancer instructions: Rolling up summaries, tags, and review questions](content-freelancer-instructions-rolling-up-summaries-tags-and-review-questions)). And of course, list pages will also have summaries to write, just like basically all pages.

List pages have the `short-title` and `thumbnail-description` properties, since they can oftentimes correspond to playlists on YouTube/podcast hosts/etc., and playlists have titles and thumbnails in the same way that videos/podcast episodes/etc. themselves do.

#### Layout: `list-page`

```markdown

---
layout: list-page
ptags: 
short-title: 
stags: 
thumbnail-description: 
title: "{list-page-title}"
weight: 
---

TODO: Summary

<!--more-->

{{%/* section-navigation */%}}

## Summary

<!-- summary -->

TODO: Summary

<!-- summary -->

## List of {things}

## Review questions

{{</* quizdown */>}}

TODO: Review questions

{{</* /quizdown */>}}

```

{{% /content %}}

{{% section-navigation %}}
