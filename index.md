---
layout: markdown
---

<div class="flash">
  <p>Welcome! Here you will find all the information you could ever want about MCEMS on the interwebs.</p>
</div>

Introduction
============

Over the past two years that MCEMS has been using the BergEMS website, it has become an integral part of the organization, handling applications, shift scheduling, some membership records and rosters, as well as being the public-facing web presence of the organization.

As the organization continues to rely even more heavily on technology, notably with the recent Active911 effort, the limitations of BergEMS have started to become apparent. When it was created, its main purpose was to handle scheduling, and was not architected in a way that would readily facilitate future expansion. Furthermore, the visual appearance of the site, while adequate, has significant room for improvement. Another drawback of the current system is that it lacks any unit test coverage, the need for which is becoming more pronounced as the application grows in size and complexity.

Recently, Heroku changed its pricing structure which gave rise to the need to reconsider the architecture of the system due to the financial infeasibility of running multiple apps on Heroku. While previously, it was possible to have an app running 24/7 on Heroku's free tier, free apps are now limited to running for 18 hours per 24 hour period. This is not acceptable for at least one forthcoming use of the platform, namely, the ability for MCDCS dispatchers to send Active911 alerts. Thus, a consolidated approach is desirable.

Currently, the organization uses BergEMS for the following purposes:

* Public website
* Member roster management
* Shift scheduling
* Certification tracking
* Application/Interview management

With the adoption of Active911, MCEMS requires additional software to be used by MCDCS dispatchers for generating alerts. At this juncture, the organization is primed to restructure its web services and digital presence due to its growth over the past several years. Furthermore, the organization now has the resources to devote to the architecture and implementation of such a new system due to the interest and availability of four software developers to work on the project: Ben Burwell, Jalal Khan, and Victor Lora, and Ron Gerschel.

Migration Plan
==============

Phase 1 - Basic API and Dispatch Console
----------------------------------------

The highest priority for the organization is to get the dispatch console up and running. To accomplish this, we will need to create some basic components of the API. Namely:

* People and Users
* Session management
* Oauth

This will allow the Campus Safety dispatchers to log into the system and send alerts. Furthermore, we need to build the actual app that they log in to. This will be a JS app that runs in the browser. It will be a static site served from GitHub Pages.

Phase 2 - New Public Site
-------------------------

The next step of the migration will be to create the new public site. When this is complete and ready, the current BergEMS system will be moved to https://portal.bergems.org/ and replaced by the new site.

Phase 3 - API and Portal Update
-------------------------------

The next phase will include further buildout of the API and creation of the portal site. The initial implementation of the portal will be focused on supporting the following current uses of the BergEMS system:

* Scheduling
* Membership Roster Management
* Applications/Interview scheduling
* Certification tracking

Buildout of the API will need to support the functionality of the portal.

Phase 4 - Future
----------------

The infrastructure created will enable future buildout of additional components as necessary. For instance, an inventory tracking system to manage equipment that is assigned to members could easily be constructed.

