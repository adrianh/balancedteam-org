---
author: ianmcfarland
category:
  - techniques
date: "2011-04-01T01:54:11+00:00"
guid: https://balancedteam.org/?p=249
tag:
  - agile
  - documentation
  - ian-mcfarland
  - just-enough-design
title: DRY Design Documentation
url: /2011/04/01/dry-design-documentation/

---
(Reprinted from [Ian's blog at Pivotal Labs](http://pivotallabs.com/users/ian/blog/articles/1577-dry-design-documentation).)

I believe it was in a conversation with Janice Fraser that I first started talking about DRY Documentation. It was certainly she (among others) who goaded me into actually writing this blog post. So I'm taking a moment on my WiFi-free (and generally amenity-free) United Airlines flight to SXSW to put pixel to screen.

DRYness is an age-old concept in the Agile space (to the extent that that's possible in a space that's only 10 years old itself) and it's elegant in its simplicity. DRY simply stands for Don't Repeat Yourself. The idea is that you should only do any one thing in code in only one place. If, for example, you are doing an interest rate calculation, don't copy and paste the code from one place where you need it to another: instead, move that responsibility to an object that reasonably should be responsible for such things, and do that interest rate calculation only in that one place. The reasons for this being important are manifold, but perhaps the canonical reason is so that it's easy to change: When the interest rate calculation changes, you don't have to go digging through your code to find all the places you do it, and make sure you change them all consistently. Instead, you change the code in only one place.

Hopefully this is old hat for most coders now, and hopefully you, gentle reader, will forgive me my oversimplifcations and conflations. The point is one of simplicity.

So now, let's shift focus to design documentation. The idea I'm trying to express when I talk about DRY documentation is one again of simplicity, though the drivers are perhaps a little different.

The mental model for truly DRY documentation is one in which every pixel on the page tells you something you didn't know before. Of course, like DRY code, it's worth being pragmatic. There are times when greater clarity can be gained by a certain amount of contextual restatement. But as a theoretical goal state, it's still quite useful to picture a body of documentation in which every last line tells you something you needed to know about what you're trying to build, and something you didn't know from looking at any other line in the documentation.

What would we notice about a set of documentation that adhered to these principles? Well, first, and most obviously, it would probably be a lot shorter than the documentation we're used to seeing. And that in itself is a benefit. Why? For a number of reasons. First, shorter documentation is in general easier to digest, and it's generally easier to find the relevant bit of documentation in a shorter corpus, all else being equal. (And of course, document structure and readability play just as big a role in a short document as they do in a longer one.)

Shorter documents are also easier to revise and maintain. And it's easier to find changes between versions, all else being equal. I talk sometimes about the 500 page PRD we got when we were developing one product, complete with two sets of revisions, also 500 pages each. Guess how easy it was for the developer to find the 2% of information that changed in each revision, and understand its implications to for the site? Guess how easy it was for the designer to be sure she'd changed everything consistently? In a DRY design doc, changes are more obvious, and more meaningful. Things jump out when they're inconsistent. And they tend to be more consistent, because the designs implied are applied more consistently across the product in question.

This brings me to another favorite topic: Principled design. DRY documentation is a lot easier to develop (and it's a lot easier to tell when your documentation is DRY) when your design is motivated by specific principles. For instance, when you decide, in the banking app you're designing, that all checking account features will use Cerulean Blue for their accent color, and all savings account features will use Prussian Blue, a lot of nice things happen. First, design questions become much easier to answer. The new Maximizer Account we've just added is a kind of savings account. Great! We know it's going to be Prussian Blue. (Or we can make a better informed decision that there should be a new point in the color family.) Second, it suddenly becomes a lot easier to document this fact. A one page style bible can capture this information, and when some new feature is implemented, it doesn't take any intervention from the VxD to make sure the new bits have the right color choices. Third, when some new feature comes along, developers roughing it out can come up with a reasonable early approximation of what it should look like, because they have principles to apply, instead of PSDs to pore over, looking for a non-existent visual treatment for the new thing they're just embarking on. This lets said VxD (and the IA) spend time tuning something that's close, rather than restating the design principles they've got in their heads, in the form of some new PSD file.

A fourth virtue is that suddenly all these color choices (or typography choices, or IxD choices,) have consistency, a consistency that our dear End User can actually pick up on. They don't end up feeling lost in a jumble of pretty colors, but start to associate the Prussian Blue with savings accounts, the Cerulean Blue with checking accounts, and, assuming the designer goes in this direction, that blue in general means cash accounts; green, stock and security accounts; reds and oranges, loans and credit accounts, or similar.

They may not be able to articulate why they know this, but they will perceive a solidity and purpose in the VxD, one that makes them feel safe and comfortable, and one that helps them use the application more effectively.

When coupled with a good domain model and a good information architecture, it suddenly gets a lot easier for the whole team to keep the design princples top of mind, and answer basic questions without having to consult a 500 page document, or even a 20-30 page set of wireframes and interaction designs. Hopefully they can answer most questions from a one or two page style bible, and by consulting the wireframe describing their grid system, and the one for the kind of module they're working on.

Again, the point is not to pursue this ideal to an absurdist end, but rather to continually ask oneself: Could this documentation be simpler? Did I cover this already? Could an existing design concept apply to the new area I'm covering? Restatement in the service of clarity is always to be lauded. Unfortunately, in practice, most restatement in the form of long design documents is just waste: Waste in that the documentation must be produced; that it must be maintained; that it must be read; that it must be understood; and waste in that it tends to obscure the princples of the design in favor of the surface of the design.

And of course, another agile principle comes into play: Refactoring. Often a second use of a given design treatment exposes new boundary cases and new pressures on the design, and the initial design needs to be modified slightly to accommodate both the new and the old use case. This is usually a simplfying force, and one not to be resisted. Let the documentation live, and reflect the deeper underlying principles of the design you're trying to express. Applied well, this rigor will help you to simplify and clarify your designs, and expose their essence.

When practiced well, DRY documentation will set you free, give you control and clarity, and communicate your design vision efficiently and clearly. It will also free your development team to do things more or less right the first time, and give them more time to work on the bits that need more love and attention.
