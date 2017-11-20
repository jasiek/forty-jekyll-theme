---
layout: post
title: Open Banking is finally open!
---

Happily, this week, a recent development in the ecosystem gives us cause for genuine positivity in the face of continuing inertia.

Up until this week, the only way to access a fully conformant mock bank was to go through Open Banking. This organisation is largely set up to cater for companies whose intention is to get full regulatory authorisation - it fulfils this requirement well, providing a unique trust framework whereby ASPSPs can be sure of the status and identity of a TPP at any point.

What hadn't previously be catered for was the individual or small organisation beginning their open banking journey, simply wanting to try the functional APIs without going through an onerous and potentially invasive registration process. [Quentin Castel](https://www.linkedin.com/in/qcastel) and [Simon Harding](https://www.linkedin.com/in/simon-harding-0896a015) of Forgerock (already the providers of one of the OBIE's mock banks) have met this need with the development of a '[directory lite](https://directory.integ-ob.forgerock.financial/)'. This enables those interested to register with a minimum of information, then generate the necessary certification and software statement assertion, which in turn can be used for registration with Forgebank. The functionality is explored in this video Quentin has made - [https://youtu.be/-BU12TGbBFA](https://youtu.be/-BU12TGbBFA) 

To supplement this new facility, Quentin has also developed a complete [Postman Environment](https://github.com/ForgeRock/ForgeRock-OpenBanking-Sample/tree/master/postman), which contains all the necessary commands for certificate/SSA generation, Forgebank onboarding, and accessing protected resources - in essence he's done the hard work for you. I've been working with Quentin, Simon and the Forgerock guys for some time, and have been continually impressed by their generosity of spirit in contributing to Open Banking in the UK - this is another example of that.

Please watch the video, give the APIs a go and let us know your feedback.

NB CAVEATS

1.  The facility is in Beta at the moment. There will be bugs - we're happy to receive feedback on these - we'll add those interested to a slack channel for this purpose.
1.  We provide support via [open-banking-uk.slack.com](http://open-banking-uk.slack.com) (register at [https://signup.openbanking.space](https://signup.openbanking.space)) but, given that this is a free to use service, we don't have an SLA on addressing issues/queries and will respond on a 'best endeavours' basis. This said there are a large number of very experienced, clever people in our Slack instance who may be able to help.
1.  Please **do not** contact OBIE's service desk in relation to this facility. Their support extends only to their production facilities, and (currently) this isn't one of them.

