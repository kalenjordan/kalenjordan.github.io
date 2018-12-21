---
layout: article
featured_image: '/assets/img/Screen%20Shot%202018-12-20%20at%207.56.51%20PM.png'
title: All Magento Extensions Should Be SaaS
---

I have a theory I’ve been kicking around in the old noggin for a while, and it’s that all 3rd party Magento extensions should be SaaS apps.

I know, I know — sounds like I drank some bad kool-aid, but hang with me here for a minute.

First off, it seems to me it’s already the case that most of the successful and fast growing “extension companies” are already SaaS — just look at the list of sponsors at Imagine. You’re looking basically at all SaaS apps.

That’s not to say that the people that matter in the community are the ones with the most money — far from it. That’s only piece of my reasoning — it’s a successful business model.

I remember when a lot of my buddies with deployed extension companies were really struggling with sales in that awkward period between M1 and M2 and I was sitting pretty because I was on a recurring revenue model.

Recurring revenue just simply is a more profitable model that allows you to reinvest more heavily in your product.

But enough about money…(damn Kalen you talk about money all the time!), there are lots of reasons why I believe this. Let’s talk about speed.

The importance of page load time has become increasingly important, as it’s become more of a signal in organic rankings, as consumer expectations have changed, and as we as an industry have become aware of just how important page load time is.

When you have 50 3rd party extensions doing all sorts of stuff server-side while the page is rendering, optimizing performance is a bit of a nightmare. I believe that the model where you have some frontend javascript that alls out over an API elsewhere is simply the better model here.

Sure, there are also problems with frontend load times — I had someone who does a lot of work with Shopify recently tell me that’s a major issue, which was surprising to me. But at the very least, now you’re just dealing with frontend optimization as opposed to dealing with both front and back.

So you’re in a better position to start with, and also it’s in the SaaS app’s interest to optimize their frontend load times — and that’s something that we see continuing to improve in the industry. It’s also becoming more common to have more and more frontend snippets on your site which is a problem in and of itself.

I had a buddy telling me about one of their clients that’s on a PWA. They built a custom PWA for them from scratch — I was asking how they handled 3rd party functionality within the PWA and they said every piece of 3rd party functionality is simply a SaaS app.

I don’t know what it’s going to look like exactly for 3rd party extensions to support PWA — it seems that’s not something we’ve received any guidance on yet. But I just can’t imagine how you could have 3rd party extensions involved server-side during page rendering. You need to have a fully cacheable static HTML app shell for PWA.

Also, I’m betting that SaaS apps are going to be faster to build PWA support into their frontend snippets of code, because their frontend snippets are all hosted and they can deploy changes to them centrally without having to deploy individual code updates to thousands of sites.

Now, the power of Magento as compared to SaaS ecommerce platforms is of course it’s extensibility. I do think that it’s important to be able to customize things at the code-level for your site, but I think that’s something the merchant or their agency should be handling.

When it comes to 3rd party extensions, I think the Magento marketplace should just support SaaS apps.

There’s also a huge ease of installation component here. Who wants to deal with code-level changes when adding an app to your store? That’s the kind of thing your development team should be doing anyways.

I think that all of the effort going into marketplace review of code should instead go into improving the REST (or GraphQL etc.) APIs. Make those APIs super robust so that there’s a ton that can be done with them. And also put a lot of work into backwards compatibility of the APIs.

The stuff that Stripe, for example, has done around backwards compatibility and versioning of their APIs is insanely cool.

Another factor is AI. Most of the functionality covered by extensions is going to start to have an AI component to it. Think about search as an example. Sure, you could install a 3rd party faceted search into your site, or you could use a SaaS app like Klevu.

What are the chances that a deployed module is going to have a prayer at delivering AI functionality? This is the domain of SaaS apps, with their significant investment into infrastructure and the concentration of user data they have at their fingertips.

Well, that about sums it up. Let me know what you think! Would love to hear any feedback! Any of course sorry to any friends with non-SaaS extensions out there ;)
