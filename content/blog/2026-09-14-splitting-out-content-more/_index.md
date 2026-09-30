---
date: 2026-09-14T09:10:00
layout: content-page
stags: 
title: "2026-09-14: Splitting out content more"
---

To avoid multi-hour-long video lengths, I decided we need to split out content more. To support this, quite a bit has to be done to modify the workflow we had been using for content processing.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

To avoid multi-hour-long video lengths, I decided we need to split out content more. To support this, quite a bit has to be done to modify the workflow we had been using for content processing.

<!-- summary -->

{{% content %}}

## Content {#content}

### Changing direction in my content production workflow: split out content, not combined content

After the last year or so of recording weekly-ish Bible studies for [my online Bible teaching ministry](https://www.bibledocs.org/), I have a much better vision of how I want content to work in the long-term. We now have approximately 65 (!) full multi-hour-long Bible studies recorded and shared locally within the Bible study group chats.

As part of deciding how to actually get all this content posted publicly to YouTube (and after [a particularly long study](https://www.bibledocs.org/discussion/ryan-reeves/longer-topical-studies/early-and-medieval-history/the-first-crusades-part-i/)), it became apparent to me that for content to stay of reasonable length, I would need to split up sections from our weekly Bible Studies.

It might not be obvious on the surface how this decision increases content production workload, but the basics are something like this:

- For optimal UX, every video requires certain metadata (a short title, thumbnail, summary, and so on), so having the exact same content split into four videos instead of all in one video (for example) just inherently creates more work.
- But before we even get there, everything workflow-wise up until this point has basically assumed content would not be split out like this, which means the entire content production process now has to be reworked from the ground up.

And so figuring out the new process has been the main thing I've been working on recently.

### A general accounting of steps taken so far

#### I launched this site, ClockworkDesign.org, to document my process and workflow for these things (among others).

- Switched the DNS servers for the domain from Namecheap to Netlify
- Set up a [GitHub Organization](https://docs.github.com/en/organizations/collaborating-with-groups-in-organizations/about-organizations) for ClockworkDesign: [GitHub.com/clockwork-design](https://github.com/clockwork-design).
  - Will be used to organize freelancers on separate software projects once I scale more. More flexible than keeping all the projects under my personal GitHub account.
- Made a new repo under the organization for the ClockworkDesign.org website itself
- Took down my previous attempt to launch the design site, and closed the corresponding Netlify project.
- Copied initial website structure from said earlier attempt to launch the design site. Updated layout templates, list pages, and some initial content pages. Committed, pushed.
- Connected the new GitHub organization to my Netlify account.
- Deployed the new site live, and connected the custom domain. Set the primary DNS record to be the www subdomain rather than the bare domain. (This lets you better isolate cookies and whatnot on subdomains, in the long-term).
- Worked with Netlify Support to debug why the automatically-provisioned SSL cert wasn't working initially. Shout out to them, since they got the problem resolved in a timely manner.

#### Worked on figuring out and documenting how the new more-split-out content structure will operate in the short term, on `combined-pages`.

- For the time being, I decided to keep all content specified on what I am currently going to call `combined-pages`. Technically, there is no `hugo` layout template called `combined-page`, and to avoid scope creep, I am going to keep things that way for now. At the moment, `combined-pages` are basically `single-page` pages with a special structure.
- In the long term, the content structure will end up more split out in truth. But by adopting a consistent format now, this can be automated later via script.
- Even in the long term, I am planning to continue to draft content on `combined-pages`, and then use script automation to separate all the sections out onto their own pages only at the end.
  - This is to let section titles stabilize before turning them into pages of their own. If you have everything split out from the beginning, and also make the file paths match page titles (as is most intuitive), then every time you change the title, the file path changes. Basically, if you try to draft content with everything split out, then changing a sub-page title partway through is proportionally much more effort-intensive. It's not like you can't improve the UX some even so (e.g., by defining a macro that lets you rename a title, close out of the file, generate the slug for the file path based on the new title, actually rename the file path on disk, re-open the file, and finally restore the cursor position you had before triggering the macro) but even if you do all of that, it is still inherently less optimal than being able to just edit a header and have that be that.
  - I should note that for the same reason as all this, when I am creating a new top-level study initially (i.e., a new `combined-page` in the new process), I try not to actually make the study page until I have mapped out the scope of what will be discussed, so that when I specify a title, it is likely to "stick". Since changing titles changes URLs on deployed sites, and top-level study titles will be visible from the very first week of a study (i.e., before I have finished all sub-sections in the study), doing this is necessary to avoid changing my mind about the study title and therefore having to set up post-hoc [URL redirects](https://docs.netlify.com/manage/routing/redirects/overview/). (Not that I couldn't do that, but again, better to avoid if possible).
- Since having a consistent content format on `combined-pages` will be critical to allowing for this automatic script-based splitting later, I had to spend a lot of time brainstorming what the new content format should be. Several different moving parts are involved:
  - YAML frontmatter, to specify page metadata.
  - A shortcode called `properties` (that I have purposefully set up to be the conceptual equivalent to [Org properties drawers](https://orgmode.org/manual/Properties-and-Columns.html), since eventually I want to switch the markup format to Org instead of Markdown).
    - This `properties` shortcode carries a lot of responsibility, since it where all metadata associated with sections/headers ends up. Since on `combined-pages` sections are standing in for what will be separate pages once everything gets split out, and pages have their metadata specified in YAML frontmatter rather than a shortcode, what this means in practice is that the `properties` shortcode supports most of the same parameters as page frontmatter.
    - Aside from the overlapping properties with page frontmatter, the `properties` shortcode also supports parameters to specify section-specific embedded audio and YouTube video clips, and a `parent` property to specify proper header hierarchy (since everything gets flattened/collapsed a bit on `combined-pages`, since HTML only supports five real level of page headers, `h2` through `h6`. The `h1` level is conventionally used only for the page title itself).
  - A shortcode called `summary` (which will get turned into a section proper on split out `content-pages` eventually, but is just a shortcode here, since everything gets flattened/collapsed a bit on `combined-pages`).
  - A shortcode called `quizdown` for specifying review questions. 
- Specifying summaries and review questions, as well as subject tags and passage tags (in frontmatter/`properties` shortcodes) is not new. What is new is specifying them for basically every single section separately, rather than only once at the page level (since here, summaries and review questions are not in their own page sections, but directly specified next to section content, albeit wrapped in the shortcodes). By splitting everything out separately, we are essentially multiplying our content processing workload by a factor of N, where N is the number of sections on the page that will eventually be split out onto separate pages of their own.

#### Worked on figuring out and documenting how the new more-split-out content structure will operate in the long term, once all the separate pages get generated via script.

- I came up with a bunch of different separate page layouts. Some will be what I am calling `content-pages`, which will correspond to pages that have their own videos, as well as content and transcript sections. Others will be what I am calling `subpart-pages`, which are a collection of `content-pages` (well, at least for `discussion` content, rather than original content). Finally, there are `aggregation-pages` which are a collection of `subpart-pages`. There are also `single-pages`, which are basically like `content-pages`, but don't roll-up onto subpart and aggregation pages. Of course, above all these page layouts are `list-pages`.
- By convention, you can call both `subpart-pages` (at least the `discussion` variety of them that roll up other pages) and `aggregation-pages` by the label of `roll-up-pages`. In essence, they roll up page sections from sub-pages (e.g., summaries, review questions, videos, timestamps), rather than listing content like `list-pages`.
- Unlike before, with my previous implementation aggregation pages that rolled up *everything* (including content and transcripts), I have now decided to *not* roll up content and transcripts. So `roll-up-pages` will have summaries and review questions and videos and timestamps for all the nested pages, but not the actual content and transcripts. This is a sort of big conceptual change, and the main reason is to avoid duplicating content proper across pages on the site. This is better UX in general (that is, having content proper live in one and only one place), and also has functional implications with regards to search engine indexing and page ranking.
- Right now all of these planned page layouts do not exist in the website theme and my Python pre-processing application (that gets run before `hugo` to prep the static site for generation), so they are more or less just hypothetical at the moment.
- But it was important for me to map out where I want things to end up in the long term as part of defining how `combined-pages` work, to make sure that I am not missing any metadata or whatnot that I might need for the final split-out pages.

#### Brainstormed what general metadata is needed to support YouTube videos and podcast episodes with good UX.

- I realized that to keep from digging ourselves deeper and deeper into the hole with every new study we record, we should be specifying everything we will need in the long term even now, perhaps months to years before we will ever actually use it. (Hopefully not years...)
- This to avoid having to come back later and make a full pass through the backlog of content to specify these things at that later point in time. Better to do it all now, at the same time we record the content and everything is fresh in our minds.
- I decided there are two foundational bits of metadata to specify:
  - `content-short-title`: on YouTube and podcast platforms, your titles may have to be displayed in a small amount of space, and the latter part of your titles may get cut off, if your titles are at all long. So it is necessary to 1) keep the version of the titles that will be displayed on these platforms as short as possible, and 2) make sure that any non-unique parts of the title (like specifying content source, the fact that the content is group discussion content, etc.) are at the end not the beginning (since them getting cut off is far less bad UX-wise than cutting off the other parts of the title that actually uniquely specify the video/podcast episode topic).
  - `content-thumbnail-description`: specifying in words what the thumbnail should look like.

#### Brainstormed how YouTube end cards will work, and what ideal UX will be for them.

- I've long known that I want to support [YouTube end cards](https://support.google.com/youtube/answer/6388789?hl=en) as part of my automated video processing workflow. Linking to another video on a video end card keeps people watching your content, which is a well-documented way to improve your overall algorithmic ranking on YouTube. (And one that is not ethically questionable, I might add, and even brings benefit to your audience, who can now navigate to additional content more seamlessly).
- Despite knowing I wanted to support YouTube end cards, I'd never sat down and thought through what I'd need to have specified to be able to build them with ideal UX.
- I settled on three main new parameters that will be specified for every section that will become its own video (alongside the more general `content-short-title` and `content-thumbnail-description` parameters described above):
  - `content-comment-call-to-action`: a string used to specify what sorts of things users might be able to share their thoughts on in YouTube comments. Will be read by an AI text to speech tool as part of generating audio for end cards.
  - `content-end-card-next-video`: the URL linking to the next video in sequence.
  - `content-end-card-suggestion`: an optional parameter linking to another video discussing related content (or just suggested content more generally).

#### Worked on figuring out and documenting the structure for Meeting Google Sheets, that list out what specific content we went over what week.

- These will now be markedly different from the Meeting List Pages that I maintain (e.g., see the [BibleDocs Open Bible Study List Page](https://www.bibledocs.org/meta/bibledocs-weekly-bible-studies/bibledocs-open-bible-study/) and the [BibleDocs Ichthys Bible Study List Page](https://www.bibledocs.org/meta/bibledocs-weekly-bible-studies/bibledocs-ichthys-bible-study/)), since the Meeting Google Sheets will be at the *section* level rather than the *page* level.
- The extra level of specificity that comes dealing in sections not pages makes it *much* clearer what content we went over what week (i.e., rather than only knowing that we did some part of the wider study, we can now specify which specific thing it was).
- The other big change is that I am shifting Dropbox links to view video recording segments from public webpages onto these private Meeting Google Sheets (that can only be viewed by those with the link = those in the community group chats). This is to avoid misusing/abusing the Dropbox sharing links, which have bandwidth limits and whatnot.
  - Unfortunately, this means that until everything goes live on YouTube, the video recordings of our studies will no longer be visible to the general public (i.e., people who aren't directly in the community group chats), but I don't really see a great alternative until all the content goes live on YouTube. Share links from cloud storage providers like Dropbox/Google Drive/whatever just aren't designed for *publicly* hosting content (at least not when what you are sharing are video files in the hundreds of megabytes each).

#### Worked on figuring out and documenting the new Content Freelancer Google Sheet structure that will be necessary to process content in a split out form.

- So far, the way I have been organizing work for my Content Freelancer friend to help me do content processing (e.g., adding summaries, subject tags, passage tags, review questions, etc.) is via a Google Sheet, that I am going to generally refer to as the "Content Freelancer Google Sheet".
- It has checkboxes that call a [Google Apps Script](https://developers.google.com/apps-script/guides/sheets) function to open studies in [VSCode](https://code.visualstudio.com/), via protocol handler links (i.e., things that look like `vscode://file/{full-path-to-file}`)
- To avoid making my non-programmer Content Freelancer friend learn `git` and version control proper, at the time of writing, we collaborate on files via a shared Dropbox folder.
- Basically, all the process changes related to splitting content out more have made me completely rework the structure of this Google Sheet. Just as with the Meeting Google Sheets, every row used to represent a page, but now every row represents a section.
- Additionally, a new column has been added to track page layout (cf. above where I explained `content-pages`, `subpart-pages`, `aggregation-pages`, `single-pages`, and so on). This column will be used as the key in a VLOOKUP table to populate TODOs for each section, as well as a column tracking how much I will pay my freelancer friend for doing the pre-processing and post-processing for the section. (We decided to switch to this form of compensation rather than hourly, because it requires a lot less admin bookkeeping on the part of my friend).
- I also updated conditional formatting in the Content Freelancing Google Sheet to be much simpler and more intuitive, only based upon hardcoded cell contents (rather than being formula-based = dynamically tracking completion status via a completion date column).

#### Worked on figuring out and documenting the new division of responsibilities between myself and my Content Freelancer friend.

- As part of revamping the whole content production process to split everything out more, I decided to use this time of the boat already being rocked (so to speak) to also finally get around to offloading the remaining weekly content processing responsibilities I hadn't already.
- At a high level, I will now be responsible *only* for writing content, determining slide break positions in the content, and recording content (as well as using `git` to push webpages live once everything is ready), and my Content Freelancer friend will do basically everything else.
- Prior to this, I myself was still doing these tasks:
  - Organizing video recording segments after every meeting (that is, renaming them appropriately, and getting them organized into the correct recording directory).
  - Adding Dropbox share links to share these recordings with the Bible study groups.
  - Adding rows to the Meeting Google Sheets.
- Now that the Content Freelancer Google Sheet will also require more organization, I am also setting things up for that to also be handled entirely by my Content Freelancer friend, and not me.
  - That is, aside from me adding the initial file path to kick off a new `combined-page`, my Content Freelancer friend will be responsible for everything else, like specifying all the sections based upon the `combined-page` Markdown headers, generating TODOs for them, and then tracking content processing progress thereafter.
- I should note that in addition to generally handing off some of the things I was doing every week previously, the workload my Content Freelancer friend will be carrying every week will also be increasing a lot simply due to the greater amount of metadata that the new split out content structure requires. Basically, the fact that every section now requires its own summary, review questions, etc. means that my Content Freelancer friend simply now has a lot more to do on the content processing side, just inherently.

#### Worked on figuring out and documenting the new weekly process.

- Now that who is responsible for what has changed---and the process has gotten orders of magnitude more complex with the new split out content format---I decided to try and formalize the weekly process by starting to write it all down. 
- Prior to now, the weekly process was a bit more loose and informal. Now, however, we are going to make the weekly process have well-defined steps, each belonging to either me or my Content Freelancer friend. Based on this, it will now be very clear whose court the ball is in at any given point of time (so to speak), which should hopefully help reduce confusion and add structure to our weekly tag-team process that we go through to get content ready for release.
- I haven't finished this yet (it will be one of my main priorities for the next bit), but I got a good start.

#### Reworked our Dropbox file organization structure, to support everything in the new process.

- Previously my Content Freelancer friend was fine on a free Dropbox account, since the only thing I had shared with them was the text content (which didn't take up very much storage capacity).
- But now that I am having them also be responsible for organizing the video recording segments every week, they need access to the videos too. (Given our backlog of recordings, it is hundreds of gigabytes of video files).
- I researched how to make this happen, and decided to upgrade to the [Dropbox Family plan](https://www.dropbox.com/family), which is 2 TB of shared storage. This lets me just dump stuff into the shared `Family Room/` folder, and then my Content Freelancer friend will have access to everything, including the video recording segments to organize.
- I also set up the location my video recording segments get saved to by default to be inside this folder, so I don't even have to manually move them in for them to get in the right place for my Content Freelancer friend to subsequently organize them.
- As part of transitioning to the shared `Family Room/` folder, I had to work with my Content Freelancer friend to get rid of the prior shared text content folder, and then move it into the `Family Room/` folder.
  - Unfortunately, my friend's Dropbox install on Windows 10 randomly stopped supporting right-click properties in File Explorer, making it impossible to *de jure* set the smart sync preference for the new folder location. We spent a few hours trying to debug it, but eventually gave up because 1) it seems to be an active Dropbox bug lots of people are having (see [here](https://community.dropbox.com/en/discussion/860899/right-click-context-menu-has-disappeared-from-dropbox-folder-in-file-explorer)), and 2) my friend can still open the content files dynamically (i.e., Dropbox will automatically download them behind the scenes, even if they start out online-only initially), so it doesn't break our process, aside from just not being ideal.
- I also researched how to set up [selective sync](https://help.dropbox.com/sync/selective-sync-overview) so that my Content Freelancer friend would not need to actually sync down the video recording clips. My friend lives in a sort of rural part of the country, and has limited download speeds, so this would pose issues. Instead, they can do all the management of the video files through the Dropbox web UI. So we got all that set up.

#### Had a Zoom call with my Content Freelancer friend to explain all the process changes.

- Both the new split out content format, as well as the restructuring of weekly responsibilities, and the Dropbox stuff too.
- It was a long call (couple hours), since there was just a lot to go through.

#### Planned out how to back-propagate all of this to the previous ~65 studies we've already recorded.

- It is going to be a *massive* amount of work to get all of the previous studies organized into the new `combined-page` format, with all metadata specified.
- Complicating this even more is the fact that before I saw the benefit of having everything split out more, I was not even splitting video recording segments (i.e., was instead recording multiple sections together in the same video chunk). So part of organizing the past studies will also necessarily involve me going and manually listening to the past recording files to specify split points.
  - I can pay a freelancer to actually go in and do the video splitting, but determining where (i.e., at what transcript text/timestamp) to do the splitting is something I will still need to do myself.
- While a lot of this work will be tedious (and is the sort I'd normally pay to outsource to a freelancer), deciding on the header structure and nesting is something I can't really outsource. Upshot: I'm going to have to most of the post-hoc content reorganization here myself. To be honest, I'm dreading it, since it will be a ton of tedious work.
- Of course, then my Content Freelancer friend will also have to go back and add metadata for all the now-split-out sections, which will also be a ton of work.
- But this will all be necessary for having all this content end up in the split out format once it goes live, which will keep the YouTube videos to ~15-20 minutes most of the time (as opposed to 3+ hours, in some cases, were all sections to be combined into one video, like we were doing before).

### Did I really get all this completely documented in the last couple weeks?

Goodness no. I mostly just brainstormed, researched, and made decisions, and then tried to write down the decisions themselves, rather than all the reasoning for them and the full process specification.

In the next little bit I want to work on formally documenting all of this better. One of the main purposes of ClockworkDesign as a website will be to formally specify the processes and systems and methodology I deploy in my life in various areas, and this matter of our weekly content processing workflow is a great place to start.

Whether or not other people find all this useful (given that it will be public on the internet), I am actually mostly writing everything down for me, so that I can refer back to it over time, and have a centralized place to revisit my processes and the reasoning behind them.

Some of the initial write up I worked on (these are more than a bit rough at the moment, and far from complete, but it is a start):

{{% note %}}

In the future, some of these links might end up broken, since I am still in the process of figuring out how to split up all the documentation and such, meaning URLs are still moving around a fair bit.

{{% /note %}}

- [Content Freelancer instructions: Checklist for weekly content processing · ClockworkDesign](https://www.clockworkdesign.org/notes/content-freelancer-instructions-checklist-for-weekly-content-processing/)
- [Content freelancer instructions: Content file structure · ClockworkDesign](https://www.clockworkdesign.org/notes/content-freelancer-instructions-content-file-structure/)

{{% /content %}}

{{% section-navigation %}}
