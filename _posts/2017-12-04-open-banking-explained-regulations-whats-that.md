---
layout: post
title: Regulations - what's that? (CMA Order, PSD2, RTS on SCA)
---

Some insight into this subject was given in the prior post [(see here)](/2017/11/20/what-is-open-banking.html), but to elucidate further;

The [CMA Order](https://www.gov.uk/government/publications/retail-banking-market-investigation-order-2017) was published following their [investigation into retail banking](https://www.gov.uk/cma-cases/review-of-banking-for-small-and-medium-sized-businesses-smes-in-the-uk#final-report). This requires that 9 Banks in the UK (referred to as the CMA9) implement Application Programming Interfaces (APIs) to deliver information about a range of on sale products (Open Data), to deliver information about customer accounts (AISP) and to allow the initiation of payments on a customer’s behalf (PISP).

The [Revised Payment Services Directive](https://ec.europa.eu/info/law/payment-services-psd-2-directive-eu-2015-2366_en) (referred to as PSD2) is Europe-wide legislation which places similar obligations (and many more besides in relation to implementation, transaction processing and communication) on financial institutions across Europe. This has now been supplemented by the [Regulatory Technical Standards (RTS) on Strong Customer Authentication (SCA)](http://ec.europa.eu/finance/docs/level-2-measures/psd2-rts-2017-7782_en.pdf), these being essentially the ‘how’ where PSD2 is the ‘what’.

From an implementation point of view, the differences are becoming less significant, as Open Banking Ltd has been [given a mandate](https://www.openbanking.org.uk/about-us/news/uks-open-banking-project-expanded/) to expand the functional coverage of its API specifications to cover the functionality required by PSD2; originally their scope was limited to that required by the CMA Order. As I mentioned previously, the best way to understand this relationship, based both on scope and the approach the banks are taking to implementation, is to see the functional scope required by the CMA Order as being the first step on the road to PSD2 compliance.

### Participants – who’s who (Regulators vs OB, Banks, TPPs)

European Banking Authority – the EU’s regulatory body for the financial services industry, responsible for drafting EU Law relating to this space.

European Commission – the EU body with responsibility for the adoption of the EBA’s proposals

Financial Conduct Authority – the UK regulatory body for financial services, responsible for drafting the statutory instrument incepting PSD2 into the law of the UK

Competition and Markets Authority – government department responsible for reducing anti-competitive practices, and the progenitor of the order

Open Banking Ltd (OBIE) – body set up by the CMA and nine impacted banks to deliver API specifications, a directory of authorised participants and operational support for the new ecosystem

### Component parts – Specifications, Platforms and the Directory

What are the essentials of a Bank’s implementation? From the conceptual to the outer layer, we can start with;

API Specifications – these amount to the functional design of how an API should behave. In the UK, these have been designed by OBIE in collaboration between a number of fintechs and the CMA9, to satisfy the requirements of the order, and are now being expanded to cover the requirements of PSD2. At a high level, they dictate the process of forming a connection (and its properties relating to data security), the structure and contents of the messages exchanged by TPPs and banks (including field types, cardinality, values and occurrences), and the scope of resources that can be accessed. Having a common specification used by (at least) 9 banks means that (in theory) a TPP developer can leverage an economy of scale in building applications as minimal work will be required to account for variances in the interfaces of the banks. In short, as the specifications are common, for the most part the behaviour of each bank implementation should be the same.

Platforms – API platforms assist banks in making their services available. They can provide an interface to communicate designs and other information, issue credentials, expose endpoints, assist with threat protection and a great deal more besides. Essentially, using an API platform can greatly assist in the process of exposing new interfaces to the world. A good explanation of the services an example platform provides can be found on the [Apigee website](https://apigee.com/api-management/). There are a very wide range of API platforms out there, but as the content of the link reflects, much of their subject matter that advertise is industry standard, as opposed to proprietary.

In the world of open banking, this is inevitable, as API specifications are open, and the ID profile is an industry standard, but it's clear that many of the platform providers do not make clear that much of their offerings are simply adoptions of the work of organisations like Open Banking, the OpenID Foundation, [RAIDiAM](https://www.raidiam.com/). In one example we’ve seen, and organisation purporting to offer its own API specification had copied that from Open Banking and neglected to remove references to the latter’s open licence. As flattering for OBIE as this might be, it goes to show that, rather than specifications or flows, providers should look to factors such as ease of integration and developer concerns when considering the platform market.

OB Directory – this is one of the key offerings of the OB, but it is important to clarify the scope and functionality. The principle of PSD2 is that TPPs registered across the member states can, with passporting rights, interact with any bank. This presents banks across the EU with a challenge – how to validate the status and identity of those TPPs asking to onboard and interact. OBIE have closed this gap by providing a Directory service that offers a verification (of regulatory status) and identification service for both TPPs and banks. These are issued credentials (following validation) which they can use to identify themselves to new partners, who in turn can use the Directory service to validate that the credentials remain current, both when the relationship is initially formed, and on an ongoing basis. This last aspect is particularly important given that TPPs may have their regulatory status revoked.

To date the Directory’s policy is to cover only those TPPs registered or passported into the UK. There has been talk across the EU about the EBA establishing a register, or other organisations like [PRETA](https://www.preta.eu/) building a function that would cover the entirety of Europe. Initial indications are that these would be sources of policy only, and would not provide the necessary technical means, such as certificates for assuring identity and securing data against tampering and eavesdropping. Additionally, the EBA have made it clear that their register could not be relied upon from a liability point of view, which renders it of very limited value. Ultimately the OB Directory fills a very important gap in the ecosystem, and is a first attempt at a model, whilst limited in initial scope, where there is significant room for expansion.

### Getting ready for a basic customer journey

Frequently asked questions include what the customer interaction looks like, and how a TPP gets ready to fulfil this need. To answer this, we can break it down into several parts, and will answer this in a UK context only.

#### Getting ready

1. TPPs will first need to *register with Open Banking*. The detail of this can be found on their website, but will involve validation of those elements mentioned above.

1. Before OBIE will issue credentials, a TPP must be *authorised by its National Competent Authority*, the FCA in the UK, or be issued a passport to the UK.

1. Once 1&2, are complete, the TPP can *onboard with one or all of the CMA9*, which can be done automatically or manually depending on the provider. Each bank will check the validity of OB-issued credentials presented (using an API call) then issue credentials which TPPs can use to interact with their APIs.

#### The customer journey

1. Any TPP application will need to send the bank the details of the resource it wishes to access, once the customer has reached a point where they are ready to authorise. To keep things simple, we will assume that the customer is seeking to authorise a payment or the flow of some information back to the TPP.

1. For messages to flow between TPP and bank, a mutually assured, secure connection must be formed between the two. At this point, it is likely that the bank will use the Directory to check that the authorisation status of the TPP is still current, which it can do automatically via an API call.

1. The TPP must make the scope of the transaction clear to the customer, so that they can consent to it – this might be something as simple as the amount they are going to pay for a product on a date, or giving the ability to check a balance on an account for a period of time. This information will also be sent to the bank to facilitate creation of the authorisation model.

1. The next step is for the customer to authorise the transaction with the bank. They will be redirected to their bank’s portal / application where they will need to authenticate, and will then have the details of the transaction re-presented to them, and will be prompted to authorise the same.

1. Once authorisation is provided, the customer is redirected back to the TPP application, and their journey is complete. The application will complete the process of initiating payment or pulling information, which can be used to support a multiple of use cases.

This post and the last have sought to explain the ecosystem, and the basics of the players involved, the design and the process involved in onboarding and making transactions. In the next post we will look to what can be expected after 13 January 2018, the impact of the RTS, and the short term future for open banking.

