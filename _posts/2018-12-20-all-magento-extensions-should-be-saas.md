---
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

The stuff that [Stripe](https://stripe.com/blog/api-versioning), for example, has done around backwards compatibility and versioning of their APIs is insanely cool.

Another factor is AI. Most of the functionality covered by extensions is going to start to have an AI component to it. Think about search as an example. Sure, you could install a 3rd party faceted search into your site, or you could use a SaaS app like Klevu.

What are the chances that a deployed module is going to have a prayer at delivering AI functionality? This is the domain of SaaS apps, with their significant investment into infrastructure and the concentration of user data they have at their fingertips.

Well, that about sums it up. Let me know what you think! Would love to hear any feedback! Any of course sorry to any friends with non-SaaS extensions out there ;)

---

# Objections
Below are some responses/objections that I received which I want to
respond to. Thanks to everyone for their feedback--agree or disagree, it's an 
interesting thing to discuss!

##Yes, I agree that all ecommerce should be SaaS
No, that wasn’t what I was saying :) I’m suggesting open source Magento core + code-level customization by merchants or SIs + 3rd party extensions as SaaS.

## Example types of extensions

I think a big part of this boils down to specific examples
of extensions and use cases. There will probably be some use cases
that will lend themselves more heavily towards native code than
others - so I'll start to list out some of the specific examples
I've had thus far and add to this as I go.

### Subscription box extension

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Example: one of our subscription box clients. We use the excellent extension from <a href="https://twitter.com/paradoxlabs?ref_src=twsrc%5Etfw">@paradoxlabs</a> to power this. But there is a lot of logic in that module we&#39;ve adjusted for their unique needs. Our client has avoided a SaaS subscription service in part to retain that flexibility.</p>&mdash; Scott Buchanan (@thescottsb) <a href="https://twitter.com/thescottsb/status/1076632647991021569?ref_src=twsrc%5Etfw">December 23, 2018</a></blockquote>

So this is a pretty decent example - I can see how perhaps native code could be really important for a subscription box feature. One thing I will say is that it’s interesting that the vendor of this extension is actually an SI and not really a true extension company.
That almost makes this more of an example of first party code that an agency builds and modifies for their customers than it does a true product company for an extension.
I’d be willing to bet that the amount of revenue generated for services engagements for customizations of this extension far surpass the revenue generated from the extension sales themselves.

### Cart promotion customization
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">
Say you want an extension that has cart promotion customization, you wouldn't want to throw the quote to the service on the cloud every time a re-calculation is needed, even if somehow the services are super fast internally, the network overhead would heavily impact the site performance when we integrate with more "services".
</p></blockquote>

Alright so I’m not sure I’m convinced on this one. Having worked a little bit on extensions that recalculate the cart a lot like Sweet Tooth, I am somewhat familiar with how many times a cart save can happen where it perhaps is not completely necessary but just an artifact of the Magento code base.
Let’s look at taxes and shipping. Those are 2 categories with very dominant SaaS providers and I’d argue that they need to recalculate the cost as frequently as something related to promotions would, and they seem to work just fine.

### Payment gateways

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">4/ ...with the source code, take payment gateways as an example, SaaS everything does that apply there? There is a place and true value for SaaS but this is not a zero sum game, there is room for SaaS and 3rd party extensions.</p>&mdash; Allan MacGregor (@allanmacgregor) <a href="https://twitter.com/allanmacgregor/status/1076115360519053312?ref_src=twsrc%5Etfw">December 21, 2018</a></blockquote>

I might need some more examples here because I feel like the case for SaaS pretty much makes itself here. You can keep yourself out of scope for PCI as well by minimizing native code here - and virtually all of the dominant payment gateways are SaaS - Braintree, Stripe, Paypal, etc.

I believe many European countries are ahead of the US in how they handle payment gateways which is to a large extent via iframe or linking over directly to the payment gateway to complete transaction.

There’s really no good reason in my mind to be having customers enter credit card information in your forms today.

### Import/export

One extension that comes to mind is Unirgy Rapidflow. I know a lot of people that use it because it’s reliable and does imports very quickly. I can see how it might be hard to replicate that over SaaS.

That said, perhaps a big part of what this does can be supported by bulk APIs in the core, which is something that’s currently under active development.

With a focus on SaaS-only extensions in the marketplace and doubled down resources on the flexibility and reliability of core APIs, perhaps the bulk APIs could be good enough that you wouldn’t need 3rd party import/export extensions.

## Performance

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Agree with all the other push back. Adding two other points:<br><br>1. Performance hit with many backend API calls &amp; separate origin frontend loads.<br><br>2. Encourages vendor lock-in. Any data stored on SaaS is subject to their export tools/policies. When local, you can always get it out.</p>&mdash; Scott Buchanan (@thescottsb) <a href="https://twitter.com/thescottsb/status/1076482576552992768?ref_src=twsrc%5Etfw">December 22, 2018</a></blockquote>

That’s true regarding multiple backend API calls but I think is a somewhat minor detail in the broader context of performance. First off, many of the same people disagreeing on this point are fans of microservices, which essentially means more backend API calls to potentially different origin domains.

