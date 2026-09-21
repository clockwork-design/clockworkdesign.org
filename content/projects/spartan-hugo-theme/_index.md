---
layout: single-page
title: Spartan Hugo theme
weight: 
---

The `spartan-hugo-theme` project is a [Hugo](https://gohugo.io/) theme associated with the [`spartan` project](/projects/spartan), which is an automation framework aimed at helping content-first high-throughput content creators sustainably scale production volumes.

<!--more-->

{{% section-navigation %}}

## Summary

<!-- summary -->

The `spartan-hugo-theme` project is a [Hugo](https://gohugo.io/) theme associated with the [`spartan` project](/projects/spartan), which is an automation framework aimed at helping content-first high-throughput content creators sustainably scale production volumes.

<!-- summary -->

{{% content %}}

## Content

This is very much a work in progress at the moment. I will work on getting documentation broken out better after getting more down on paper.

### Frontmatter structure

TODOs:

- Convert `ptags` into `passage-tags`
- Convert `stags` into `subject-tags`
- Convert `category` into `meeting-category`
- Convert `date` into `meeting-start-date`

I use YAML (rather than TOML), at the moment.

Frontmatter is divided into multiple sections, and parameters are organized alphabetically within each section. The sections themselves are not listed alphabetically, but in what amounts to an arbitrary order, based upon what I think makes the most sense.

I am planning to rename some of the parameters. I am currently generating new content with the old parameters names, but sorted in the alphabetical order of what the new parameter names will be, if that makes sense. (So that when I global rename later, everything will automatically be in the right order). Refactoring will involve several steps:

- Renaming parameters in frontmatter and properties shortcodes everywhere
- Updating Hugo layouts and templates to use the new parameter names
- Updating the `spartan` Python project to use the new parameter names

The sections (in the order that they will show up in frontmatter):

No prefix = Hugo/webpage related

- `date`: will mostly be used for blog posts, since that is the only content type I support that actually has specific dates attached.
- `layout`: specifies which Hugo template to use to render the page. I split things out in a very fine-grained fashion (see below for write ups on the main types of layouts).
- `passage-tags`: this parameter will only be relevant for content that is related to some text (e.g., Bible study content; content going over other ancient texts that are organized by section/book/line number, and so on). It is used to tag content pages with the specific text passages that it goes overs/discusses, and then bidirectional links are set up between content and a passage index page.
- `subject-tags`: this parameter is where general subject tags are specified. The `spartan-hugo-theme` and `spartan` projects together support the construction of a subject tagging system with bidirectional links between pages/headers on pages, and an exhaustive subject index page. (I should note that supporting bidirectional tags down at the header/section level is the killer feature, since Hugo's native [taxonomies](https://gohugo.io/content-management/taxonomies/) only operate at the page level, not the header/section level).
- `title`: The page title. For consistency, both directory names and page names are always based on title, and are never shortened or truncated. This means that websites that use the `spartan-hugo-theme` and `spartan` projects will almost certainly require setting up long path support at the operating system level, the git level, and the file manager level. This may sound like a lot of extra work, but I think making file paths 100% consistent and deterministic is worth it.
- `weight`: for content that is sorted arbitrarily rather than alphabetically, this parameter is what is used to make that happen. Content you want to appear first should have lower weights than content you want to appear later (cf. Hugo's [`ByWeight`](https://gohugo.io/methods/pages/byweight/) method).

Things related to meeting list pages (these parameters are used on various page layouts that can be associated with one of the discussion group meetings I hold weekly: `original-content-aggregation-video-page` pages, `original-content-single-video-page` pages, `discussion-aggregation-video-page` pages, and `discussion-single-video-page` pages):

- `meeting-category`: at the moment, I run two types of weekly meetings that so happen to be Bible studies (the [BibleDocs Open Bible Study](https://www.bibledocs.org/meta/bibledocs-weekly-bible-studies/bibledocs-open-bible-study/) and the [BibleDocs Ichthys Bible Study](https://www.bibledocs.org/meta/bibledocs-weekly-bible-studies/bibledocs-ichthys-bible-study/)), although the concept generalizes just fine to any kind of meeting, which is why I have named the parameters generically.
- `meeting-start-date`: in how I have the theme set up, meeting list pages only ever list higher-order content (i.e., `original-content-aggregation-video-page` pages, `original-content-single-video-page` pages, `discussion-aggregation-video-page` pages, and `discussion-single-video-page` pages), rather than all the sub-pages. So the reason why this parameter is `meeting-start-date` rather than just `meeting-date` is because it can take multiple weeks to get through one of these higher-order content pages, if there are multiple sub-pages that go along with it. So the date conceptually represents the date we *started* the higher-order page in our meeting.

Metadata relating to the YouTube/podcast version of content (only for content pages; see write ups of page layouts below)

- `content-comment-call-to-action`: a string outlining two or more questions to prompt user comments on YouTube videos. 
- `content-end-card-next-video`: a YouTube video URL for the content to show up on the video end card as the "next in sequence" video.
- `content-end-card-suggestion`: a YouTube video URL for the content to show up on the video end card as the "see also" video.
- `content-short-title`: the version of the title that will be used as the title for the YouTube video and podcast version of the content. Can be the same as the normal title, or be a shortened version of it. For `source-clip-video-pages`, source specification is moved to the end, so that it doesn't take up precious visible space (given that so few characters in titles can actually get displayed on YouTube, e.g., at any given point in time).
- `content-thumbnail-description`: a string describing what the thumbnail should be. Will be given to a freelancer to generate the thumbnail

Metadata relating to the YouTube/podcast playlist associated with the list page or roll-up pages (see write ups of page layouts below):

- `playlist-short-title`: directly analogous to `content-short-title`, but for pages that will turn into playlists rather than content videos.
- `playlist-thumbnail-description`: directly analogous to `content-thumbnail-description`, but for pages that will turn into playlists rather than content videos.

### Properties shortcode structure

TODOs:

- Convert `ptags` into `passage-tags`
- Convert `stags` into `subject-tags`
- Convert `srctitle` into `audio-title` and `youtube-title`
- Convert `srcmp3audiourl` into `audio-url`
- Convert `srcyoutubevideoid` into `youtube-url`
- Convert `srcstart` into `audio-beginning-timestamp` and `youtube-beginning-timestamp`
- Convert `srcend` into `audio-end-timestamp` and `youtube-end-timestamp`
- Convert HTML comments into `audio-beginning-text`/`youtube-beginning-text` and `audio-end-text`/`youtube-end-text`

The `spartan-hugo-theme` at present uses a shortcode called `properties` to specify properties that belong to sections/headers. Once I shift everything to Org rather than Markdown, these `properties` shortcodes will get transformed into collapsible [Org properties drawers](https://orgmode.org/manual/Property-Syntax.html), which will keep content buffers by default only displaying content itself, not metadata.

The `properties` shortcodes have sections just like frontmatter, and work basically the same way (i.e., section order is arbitrary, but parameters within each section are alphabetical).

Because Org properties drawers do not support blank lines between properties in drawers, sections in properties shortcodes are not separated by blank lines (unlike frontmatter).

The sections (in the order that they will show up in the `properties` drawers):

No prefix = Hugo/webpage related:

- `parent`: will only be used in the `properties` shortcode belonging to a `group-discussion-video-page` header on a `combined-page`. (See below for write up documenting page layouts).
- `passage-tags`: like the frontmatter parameter, but just at the header level.
- `subject-tags`: like the frontmatter parameter, but just at the header level.
- `timestamp`: is not something that will be manually set or adjusted, but set via automated script. This value will be combined with the video URL specified on content pages to make it so that every section has a button/link that adjusts the embedded YouTube video player to jump to the timestamp in the video associated with the specific header/section.

Related to video/podcast version of content. Only for the `properties` shortcode belonging to a content page header on a `combined-page`. (See below for write up documenting page layouts).

- `content-end-card-next-in-sequence`: works same as frontmatter parameter, just defined in section metadata here.
- `content-end-card-see-also`: works same as frontmatter parameter, just defined in section metadata here.
- `content-short-title`: works same as frontmatter parameter, just defined in section metadata here.
- `content-thumbnail-description`: works same as frontmatter parameter, just defined in section metadata here.

Related to embedded audio via HTML `audio` tag. Only used under headers that are in the format `Source clip from {source}`, where the source is an audio file (e.g., an MP3 file).

- `audio-beginning-text`: only specified if do not have access to a clean text version of the audio content to quote. Specifies what text the source clip should begin with, so that the correct timestamp can be determined.
- `audio-end-text`: only specified if do not have access to a clean text version of the audio content to quote. Specifies what text the source clip should end with, so that the correct timestamp can be determined.
- `audio-beginning-timestamp`: specifies the second corresponding to the `audio-beginning-text` or the beginning of the quoted fully-reproduced clean text version of the source clip. Needs to be in the format of `hh:mm:ss`.
- `audio-end-timestamp`: specifies the second corresponding to the `audio-end-text` or the end of the quoted fully-reproduced clean text version of the source clip. Needs to be in the format of `hh:mm:ss`.
- `audio-title`: specifies the title of the source audio clip being embedded
- `audio-url`: specifies the URL of the source audio clip being embedded. (Must point directly to an audio file).

Related to embedded YouTube video via iframe. Only used under headers that are in the format `Source clip from {source}`, where the source is a YouTube video.

- `youtube-beginning-text`: only specified if do not have access to a clean text version of the YouTube content to quote. Specifies what text the source clip should begin with, so that the correct timestamp can be determined.
- `youtube-end-text`: only specified if do not have access to a clean text version of the YouTube content to quote. Specifies what text the source clip should end with, so that the correct timestamp can be determined.
- `youtube-beginning-timestamp`: specifies the second corresponding to the `youtube-beginning-text` or the beginning of the quoted fully-reproduced clean text version of the source clip. Needs to be in the format of raw seconds.
- `youtube-end-timestamp`: specifies the second corresponding to the `youtube-end-text` or the end of the quoted fully-reproduced clean text version of the source clip. Needs to be in the format of raw seconds.
- `youtube-title`: specifies the title of the source YouTube clip being embedded
- `youtube-url`: specifies the URL of the source YouTube clip being embedded. (Must point directly to a YouTube video).


{{% /content %}}

{{% section-navigation %}}