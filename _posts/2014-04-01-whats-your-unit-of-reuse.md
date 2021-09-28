---
layout: post
title: "What's your unit of reuse?"
categories: [Software Engineering]
---

We are constantly trying to lighten our load on Earth. A lot of man-made things are designed to last beyond their useful life, going full-circle and ending up in a store after being discarded and remade. New packaging, for example, can be made from old packaging - old plastic and cardboard recycled appropriately. Mother nature has been doing this for a long time too! A great example is earthworms, which munch organic matter from dead plant material and produce lovely soil, ready for the cycle of growth to continue. Earthworms are able to do this because of the material being reused. It's organic matter, and there's only one kind of thing.

![Earthworms making soil](/images/earthworms.jpg)

Other "stuff" is just destined for landfill. Lots of human-made things are not easily reused: pieces of disparate material such as wood, plastic and cardboard glued together or snapped together never to come apart. I was throwing away the box from a toy helicopter the other day, and its plastic window was glued to its cardboard box. Unsure how to recycle this I shrugged and threw the whole thing in the recycle bin. I am guessing some poor person has to take that plastic and cardboard apart and put them in separate piles. It gets worse: in the computer industry we have [toxic e-waste](http://www.cbsnews.com/news/following-the-trail-of-toxic-e-waste/) being handled by people.

![E-waste; humans are still learning](/images/e-waste.jpg)

Code behaves similarly. When the time comes to reuse code, I like to think about this as an analogy. Code from a "good" codebase, when viewed at say 10% magnification, has a very obvious "appearance". It's not the same across the whole codebase though: controller code is short methods delegating work and rendering - you won't see much nesting. Repositories look like database accessors, inheriting most of their behavior. Views are mindless puppets mostly made up of template code.

![Different types of code appear different when you zoom out](/images/code.jpg)

In a "bad" codebase though, the same parts are there but the code has no specific appearance. All the "materials" the code is made from - models, repositories, controllers, views, helpers, services... - weave in and out with each other and are difficult to pry apart. Everything works great though until the company must react to change:

> Our traffic is 50% mobile! We need an app!

Hopefully at least some of your code can be reused for the smartphone app. But how much must be rewritten? Will you keep the existing code or support both desktop and mobile in the new code? Unless you've been diligently keeping code concerns separate - keeping your "materials" easily recyclable - you have a lot of work ahead and some code will get thrown away.

I've seen this in a complicated codebase. User interface controls designed to take up a physical region of a page on the desktop site had significant business logic in them. The business, faced with the need to support mobile devices, suddenly needed a mobile web UI, plus iOS and Android apps. That's a total of 3 new ways to reach the same information and do the same things, but they all needed new view code. With the business logic locked up in the desktop site's view code the company had to change. They were OK, but they learned the hard way.

So rather than trying to anticipate change, try to respect the "materials" your code is made from. Remember different code has different properties. If you keep them apart nicely you can recycle them. Put them together too tightly and you'll get an unrecyclable mess, only good for landfill. Be more like mother nature and _recycle!_
