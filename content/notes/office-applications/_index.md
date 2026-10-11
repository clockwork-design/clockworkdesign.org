---
layout: single-page
stags: 
title: "Office applications"
---

If you are looking for an open source Microsoft Office equivalent, what should you use, and why?

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

If you are looking for an open source Microsoft Office equivalent, what should you use, and why?

<!-- summary -->

{{% content %}}

## Content {#content}

### What I currently use

- [Collabora Office](https://www.collaboraonline.com/collabora-office/)

### Options

Offline:

- [Microsoft Office](https://www.microsoft.com/en-us/microsoft-365/microsoft-office)
- [Libre Office](https://www.libreoffice.org/)
- [Collabora Office](https://www.collaboraonline.com/collabora-office/)
- [Only Office](https://www.onlyoffice.com/)
- [Google Workspace](https://workspace.google.com/) (via [Google Docs Offline Chrome Extension](https://chromewebstore.google.com/detail/google-docs-offline/ghbmnnjooekpmoecnnnilnnbdlolhkhi?pli=1))

Online:

- [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/free-office-online-for-the-web)
- [Collabora Online](https://www.collaboraonline.com/collabora-online/)
- [Google Workspace](https://workspace.google.com/)
- [Proton Workspace](https://proton.me/business/drive/workspace)
- [rollApp](https://www.rollapp.com/) + LibreOffice

### Evaluation criteria

- Fully open source
- Works offline via desktop app
  - This desktop app must be available natively in [NixOS](https://nixos.org/) via [Nixpkgs](https://github.com/nixos/nixpkgs), or at least be installable on NixOS via [flatpak](https://flatpak.org/)
- Works online through browser (think Microsoft 365)
- Online and offline versions function basically identically. (Ironically, Microsoft 365 is actually not good in this regard. [See here](https://www.collaboraonline.com/blog/collabora-online-now-available-on-desktop/#:~:text=To%20see%20why%20this%20matters%2C%20let%E2%80%99s%20look%20at%20Microsoft%E2%80%99s%20suite))
- For the offline desktop version at the least, must be able to eventually make a full [Vertico](https://github.com/minad/vertico) command palette for it, once I start using customized [Emacs](https://www.gnu.org/software/emacs/) completion interfaces to build command palettes for all non-Emacs programs.
  - To be able to do this, you must at the least be able to change keybindings, and import/export your keybindings.
  - Even better if there is a `.json` or `.toml` (or whatever) config file, meant to be edited directly. But this isn't strictly necessary. So long as keybindings can be changed and also imported/exported, that alone is sufficient.
  - An example of an application that flunks this, somewhat shockingly, is Microsoft Excel on Windows. It does not natively allow you to change or customize its built-in keyboard shortcuts... at all. (Ironically Excel for Mac does).
- Has a proper CLI

Not important to me:

- Has a command palette out of the box. (Collabora Office does not, at time of writing).

### Further reasoning for decision

#### What do I need my office system to do?

Basically, I just need to be able to edit normal office files:

- `.docx`
- `.xlsx` and `.csv`
- `.pptx`

I want to shift absolutely as much of my life as I can into [Org Mode](https://orgmode.org/), but I have historical documents right now that aren't `.org` files. I mean, most of my files that aren't `.org` are Markdown, but the office suite is for the files that aren't plaintext at all. In practice for me, that is mostly `.xlsx` spreadsheets. Eventually I'd like to move many of those into Org tables, but it will quite an effort to get Org configured to the point where I am able to fully do that. I think most of what I want to do is possible with enough configuration tinkering, but it isn't an overnight sort of thing.

#### Collabora's sales pitch

Collabora has a number of excellent pages up that I found quite persuasive:

- [Collabora Office](https://www.collaboraonline.com/collabora-office/)
  - [Collabora Online now available on Desktop - Collabora Online and Collabora Office](https://www.collaboraonline.com/blog/collabora-online-now-available-on-desktop/)
- [Comparing Collabora with OnlyOffice - Collabora Online and Collabora Office](https://www.collaboraonline.com/comparing-collabora-with-onlyoffice/)
- [European and More: 6 Reasons to Choose Collabora Online as Your Document Editor - Collabora Online and Collabora Office](https://www.collaboraonline.com/blog/european-and-more-6-reasons-to-choose-collabora-online-as-your-document-editor/)

{{% /content %}}

{{% section-navigation %}}
