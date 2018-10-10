---
layout: post
title: The strange case of the Open Banking Implementation Entity (OBIE)
---

For those unaware, the OBIE was established as a result of the Competition and Markets Authority's [Order into Retail Banking](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/600842/retail-banking-market-investigation-order-2017.pdf), and subsequently had its role expanded to develop API specifications for the purposes of PSD2 compliance. It has now completed this activity, and done much good work, but its PR/Comms output is confusing to the point of being misleading.

![OBIE updates](https://www.openbanking.org.uk/wp-content/uploads/September-infographic-1024x536.png)

Breaking down this information shows a very odd story. They've used large font to highlight they have enrolled **77 providers**, made up of;

* 52 TPPs - but in very small text they make clear that only 6 of these have products which use the APIs live in market.
* 25 ASPSPs - its not clear what number of these are providing API platforms for live use, but the TPP community is only aware of the CMA9.

So from a headline figure of 77, there is now a total of 15 with services live in market.

Taking the **4.2m** API calls, this is at such a high level of detail to be meaningless. To put this in context, to access a data payload (balance, transactions etc.) a minimum of 3 API calls is required:

1. POST /account-requests,
1. GET /accounts
1. GET /accounts/{AccountID}/transactions

Calls 2 and 3 are only possible if the customer successfully authenticates with the ASPSP, and feedback has shown a high rate of dropout at this point. Without clarification of what number of those 4.2m calls are actually successful pull downs of data, outside of any testing/monitoring activity conducted by ASPSPs and TPPs, the headline number shows very little about the health of the ecosystem.

### Moving to the key milestones

**Updated standards (v3)** - it's true that OBIE published a new specification version, but the major changes in this release related to the expansion of payment resources, which receive no mention. Instead the headline is the changes to the account information specification, which are relatively minor and allow for a wider range of account products.

**CMA9 live on v2** - there was a deadline of 7 September, but it's doubtful whether all of the CMA9 were actually live on this date. Based on the [Security Profile Conformance Page](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/126321042/Open+Banking+Security+Profile+Conformance), it's clear that there are still v2 implementation issues outstanding with most ASPSPs, with only AIB and HSBC having implemented successfully. 'Live with caveats' might be more accurate.

Finally highlighting **Barclays** inclusion of an account aggregation function in its mobile banking app. Whether this is a cause for celebration is debatable. It's clear that the TPP community have faced a [number of obstacles](https://github.com/openbankingspace/tpp-issues/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+barclays) to integration with Barclays, and in many cases Barclays have steadfastly refused to accept problems highlighted. Notably, the market leader in open banking customer acquisition **Yolt** went live with Barclays last among the CMA9, only recently and OBIE's PR highlights. Given that Barclays have been the hardest of the CMA9 to integrate with, whether as a result of incompetence or intention on their part, it is difficult to understand why the OBIE would promote their new functionality, particularly as it is not available to all of their customers. It is notable that both PSD2 and the CMA Order point to API platforms being primarily for consumption by Third Parties, in part for the purpose of improving competition. Celebrating adoption by an organisation found (by the CMA's investigation) to be part of this non-competitive market is difficult to understand, even more so when this organisation has been the focus of so much complaint from TPPs themselves.

The OBIE has done admirable work in the delivery of its API specifications and directory service, solving many issues faced by ASPSPs and TPPs alike. In its communications to the outside world, it seems hell bent on creating a positive, but misleading narrative about API adoption, which potentially draws focus away from the many issues which are inhibiting both TPP and customer adoption today. If it really wants to have a success story to tell, its time might be better focussed on resolving these problems and bringing them to the forefront of public discussion.