---
layout: post
title: A Brief History of Conformance and Certification in the World of Open Banking / PSD2
author: jha
---

Those reading the FCA's [CP18-25 Paper](https://www.fca.org.uk/publication/consultation/cp18-25.pdf) on its approach to the PSD2 Regulatory Technical Standards (RTS) will note the references to 'conformance testing'. This is not a novel concept in the UK - it was developed out of the [OpenID Foundation](https://openid.net/foundation/)'s [approach to certification](https://openid.net/certification/) for implementers of OpenID Connect. To facilitate open banking, the Open Banking Implementation Entity (OBIE) developed a [draft security profile](https://bitbucket.org/openid/obuk/src/f7d1f6eb7b06658e890e9a1ee18965821f375911/uk-openbanking-security-profile.md?at=master&fileviewer=file-view-default) which dictates how connections between ASPSPs (banks) and third parties (TPPs) should be secured. This profile is currently on a trajectory where, as a consequence of the need to align around eIDAS certificates as the sole means of identification, the industry will align to the [Financial-Grade API Security Profile](https://bitbucket.org/openid/fapi/src) (FAPI), in its second version. This profile is agnostic of jurisdictional/regulatory context, and is being leveraged for most of the open banking initiatives going on around the world today.

Re-winding to late-2017, whilst the OBIE security profile used elements of FAPI, OpenID Connect and OAuth2, there was no singular means for an implementer to validate the correctness of what they had built. To build trust in the ecosystem, it was important for banks to demonstrate to TPPs that their authorisation server build had followed the security profile correctly, and to enable validation of any unexplained errors. OBIE (represented by the [author](https://www.linkedin.com/in/johnheatonarmstrong/)) and [Joseph Heenan](https://www.linkedin.com/in/josephheenan/) of [Fintechlabs](http://fintechlabs.in) got to work on a [Conformance Suite](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/23856067/OB+OIDC+Conformance+Suite) and [Certification Approach](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/117440540/Conformance+Certification+Process) to assist banks (and platform vendors) in the validation of their implementations of the security profile, to allow them to self-certify, and [publish the fact](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/126321042/Open+Banking+Security+Profile+Conformance).

The response to this activity was varied. Some required convincing of the need to ensure that a common profile was implemented correctly. Some of the banks were concerned about the fast development trajectory of the suite, taking little account of the unchanging nature of the standards being validated. In simple terms, the exam questions were increasing, but the subject matter for study had remained the same. Today, the suite has been used thousands of times, and is undoubtedly one of the most significant contributions to the open banking ecosystem worldwide. To quote one senior bank representative - '_our only complaint about the suite is that we wish it was available earlier_'.

Experience of running the Certification process led to the view that a similar conformance suite was essential for validation of implementations of the functional API specifications. This would not only enable banks to test their platforms, but would complete the circle on an open banking Certification Framework, bringing an independent service into the public domain, and laying groundwork for the bank-TPP trust relationships which are essential to the development of this ecosystem. Despite support from the TPP community (see [FDATA papers](https://fdata.org.uk/fdata-papers/)), the proposal was met with some resistance from within the OBIE and banks, due to concerns regarding liability. Thankfully, the [CMA's Trustee](https://www.linkedin.com/in/imran-gulamhuseinwala-b673701/) supported the idea, and a [proposition](https://openbanking.atlassian.net/wiki/spaces/WOR/pages/243171545/Proposition+-+Conformance+and+Certification) was adopted at the OBIE Steering Group to move (further) forward with the development of a functional conformance suite, and a framework to bring the two areas together. Thanks must go to [Chris Michael](https://www.linkedin.com/in/cjemichael/), [Ezo Saleh](https://www.linkedin.com/in/ezosaleh/), [Rob Mckinnon](https://www.linkedin.com/in/rob-mckinnon-7a96601/) and [Mohammed Bana](https://www.linkedin.com/in/mbana/) for their commitment to the concept, and patience with a demanding Product Owner! The suite will soon be made open source, and with the code available for scrutiny and collaboration.

To return the FCA's consultative paper, weight has been placed on the importance of running conformance testing services, and using the results as part of an application for exemption from the requirement to build a fallback interface. Both the CMA Order and PSD2 (although to a lesser extent) place emphasis on the adoption of industry standards. OBIE and the others in Europe have done an excellent job of defining these standards, and the dual challenges the ecosystem now faces are to implement these, and ensure mutual trust around the correctness, performance, availability and stability of API platforms. It is a positive development that both the EBA and the FCA have seen fit to support conformance/certification initiatives, but as with so many elements of this domain, certification should not be seen as a compliance activity. The nature of the framework will be a transparent, objective and universal process which anyone can access to validate their implementation and demonstrate both to the regulator, and to consumers (be they TPP or PSU) that it is usable. In this respect it aligns to the basic aims of the open banking regulatory regimes, and the concept of an open ecosystem based on trust, consent, security and data portability.

*John Heaton-Armstrong* has worked at the forefront of the UK's Open Banking initiative since it began, and led the delivery of technical products at Open Banking Ltd in the UK, including model banks, security and functional conformance suites, and reference applications. Up until July 2017 he led the development of the OBIE Open Data standard, the first part of the response to the CMA Order. He was Product Owner for the OB Security Profile and liaised with the OpenID Foundation to ensure a pathway to the adoption of the FAPI standard. He is a member of the OpenID Foundation, and its Financial Grade API (FAPI) Working Group. He works directly with Fintechs to ensure effective representation of their concerns, and has advised the FCA, EBA and Central Bank of Ireland on similar issues. John is a Senior Associate at [RAiDiAM](https://www.raidiam.com), and works with a range of banks worldwide covering both Digital Identity and Open Banking domains. He is a contributor to the Consumer Data Right standard being developed by Data61 and their API Standards Working Group.
