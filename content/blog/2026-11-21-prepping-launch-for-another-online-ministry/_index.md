---
date: 2026-11-21T09:10:00
layout: content-page
stags: 
title: "2026-11-21: Prepping launch for another online ministry"
---

A friend of mine is thinking about getting a formal online presence established for his Bible teaching ministry. Since I'll be helping with this, I thought it made sense to try and document all the to-dos, for both of us.

<!--more-->

{{% section-navigation %}}

## Summary {#summary}

<!-- summary -->

A friend of mine is thinking about getting a formal online presence established for his Bible teaching ministry. Since I'll be helping with this, I thought it made sense to try and document all the to-dos, for both of us.

<!-- summary -->

{{% content %}}

## Content {#content}

### Solo step you take: Picking a name for the ministry

In my opinion, online Bible teaching ministries should use domain names that end in `.org`, to make it clear that they operate in a not-for-profit fashion.

Domain name availability can be checked on Namecheap, which is the domain name register I use and recommend:

- [Buy a domain name - Register cheap domain names from $0.99 - Namecheap](https://www.namecheap.com/)

What you'll need to look at is if the `.org` top level domain is available, for whatever website name you try. For example, my ministry website is `bibledocs.org`. You need to come up with the bit that comes before the `.org`.

After finding an available web domain, before registering it (which usually renews at about $15 a year, or thereabouts), you should check if your chosen ministry name also has a matching YouTube handle available. You can use this site to do that:

- [Name Checker - Social Media Username Checker](https://dnschecker.org/social-media-name-checker.php)

For example, my ministry YouTube handle (which matches my ministry website name) is `@BibleDocs`.

After verifying that a YouTube handle is also available for your name, then you should go ahead and register the domain name with Namecheap. I recommend setting it up to auto-renew, if possible, so that there is no possibility of it expiring on you, and you losing access to it.

### Solo step you take: Getting stuff ready for our setup Zoom meeting

It will be simplest for me to just remotely take control of your computer as we go through parts of the setup. Otherwise I'd just be constantly telling you to do this and that.

To support me remotely taking control of your computer, I recommend we use something called Chrome Remote Desktop. For you as the person granting control of your computer to me, you have to have three things installed:

1. The Google Chrome web browser
2. [The Chrome Remote Desktop remote access application](https://remotedesktop.google.com/access) (needs to be downloaded and installed on your computer)
3. [The Chrome Remote Desktop browser extension](https://chromewebstore.google.com/detail/chrome-remote-desktop/inomeogfingihgjfjlpeplalcfajhgai?hl=en) (needs to be added as a Chrome extension)

So before we meet on Zoom to get your ministry set up, you should have these things set up and ready to go.

If you don't already have [Git](https://git-scm.com/) installed, you'll need it. I think you already do, but if not, download and install it.

As a frontend for Git, I also recommend you download and install [SourceTree](https://www.sourcetreeapp.com/), a visual Git client. I use this at work and for my own personal projects, so am used to it, and can provide support, assuming you are willing to use it too. You will use this tool to push updates you make live on your website. So this is another thing it makes sense for you to have downloaded and installed before we meet.

You should also have your login credentials ready for these websites:

- [GitHub](https://github.com/)
- [Netlify](https://www.netlify.com/)

Your source Markdown files will live on GitHub, and your site will be hosted and deployed on Netlify. All of this is completely free (so the domain name renewal will be your only recurring cost).

You should also make an account on this website:

- [Buttondown — Newsletter software for people like you](https://buttondown.com/)

We will use it for setting up an emailing mailing list for your ministry.

You should also make an account on this website:

- [Free Email Forwarding for Custom Domains - Open Source Email Service](https://forwardemail.net/en)

We will use it to support you using an email address in the format of `me@myministry.org`.

### Solo step you take: Record at least one reaction video

You don't have to upload it to YouTube yet; we just need something recorded and ready to upload, so that there is something of this content type when we set your website up.

This step is the last one you'll do on your own. Past this point, we'll work together.

### Step we take together: Discussing the YouTube interface

I know you've uploaded videos to YouTube before, but just to make sure everything is fresh for you, I'll briefly go over my thoughts on how to upload YouTube videos and properly manage video metadata.

If you haven't already created your ministry YouTube channel, we'll do that together. Then we'll upload the reaction video you recorded, and talk through what format your video descriptions ought to have, for reaction content.

### Step we take together: Setting up a Git repository for the ministry website

On GitHub, we will create a new Git repository named the same thing as your domain name. So, for example, the repo name for my ministry is `bibledocs.org`.

After this we'll get GitHub set up with an SSH key, so that you can seamlessly authenticate in SourceTree without having to enter login credentials.

After creating the new repo on your GitHub account, we will give me write access to it, and then I'll take over setup on my side (my computer).

First, I'll copy the entire Git repo I have for BibleDocs into the new repo you made.

Then, you and I will talk about what content types you want to have set up. I'll update the `layouts/` folder to only have those content types, and also remove all stuff from the `content/` folder except for `_index.md` pages we adapt for your starting content types. We will also add content pages for everything you already have written that is ready to post, and also make a content page for the first reaction video you recorded (which won't have anything formally written, but will have the auto-generated transcript text, like we discussed).

- Do you want to be able to arbitrarily order content within each of your content types, or should it just be alphabetical? If you have multi-part series, you probably need to support weight-based ordering. Otherwise, I recommend alphabetical.
- We will also go over how to embed YouTube videos using the `video` shortcode. You'll use this on your reaction video webpages.

Next, we'll talk about what meta pages you want (e.g., "About the author" and "About the site" pages). Starting out, we can leave stubs for these, and you can fill them in on your own time.

After this, I'll update the `config.toml` file in various ways, to make it work for your site instead of mine. For example, we'll change the base name and base URL of the site, and set up all the metadata configuration for the sidebar menu structure.

At this point, we'll be ready to test your site. I'll demo running the local [`hugo`](https://gohugo.io/) webserver on my computer, then I'll work with you to get the right `hugo` binary version installed and on your PATH on your computer. Then you'll be able to run it by launching a PowerShell command prompt inside your website's folder, and then running the command `hugo server`. At that point, you'll be able to see a local copy of your website on `http://localhost:1313/`. This lets you test your changes before pushing to Netlify, which helps catch build errors.

### Step we take together: Setting up the Python tool that automatically downloads YouTube transcripts for your reaction video webpages

We will work together to:

1. Make sure you have Python installed
2. Git clone the Python project I built for you for this purpose
3. Create a PowerShell alias for the Python script, so you can execute it no matter what directory you open PowerShell in

After this, you will just launch a powershell command prompt in the directory of whatever page you want to add a transcript to (which you can do by right clicking in File Explorer > "Open in Terminal"), and then run `add-transcript _index.md` (or the like). Once your website is live, the transcript this Python script adds to your webpage will have timestamp links that will change the time in the embedded YouTube video on that webpage.

### Step we take together: Setting up a Buttondown mailing list

We will login to your Buttondown account, and do whatever we need to do to grab the proper embed code for your mailing list page on your website.

I will then go over how you can draft emails in Markdown on the Buttondown website, to send email mailing list ministry updates.

### Step we take together: Connecting the GitHub repo to Netlify, and getting the site deployed

After logging into your Netlify account, we will first transfer the domain name your registered to Netlify's DNS servers, and set it up so that the `www` subdomain is marked as the primary domain. Having Netlify handle the DNS is necessary to make everything go smoothly in website hosting.

After this we will make sure you have given Netlify access to all your GitHub repos, including the new one for your ministry website.

Then we will set up the new site on Netlify. It should automatically provision an SSL certificate (for HTTPS).

After connecting it all, all we have to do is wait and see if it all works the first time. It can take the DNS records some time to propagate, so unfortunately we might have to reconnect at a later time to see if it all worked properly.

### Step we take together: Getting "send email as" set up in Gmail

First, you'll want to decide what you want your ministry email address to be.

After that, we'll set things up with [Forward Email](https://forwardemail.net/en) to let you manage your ministry email seamlessly through Gmail.

This will involve adding MX records on the Netlify DNS interface, among other things.

{{% /content %}}

{{% section-navigation %}}
