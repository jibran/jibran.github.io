---
layout: post
title:  "Working on a GovCMS 7 Site"
subtitle: My first impression of GovCMS 7 while working on a support ticket.
banner: https://wallpapercave.com/wp/wp7388712.jpg
categories: [GovCMS]
tags: [drupal_planet, GovCMS 7, Drupal 7]
---

I have not yet worked on any GovCMS site 7 or 8. I haven't worked on Drupal 7 site in a while as well. Last week, at
work, I was working on a support ticket for site which was built using GovCMS 7.

## Setup
### Account Setup
I had to set up a couple of accounts first which is always fun. It is nice to see
[GovCMS Projects][projects-site]{:target="_blank"} site is set up using GitLab distribution, so setting up profile and keys was
straight-forward.

There was [GovCMS Support][govcms-support]{:target="_blank"}, single page profile setup, so it was very easy. Then there
was [GovCMS Dashboard][govcms-dashboard]{:target="_blank"}, I was already logged in so no profile set up. Yay!!!

### Local Setup
Project README had clear instructions about setting up local environment. Pull down docker container was fine, but I
didn't like installing the pygmy gem. Docker4Drupal doesn't use gem for similar kind of local setup.
Thankfully, I have rvm, ruby and gem already setup locally so installing the gem was not a hassle. I ran
`docker-compose up` or `ahoy up` in this case and forgot about running `pygmy up` because I usually just `docker-compose up` to
fire up local stack.

## Codebase

As far as I remember, we hit a sweet spot with Drupal 7 deployments, update hooks and feature exports but none of that
was available on GovCMS7 because you are not allowed to write custom code. I cloned the repo locally and because every
site has a standard setup there are only handful of folders in the repo which was based on
[GovCMS 7 scaffold][govcms7-scaffold]{:target="_blank"}. When I opened the repo in PHPStorm it didn't even recognise
the project as Drupal 7 project.

## Fixes and Deploy

As per [GovCMS building a new website][govcms-building]{:target="_blank"}, there are two ways to deploy your DB changes
to the site:

* On platform development
* Off platform development

As this was a live site so "On platform development" mean either changes on production instance or local instance, so I
looked into "Off platform development" for which you need a Forklift.

> ### Forklift
>
> A forklift is the process of transferring your website into the production environment, if it is developed off the
> GovCMS platform

I think I'll be going with "On platform development".

[projects-site]: https://projects.govcms.gov.au
[govcms-support]: https://www.govcms.support
[govcms-dashboard]: hhttps://dashboard.govcms.gov.au
[govcms7-scaffold]: https://github.com/govCMS/govcms7-scaffold
[govcms-building]: https://www.govcms.gov.au/support/building-new-website
