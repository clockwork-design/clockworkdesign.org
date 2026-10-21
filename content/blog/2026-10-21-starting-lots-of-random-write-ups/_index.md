---
date: 2026-10-21T09:00:00
layout: content-page
stags: 
title: "2026-10-21: Starting lots of random write ups"
---

Recently, I got a lot of thoughts down on paper, but not so many things formally published. I'll work on that.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

Recently, I got a lot of thoughts down on paper, but not so many things formally published. I'll work on that.

<!-- summary -->

{{% content %}}

## Content {#content}

There have been all sorts of things I've been working on recently, and I had a hard time picking just one thing to title this update. So I decided to just name it something generic, and talk about all the things.

### Notes pages I did finish (at least in some form) recently

I wrote up these three things:

- [Office applications](https://www.clockworkdesign.org/notes/office-applications/)
- [Portable air fryers](https://www.clockworkdesign.org/notes/portable-air-fryers/)
- [Diet and nutrition](https://www.clockworkdesign.org/notes/diet-and-nutrition/)

The diet and nutrition page took quite a long time, since there is a lot there. I currently have a bunch of links saved in a to-do block for when I get around to documenting the bulking side of the diet. But since I'm cutting at the moment, this is sufficient for today.

### Procrastinating on documenting final process changes

The main list of things I still need to do to completely finalize the new process (in no particular order):

- Document how the Meeting Spreadsheets still need a row even for weeks we didn't meet. Every single week needs a row.
- Switch things up so that replacing Bible passage references with scripture shortcodes happens as part of pre-processing, not post-processing
  - This requires me to have all content completely written a week in advance, but makes a lot more sense overall.
- Refactor the weekly procedure write up to only list Content Freelancer to-dos (rather including my own to-dos as well). This should hopefully make it less confusing overall.
- Change it so that the Meeting Spreadsheets link to folders for the recording segments (rather than individual segments), except for `source-clip-video-pages` that require a link to the section with the embedded video, so are still still split out segment by segment.
  - Go back and remove Dropbox share links for all the relevant individual segments, and clear the relevant links in the Meeting Spreadsheets. These will all need to be redone.
  - For videos that are only one segment, link directly to the segment, not the folder.
- For the core Markdown content files, switch to using Git instead of Dropbox, to sync changes between myself and my Content Freelancer friend.
  - There will be four main Git branches used for this purpose: `ibs-pre-processing`, `ibs-post-processing`, `obs-pre-processing`, and `obs-post-processing`.
- Finalize columns in the Content Freelancer Spreadsheet, corresponding to weekly to-dos for the Content Freelancer, and also weekly to-dos for me.
- Create a tab in the Content Freelancer Spreadsheet to define which weekly to-dos apply for which page layouts. (I'll need to define these page layouts on a notes page somewhere). This will then be used to quickly set up to-dos for all the sections, as we go.
- Add rows in the Content Freelancer Spreadsheet for all recent study sections, since we switched to the new process. Use the VLOOKUP tab to set initial values for all the sections, and then go back through and update state for all of these rows until they are accurate to where we are present.
- Document all of this in relevant notes pages on ClockworkDesign. Be thorough, so everything is clear.

I've had a hard time getting myself to buckle down and do all this, because it is just isn't the most fun stuff to think through and document.

But over the next bit, I want this to be my top priority, so that we can get the final format in place and then keep up with new content week by week.

### Getting the content backlog processed, without stopping the weekly meetings

As just discussed, we are close to stabilizing the final content structure (at least the "for now" final content structure). Priority #1 clearly needs to be getting it finalized and then keeping up with it week by week. But even once we are doing that, what about the dozens of past studies that will not yet be in this final format? How can we play catch up without stopping the weekly meetings?

I spent a good bit of time thinking through this, and started a draft write up. I'll post it soon---hopefully by the time of the next update.

### The plan for hiring freelancers to take over parts of my workload: Hiring a Project Manager Freelancer to oversee all the others

Another thing I spent a good chunk of time thinking about. I don't know why it never occurred to me before that I could hire a freelancer to 1) go hire other freelancers, as needed, 2) organize all the specifics of the work other freelancers do, 3) answer questions other freelancers have (passing them onto me if and only if they cannot be answered without me)... and so on. Basically, someone to act as a project manager proper.

In short, just how the functional stakeholders/requirement generators for software projects usually are *not* the same people as the project managers who actually handle the nitty gritty implementation details, why not do the same thing with the freelancers I hire? (And not just for the software projects I will be running, but for *everything* I am farming out to freelancers)?

Basically, I'd be paying someone to be my lieutenant/second-in-command. I'd explain my vision and goals to them, and then they'd do whatever is necessary to actually make it happen. Including breaking requirements down into bite-size tasks, sequencing and prioritizing them, testing the output of other freelancers against acceptance criteria, etc. etc.

Clearly, I'll need to trust this person *a lot*, since they will be given leave to operate with a lot of independent decision-making authority. But *if* I can find someone who is a good match for this role, then I would truly be able to offload massive amounts of work to this person, and it would free up the maximum amount of my own time, energy, and focus.

I am a bit worried that finding a good fit here will be extremely difficult, since I find it unlikely that I can just find someone who will have a lot of experience with all the various things I will want them to be coordinating work for. For example, my projects are going to end up spanning across Python, Emacs Lisp, NixOS and Linux dotfiles configuration, video editing and other forms of content processing, outsourced social media management, and so forth. While I could technically find different project managers for each independent area... that would sort of defeat the point of *me* not having to be constantly interviewing potential freelancers and screening them, setting up their milestones;/specific tasks, etc.

So rather than finding someone who already has experience in all these specific things, I think it will be necessary to instead try to find someone who 1) is capable of picking up and truly understanding new areas without much hand-holding, and 2) someone who will not just make assumptions if what is desired is ambiguous, but always ask for proper clarification. Basically, the person will need to be very self-driven, and an excellent communicator.

I jotted down a lot of other details too, but sort of didn't get everything into a pretty form yet. I'll work on getting this cleaned up and published too.

### Researching the idea of creating a 501(c)(3) nonprofit for supporting online Bible teaching

In the back of my head for a while now, I've been considering the idea of launching a nonprofit proper for supporting in-depth online Bible teaching efforts. I have spent *a lot* of time recently trying to set up efficient content generation processes, and am in the process of trying to set up a system whereby I can outsource all sorts of regular tasks to freelancers in order to free up even more of my time for writing ministry content proper. The thought was basically if I get the whole pipeline set up cradle to grave, then could I maybe make a nonprofit that focuses on supercharging the ministry output of other online Bible teachers? If I already had a battle-tested weekly procedure and network of freelancers and so on established, it would hypothetically be pretty easy to have other Bible teaching ministries piggyback on this proven system. Maybe?

I did a bunch of research about how nonprofits work (e.g., in the state of Georgia you need at least two people = a President and Secretary, but to file for *federal* 501(c)(3) status, you probably need three = President, Secretary, and Treasurer), and considered ideas about how one could maybe be set up.

Nothing final here either. Eventually I will post the more detailed notes I have.

### Researching handheld wireless mice

If I am watching a video or whatever while walking on my treadmill inside, it would be useful to be able to control the mouse pointer in order to adjust playback speed, toggle fullscreen, etc.

But in this situation, whatever device lets me control the mouse should not require a desk surface, but should be handheld.

As I started to research the options out there for handheld wireless mice, it sort of shifted into trying to find a control device that would not only serve as a wireless mouse, but also a wireless presentation remote (think next slide and previous slide), a wireless media remote (think play/pause, volume up/volume down, mute, etc.), and so on---both across desktop computer usage, and also Android. I already have devices for some of these other purposes (which is why I started by researching wireless mice), but I am *very* pro-minimalism, so like the idea of having one device that does everything. So once I find a multi-purpose option I think will work across use cases, I will probably buy this combined control device, then get rid of all the rest.

I got a lot down on paper about all this but... as in all the other cases this week, it is not final yet.

### Researching/planning my home office layout

My home office currently has a Twin XL bed, a projector/125" projector screen, a treadmill, an indoor fitness cycle, and a couple couches.

I want to make the room properly support two basic configurations:

1. **Exercise mode**: The treadmill and indoor fitness cycle are located towards the middle of the projector screen, far enough back tha the FOV is not overwhelming. There should be a standing desk holding a keyboard. Either it needs to span across both (and therefore be very wide), or be narrower but easily moved to align with one or the other. (There will not be a case where both the treadmill and indoor fitness cycle need to be used at the same time, which is why this would work).
2. **Couch mode**: The treadmill, indoor fitness cycle, and standing desk have been removed from the room (or at least their position has been adjusted), so that the couches are located on the back wall (opposite the screen), with nothing obstructing visibility.

Right now, I don't have a good solution for the standing desk, and the couches are not easy to move, due to a lack of wheels. (I need to look into getting couch risers that have wheels, maybe?). Also, the projector is currently placed on a plywood assembly built just over the top of the treadmill. It works fine, but prevents the treadmill from being easily moved. Instead of this, I probably should get a standalone projector stand, or even consider transitioning to an ultra short throw (UST) projector in this room too?

I also probably want to get a soundbar for this room, since it is serving as a backup mini-theater of sorts.

At any rate, I spent time considering all this, and got a good bit written down, but still want to finalize things more.

### Brainstorming pages to write up to document my daily schedule and task management workflow

I settled on this list for now, to document my daily schedule:

- Daily schedule: Normal workday schedule
- Daily schedule: Monday schedule
- Daily schedule: Tuesday schedule
- Daily schedule: Wednesday schedule
- Daily schedule: Thursday schedule
- Daily schedule: Friday schedule
- Daily schedule: Saturday schedule
- Daily schedule: Sunday schedule

And also this list to document my task management workflow:

- Task management: Monday tasks
- Task management: Tuesday tasks
- Task management: Wednesday tasks
- Task management: Thursday tasks
- Task management: Friday tasks
- Task management: Saturday tasks
- Task management: Sunday tasks
- Task management: Only ever work tasks that are formally tracked and prioritized
  - Aside from things on daily schedules, everything is tracked as formal tasks
- Task management: Tasks are tracked in plaintext Org files
- Task management: Prioritizing tasks
- Task management: Daily task management cleanup
- Task management: Weekly task management cleanup
- Task management: Formalized motivation
- Task management: Ultra-strict focus
- Task management: "Earning" off time

I started drafting a couple of these, but didn't get very far. I'll work on them soon enough. These are good places for me to start to document my processes, in the primary spirit of what I intend for ClockworkDesign to be.

{{% /content %}}

{{% section-navigation %}}