That said, frontend optimization of javascript snippets with external API calls is definitely something that needs to be focused on. I actually heard recently from someone in the Shopify space that a lot of Shopify stores are super slow because of this.

But in my mind it’s a solveable problem—most Magento stores have to deal with both frontend and backend performance optimization. If you can limit to just one of the two, that’s already a one.

And with the direction that PWA is going, it seems like virtually all data is going to be populated from REST or GraphQL calls anyways.

## Downtime?
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Agree with Allen on nearly every point he made. Also what happens when just one of these SaaS vendors goes down on the holidays? What happens when they go belly up? There are real concrete downsides here and also some obvious upsides, but it’s not Magento’s advantage. 1/x</p>&mdash; David Alger (@blackbooker) <a href="https://twitter.com/blackbooker/status/1076476585836982272?ref_src=twsrc%5Etfw">December 22, 2018</a></blockquote>

As an SI that’s used to being able to get in and troubleshoot, debug, and fix any part in the entire codebase, losing that control to SaaS that could go down is kind of a big deal. It may seem like there is very little upside to offloading infrastructure to a 3rd party in this way, but I’d like to reframe this slightly.

While it’s true that, as the SI, your experience is worsened when you’re unable to fix anything, and bill for that time, this doesn’t necessarily mean that the overall experience is worse for the merchant.

For example, pre-SaaS, let’s say Fedex API goes down and the merchant’s checkout is broken. Happens on a busy day, they contact you, the SI, to resolve it. You get in there, figure it out, roll out a fix and deploy - maybe if you’re very fast it’s resolved within hours from when customer’s first reported it to when it’s actually fixed.

This may feel like a win to the SI because they were able to fix the problem quickly—obviously it sucks for the merchant but Fedex going down was outside of everyone’s control so it’s something that couldn’t have been avoided, and the fact you fixed it quickly is great.

Now let’s fast-forward to SaaS. The shipping provider deals with shipping APIs all the time. That’s their specialty. They’ve dealt with Fedex APIs going down so many times that they already have automatic fallbacks in place.

Same situation repeats - except this time there’s zero downtime - it’s handled without a blip.

That’s the flipside to “what if a SaaS has downtime” - it’s when SaaS through their expertise is able to be more reliable than native code.

Now, it goes without saying that even if it’s true that SaaS extensions are the future, that doesn’t mean that you should really on every SaaS that just came on the market 2 weeks ago. As SaaS grows in popularity, everyone in that ecosystem is building expertise around infrastructure and ultimately becoming better at reliability and fault tolerance of their products.

## Encourages vendor lock-in
This is true, however one of the trends that I see developing is more widely adopted migration-friendly policies around your data. All of the huge tech companies are starting to do this and I think you see that rippling downmarket.

This is similar to my point on SaaS reliability—it’s something that is improving and will continue to improve. And even if SaaS is ultimately the right model for extensions, that doesn’t mean you should select a *bad* SaaS extension—whether due to their export policy, reliability, quality of their API, or anything else.

## It limits the customizations an SI is able to do

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Adding to this after a *few* issues with SaaS style solutions. The support a SI can then offer is crippled. We are resellers. It’s pretty common to want to modify/alter/patch 3rd party code and to take that away I would leave magento behind.</p>&mdash; james cowie (@jcowie) <a href="https://twitter.com/jcowie/status/1076421196672053248?ref_src=twsrc%5Etfw">December 22, 2018</a></blockquote>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">But...that&#39;s the point. What the &quot;extension&quot; is doing inside the API call is what may need to be customized. Of course what&#39;s outside the black box (inputs/outputs) is visible, but we&#39;re talking about the customization of the *extension*, not everything outside it.</p>&mdash; Scott Buchanan (@thescottsb) <a href="https://twitter.com/thescottsb/status/1076638999979220992?ref_src=twsrc%5Etfw">December 23, 2018</a></blockquote>

Obviously SIs are very accustomed to being able to customize 3rd party extensions, and I can see how losing that ability would be concerning.

The flipside of that though is that many things that a merchant might want to be customized don’t necessarily have to.

When you’re working with a blank canvas and can do anything that you want to do, you will probably lean towards customizations that may not really be that important.

For the SaaS extension, the problem domain that they solve is their area of expertise, so I believe they are in the best position to give you the ability to make the customizations that are important to your business and to continue to iterate on their offering in ways that are maximally valuable for the merchant.

Now, if a merchant needs something customized and it’s 100% a deal breaker, then it is what it is. I’d bet that 80% of customizations made to 3rd party extensions might be better off not made. But the devil is in the details, so it would be interesting to dig into more speific examples.

## What about upmarket?
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">5/ Finally, have you considered how this solution looks when you go up market? Talking with larger organizations like enterprise or goverment bodies, yeah we can build your solution but we are also going to need you to talk with this other 50 vendors and setup the...</p>&mdash; Allan MacGregor (@allanmacgregor) <a href="https://twitter.com/allanmacgregor/status/1076115361378914304?ref_src=twsrc%5Etfw">December 21, 2018</a></blockquote>

I think that as you go further upmarket with bigger budgets and more custom, less SaaSy needs, you simply opt for more 1st party code and less SaaS. More expensive but that’s what they would expect anyways.
