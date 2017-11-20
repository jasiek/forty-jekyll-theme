---
layout: post
title: Why is Open Banking transactional data inherently useless?
description: A small detail prevents TPPs from utilising transactional data
---

In this article, I'm going to make a very strong claim about a particular design decision which is
currently being hotly debated between the Fintech community and CMA9 banks, and will outline why it
is exceptionally important that Open Banking Ltd must push banks to comply.

Open Banking Limited is an entity which was created by the CMA9 to develop data standards and protocols
which would permit an open banking ecosystem to operate in the United Kingdom, bringing desperately needed
competition to UK's retail and small business banking sector.

In non-tech speak, they design data "templates" which allow both parties (the TPPs and ASPSPs) to have
a "conversation" using a common language. The development of these data standards is a huge undertaking
and I bow to my former colleagues at Open Banking Ltd for pushing through such a colossal amount of work at breakneck
pace to deliver to CMA's deadlines.

As is with most standards, they are developed through stakeholder engagement - where representatives of
various participants in this ecosystem come together and decide on what should be mandatory, what should
be optional, and what can be left out. This group consists primarily of representatives of banks, fintech
companies and consumers.

It is extremely unfortunate that during this process [it has been suggested that immutable transaction
identifiers would not be mandatory](https://openbanking.atlassian.net/wiki/spaces/DZ/pages/126485500/Transactions+v2.0.0#Transactionsv2.0.0-DataDictionary).
This is truly bad news for everyone wishing to build an application
on top of the OB ecosystem. Without immutable transactions, it is impossible to build a system which
can be truly relied on in terms of data veracity.

Given that transactions displayed in your online banking platform can appear, then disappear, change dates,
change descriptions, have different states (pending, booked, etc.), but contain no unique identifier --
there is no way of determining if
two transactions are really the same thing. Any application which requires continuous access to an account
(which is probably most of them), will have no reliable way of determining if they have already "seen"
transactions for a particular account. No reasonably reliable applications can be built on such a brittle
foundation. Any workaround strategy for this would focus on solving a problem which should not have existed
in the first place.

Providing this information is in the interest of banks as well - the simplest strategy against the above
described deficiency is to pull the entire transaction list for an account every time it needs to be refreshed.
This could mean months of data, as there is no defined "cut-off" point beyond which transaction data
is guaranteed not to change. Pulling large amounts of records on a regular basis means that banks will
need to spend more money on additional infrastructure required to handle this excess.

I'd argue (and this is a widely shared view among people attempting to
build applications on top of these APIs), that the transaction endpoint must be a reliable single source
of truth, otherwise it is a pointless exercise, whose only object is to give the impression that what
has been developed is in line with the spirit of what CMA has requested the banks to do.

It is not surprising why -- banks see OB in the UK primarily as a compliance exercise, and there is
zero appetite to do anything than the bare minimum. Banks have said that providing this identifier
would require development effort on their part and thus have zero interest in doing the work.
This, naturally is no excuse -- just Lloyd's profits rose by 24% last year to more than 5bn!

It is absolutely crucial that this poor excuse is pushed back on -- there are many products which cannot
be built if this information is not made available. Furthermore, this design decision goes against the
spirit in which OB was brought into existence -- to enable competition and to deliver *usable* data standards
and interfaces.



