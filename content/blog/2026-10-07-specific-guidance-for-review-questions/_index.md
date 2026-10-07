---
date: 2026-10-07T09:10:00
layout: content-page
stags: 
title: "2026-10-07: Specific guidance for review questions"
---

This week I added a documentation page explaining how my Content Freelancer friend should add review questions, among other things.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

This week I added a documentation page explaining how my Content Freelancer friend should add review questions, among other things.

<!-- summary -->

{{% content %}}

## Content {#content}

### A Content Freelancer documentation page explaining guidelines for adding review questions

I added [a documentation page going over review questions specifically](/notes/content-freelancer-instructions-review-questions). The two big points are that:

1. Review questions should stay focused only on important takeaways/high level points, rather than testing trivial details like names/dates/places. For history-related content, focusing on *why X happened* as well as *the effects X had, and its significance/importance/impact* can help keep review questions focused on tracing cause and effect, which is most useful for overall understanding and comprehension.
2. Except in specific circumstances, all review questions should be either all of the following are true except multiple choice questions or basic multiple select questions (with at most one false option).

### Adding new content type called `content-processing-feedback` to give feedback to Content Freelancers, so that we can gain experience, and have a log of corrections to refer back to over time

The pages won't be linked through the website UI. Not because there is anything wrong with them being public, but just because most people won't care. Interested parties can see the list of them here:

- [Content processing feedback · ClockworkDesign](https://www.clockworkdesign.org/content-processing-feedback/)

I've decided to have one page per year (at least for now), to chunk the feedback.

The page for 2026:

- [2026 content processing feedback · ClockworkDesign](https://www.clockworkdesign.org/content-processing-feedback/2026-content-processing-feedback/)

### Another Zoom meeting with my Content Freelancer friend, to explain the new content processing information

We covered both the new guidelines for review questions, and the content processing feedback page.

### Building out columns in the Content Freelancer Google Sheet

I think I finalized what columns are needed to track content processing progress for each `combined-page` section. Between tracking to-dos for my Content Freelancer friend and also tracking my own checks of their work, it's a lot of steps for each piece of content!

Settling on this column list was an important first step. I'll now be working on getting everything set up for us to start tracking all the content processing progress, using these columns with keywords like `To-do`, `Done`, `N/A`, and so on.

### Using AutoHotkey to add a keyboard action that marks an Org task header as DONE, and at the same time adds a CLOSED timestamp

Emacs Org Mode has a binding for this: `C-c C-t d`. This marks the task header as DONE, and with the right Org Mode setting, also adds a `CLOSED` timestamp under the header. All with one action.

Right now I am organizing all my tasks in an Org file, but using the [VS Code Org Mode](https://github.com/vscode-org-mode/vscode-org-mode) Org extension in VSCode (rather than Emacs Org Mode proper). I'll be in VSCode until I can write a script to make `C-c`, `C-x`, `C-v`, `C-z`, `C-y`, `C-a`, and so on behave as normally in Emacs, to preserve muscle memory. (While accessing the default Emacs actions on these bindings a different way, via a leader key). It's on my to-do list, since I'd like to start using Emacs as my daily driver, alongside the Vertico/Marginalia/Orderless/Consult/Embark completion stack.

At any rate, I really badly needed this action, since it is a core part of how I manage my daily task list in a time-efficient manner. When I finish a task, I just press a key combo to trigger the action, and boom, all metadata is updated properly. I can also go back at the end of the day and close anything I didn't close immediately after finishing, and the date will still be right on the timestamps, for later sorting and filtering purposes.

Managing tasks this way keeps everything in plaintext files, and that has all sorts of benefits, such as easily being able to filter Org headlines on TODO state and CLOSED date. And of course plaintext files are great for all sorts of other reasons too (such as being best for full-text searching).

At any rate, since the [VS Code Org Mode](https://github.com/vscode-org-mode/vscode-org-mode) Org extension in VSCode did not have an action defined for this operation, I had to write my own in AutoHotkey. I currently have it bound to `M-S-a`, because that is really ergonomic to hit with my left hand when my right hand is on the mouse, and does not interfere with any important binding I care about in VSCode Org files. YMMV.

I had to add some special stuff to make it work in virtual machines too. During my day job, I sometimes log into an Azure Virtual Desktop (AVD) through the [Windows App](https://apps.microsoft.com/detail/9n1f85v9t8bn?hl=en-US&gl=US). (When on the VM, I still manage my work tasks this same way in VSCode). To make AutoHotkey send the right actions even into the virtual desktop, you have to ensure AutoHotkey's keyboard hook trumps the virtual desktop's keyboard hook (whenever you focus the virtual desktop).

Here's the code to make all this work (note that by default, the [VS Code Org Mode](https://github.com/vscode-org-mode/vscode-org-mode) Org extension in VSCode makes `M-<left>` cycle backward through TODO states):

```autohotkey
#Requires AutoHotkey v2.0
#SingleInstance Force  ; Ensures only one instance of the script runs at a time.
SendMode "Input"  ; Forces all 'Send' commands to use 'SendInput' globally.
#UseHook ; So that it works on virtual desktop

; Add the Windows App / Remote Desktop window classes
GroupAdd "RemoteDesktops", "ahk_class TscShellContainerClass" ; Standard MSTSC
GroupAdd "RemoteDesktops", "ahk_class Windows.UI.Core.CoreWindow" ; Windows App Universal

#HotIf WinActive("ahk_group RemoteDesktops")
; An artificial vkFF keystroke triggers when the remote desktop window is focused,
; at which point it steals the hook. This reinstalls AHK's hook immediately.
~VKFF::
~^VKFF::
~!VKFF::
~^!VKFF:: {
    if (A_TimeIdlePhysical > A_TimeSinceThisHotkey) {
        Suspend True
        Suspend False ; Reinstalls AHK hook
        Sleep 50
    }
    return
}
#HotIf

+!a:: ; Shift + Alt + A
{
    SendInput "!{Left}"  ; Send Alt + LeftArrow
    Sleep 50             ; Wait 50 milliseconds for the application to process the shortcut
    SendInput "{End}"    ; Send End
    Sleep 50             ; Wait 50 milliseconds for the application to process the shortcut
    SendInput "{Enter}"  ; Send Enter
    Sleep 50             ; Wait 50 milliseconds for the application to process the shortcut
    
    ; Format the current date and time
    CurrentTime := FormatTime(, "CLOSED: '['yyyy-MM-dd ddd HH:mm']'")
    
    SendInput CurrentTime
}
```

To make this AutoHotkey script automatically run at system start, I made a shortcut to it, and then dragged the shortcut into the `Startup` folder, which lives at `%AppData%\Microsoft\Windows\Start Menu\Programs\Startup`.

{{% /content %}}

{{% section-navigation %}}
