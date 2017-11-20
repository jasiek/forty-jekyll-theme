---
layout: post
title: ‘Open’ Banking Week 1
description: What has been promised, and what is actually out there?
---

tl;dr: The open banking world is now a week old - despite a huge amount of discussion across digital and print media, very little has focused on the actuality (as opposed to the potential), so here is a brief review of what is available.

## Open Banking Implementation Entity (OBIE)

The Open Banking Implementation Entity have a relatively extensive [website](https://www.openbanking.org.uk) and [Confluence Space](https://openbanking.atlassian.net/wiki/spaces/DZ/overview?mode=global) which detail a great deal about the ecosystem. They have also developed a set of [reference applications](https://github.com/OpenBankingUK/reference-applications/blob/master/tpp-reference-applications.md) including a ‘reference mock server’, which acts as the resource server of an ASPSP implementation, but does very little besides.

If you are minded to, you can [enroll with Open Banking](https://www.openbanking.org.uk/wpcore/wp-content/uploads/2017/12/Open-Banking-How-To-Guide-Enrolling-Onto-Open-Banking-v4.2.pdf), and this will give you a view of their internal reference banks, more akin to full ASPSP implementations, with partial implementation of their custom [OIDC Security Profile](https://bitbucket.org/openid/obuk/src/4630771db004da59992fb201641f5c4ff2c881f1/uk-openbanking-security-profile.md?at=master&fileviewer=file-view-default). Understanding and implementing this is a key part of developing applications for this space, as it is one of the common elements (theoretically) to each ASPSP implementation.

## Banks (ASPSPs)

Regrettably, the headline here is less positive. Developer Portals range from the average to the non-existent. Looking at them one by one (details current at the time of writing);

* [AIB](https://developer.aibgb.co.uk) - probably the best of the CMA9. Gives a reasonable amount of detail, documentation, and uniquely, a sandbox.

* [Barclays](https://developer.barclays.com) - poor. Provides some information, but no detail on the AIS/PIS APIs. There is a sandbox hyperlink this appears to relate only to Open Data (as distinct from AIS/PIS).

* Bank of Ireland - nothing.

* [Danske Bank](https://danskebank.com/openbanking) - at the moment this appears only to aggregate news from Danske, as opposed to being a functioning Developer Portal

* [HSBC](https://developer.hsbc.com) - static page containing only a paragraph of description and a link to OBIE.

* [LBG](https://developer.lloydsbanking.com) - *looks* great, unfortunately, once there is a bit of digging done, things aren’t as rosy as they appear. For example support requests requiring the submission of a spreadsheet (!) and there is no sandbox to experiment against.

* Nationwide - nothing, although there is an [information page](https://www.nationwide.co.uk/guides/news/articles/2017/09/open-banking-for-our-members). Oddly enough this misrepresents the consent flow, omitting the authentication and authorisation steps...

* RBS - n/a, although there is an [old portal](https://developer.bluebank.io/) which appears to relate to a hackathon run in early 2017, before the final Open Banking specifications were published.

* Santander - nothing.

## Analysis

OBIE are currently running a ‘[managed rollout](https://www.openbanking.org.uk/about-us/news/open-banking-begins-managed-roll/)’, which amounts to a select range of Banks working with a select range of Third Parties. It’s unclear how this amounts to being ‘live’ or how this, and the absence of an open, functioning, OIDC compliant sandbox anywhere are actually in the spirit of the legislation. Further, it remains unclear when the general public will have access to applications exercising the Open Banking APIs, which ultimately means being able to control, more effectively, data which is theirs.

The aim of the [CMA Order](https://www.gov.uk/government/publications/retail-banking-market-investigation-order-2017), the source of the UK’s version of open banking and the OBIE, was to promote more effective competition through increased customer engagement. This idea has matured over time, to what Imran Gulamhuseinwala, the CMA-appointed trustee, [summarised](http://www.wired.co.uk/article/open-banking-market-problems-fintech-expert) as "trying to build a standard API everyone conforms to. This means that if you're a fintech entrepreneur, and you want to connect with all the banks in the UK, it's one set of APIs and boom - they're all available to you."

The reality appears to be very different. As a developer, without a test environment and with only specifications for reference, it’s extremely difficult to build a functioning application. Those who are involved in the ‘managed rollout’ appear to have a major advantage as both early adopters, and in the ability to circumvent the exceptionally poor developer portals the banks have made live so far. A cynical observer might go as far as to suggest that, in its current form, open banking in the UK is anything but, and is only continuing to cement the difficult process of engaging with a bank to access data.

The explanation may be in the ‘Rome wasn’t built in a day’ - simply that this is the first step on a journey, but equally no-one should be satisfied with what has been built so far. A frequent complaint about Open Banking, is that by being paid for and driven by the Banks, it serves their interests as opposed to those of the consumer, which was the original aim of the legislation. After a week of being ‘live’, we must remain hopeful that open banking will actually become open, rather than just being business as usual.

