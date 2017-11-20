---
layout: post
title: How was your data shared so far, and what will change with Open Banking?
description: Why we should bury screen scraping for good and embrace the automation.
---

This post is written in response to [BBC: Why banks will share your financial secrets](https://www.bbc.co.uk/news/amp/business-42253051).

### tl:dr;

> Your data is going to be safer when shared through the Open Banking ecosystem. It will only be accessed by whitelisted entities,
> only a subset of data will be shared, for a limited time, and you will be able to revoke access whenever you will choose to.
> None of which applies at this time - this is a change for the better, but we have yet to see whether customers see value in
> having an app store for their bank account.

It is obviously true that your financial history is something to be closely guarded. Saying however, that the information is available
to you and your bank only is misleading. Every time you use a credit, or debit card, that transactional information goes to one of
payment processors such as Visa or MasterCard - these are huge, American financial services company which indirectly hold insights into
the spending habits of approximately 720 million cardholders (if we include Visa, AMEX and UnionPay), this number bubbles up to *two billion*.

Presently, unless you're affiliated with a bank, you do not have any official ways of accessing anyone's banking information programatically. Despite that,
many companies will still offer you a service which as an input takes your financial history. How is that possible?

### Enter Screen Scraping

Until recently, the primary way to access that information was by asking the end user for their banking username and password, logging in
using those credentials, and extracting whatever information was deemed to be valuable, a technique known as screen scraping.
This is dangerous for a number of reasons - the
chief reason being - once you share your bank login details, that is it - you've just given a company access to your bank account, and
they can, in theory do whatever they want. There is no way of easily revoking that, unless you change your password. Your bank might decide
that there is suspicious activity (as someone has logged in from Mongolia, or some other remote destination), and will deactivate your
online banking access. I'm confident many of you know what pains you have to go through to have that reinstated - in the best of cases
it will require a visit to the branch. In the worst - who knows - you might be locked out from your bank account for two weeks, until a
physical piece of paper arrives and you can finally unlock it.

Screen scraping provides a way for anyone to access your account - this could be a legitimate business, loaded with VC money and regulated
by the FCA, two guys in a garage hacking on the world's best banking aggregation app, or a rogue actor who is just waiting to rip you off.
There is no easy way to tell, there is no easy way to cut them off, or shut them down, and once your data is in a jurisdiction which doesn't
care, there's no way to do anything about that data being leaked, resold - you name it.

### How will this change with programatic access?

How would we fix it? Firstly, you would never share your login and password with anyone - that remains your private master key, which you
reveal to no-one. Instead of supplying that information, you would visit the page of the business you wish to deal with and click on a button
which says "log in with your bank", or "connect to your bank". You would then be redirected to and prompted, *by your bank*
to log in with those master credentials, on the bank's portal or (in future) through their app.
Once the bank authenticates you, it will display a list of data categories, which the business is interested in. You, as the
end user can then decide if you feel comfortable with the data being shared or not. Unlike with screen scraping, only a subset of data is shared -
a subset which you agree to, and for a fixed period of time. The business can only pull this data and has no access to your account through
then bank's portal, in stark contrast to the screen scraping approach.

Once approved, the business is now issued a set of credentials which will work only for that single end user, and only for the subset of data
to which consent has been given. Those credentials work for a certain period of time, after which consent must be granted again by the user -
so there is little risk that the end user will be unaware of what is happening to their account.

Per-user per-data-scope credentials have the added benefit that they can be revoked at any time. Suppose a user decides they no longer want to
share data with a particular business - they can then visit their online banking dashboard and click a button and access will be revoked.
Similarly, if that business' IT infrastructure became compromised, the bank can then revoke access en masse.

Last of all, all those third parties must be regulated. If they can't prove they are under the watchful eye of their national regulator, they
can't participate in the ecosystem. This significantly reduces the risk that a rogue actor can start extracting data from customers.

### When is this coming?

There are two channels which currently make this possible in the United Kingdom: [Open Banking UK](https://www.openbanking.org.uk/) and
[Teller](https://teller.io/). The former is due to make their ecosystem available on January 13th, but this will be to select bank staff
and a small range of third party businesses. It remains unclear whether the general public will be able to make use of third party
applications and consent to them accessing your data. Teller is available right now.

### Adoption - the real issue

Despite all the hype and inflated expectations around being able to connect to your bank account, it remains to be seen whether this is
seen as added value by customers. Despite all efforts, only a tiny number of customers in the UK are willing to switch away from their bank.
This may well share the fate of Open Data APIs released by Open Banking last year - which is that no one cares and no one uses them.
