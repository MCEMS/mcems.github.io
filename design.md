---
layout: markdown
---

Proposed System Design
======================

The design of the system includes a centralized RESTful JSON API and <var>n</var> API clients. In general, these will be static HTML sites served from GitHub pages, but the flexible architecture allows for many other types of clients. Using an Oauth2 workflow for API authentication will allow for flexible access and should serve future needs.

The proposed design consists of the following components:

* **RESTful JSON API running on Heroku**
  * Hobby plan in order to ensure 24/7 availability
  * The API will be written in CoffeeScript using the Hapi framework
  * It will provide Oauth2 authentication/authorization to enable remote access via both internal and potentially externally built apps.
  * It will hold all MCEMS data and make it available to external components as required.
  * It will use Heroku Postgres to store data. The service is free for 10k rows. We will likely require additional capacity; it costs $9/month for 10M rows.
  * It _may_ use Heroku Redis for caching transient data such as session storage. This would be free at our scale.
* **Public-facing site**
  * This will replace the current, not-so-pretty public site component of BergEMS.
  * Static site served with GitHub Pages
  * Benefits:
    * Better performance (pages not being rendered from DB on-the-fly)
    * Responsive, mobile-ready design
    * Improved visual layout and user experience
  * Drawbacks: more technical know-how required to update
* **Membership Portal**
  * Client-side JS app served through GitHub Pages
  * Encompass much of the current BergEMS functionality
  * Snappier user experience
  * More structured and easier to extend and update
* **Dispatch Console**
  * A simple static application to push alerts to Active911 through the API
  * Room for future expansion as the Active911 API matures

Additional Considerations
=========================

* Dyn is currently, and will continue to be, used for DNS registration.
* CloudFlare's free plan will be used for DNS service, with the following names:
  * https://www.bergems.org/ -- the new public site
  * https://api.bergems.org/ -- the API running on Heroku
  * https://portal.bergems.org/ -- the new member portal
  * https://dispatch.bergems.org/ -- the dispatch console
* Weekly or daily automated database dumps will be configured
* A GitHub organization will be created to hold the repositories for the system components. This is a change from the current situation, in which the one repository is under Ben Burwell's personal GitHub account.
