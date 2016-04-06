# Should a customer pay for bugfixes?

Whether or not you agree with the basic premise of this article, I'm sure you'll be able to agree that any software project of a reasonable size will have bugs. The way these bugs are dealt with can often become an obstacle to forming a healthy relationship with the customer, and can even impede the software development process itself. There's many ways to approach this issue, and I'm going to start with a common one.

### "We paid for a feature. The feature has bugs. Why should we pay again for bugfixes?"

Many moons ago (at the first software company I worked at), if a customer came to us with a buggy feature, we would fix that feature free of charge. Customers liked this because they received the features that they had asked for, and everyone went on their merry way. The flipside to this was that features were defined in 50+ page specifications that would take days of meetings to draft. If the customer was expecting a feature that was not on the specification, the company would charge to add this new feature. Once, the specification dictated that the user should be able to "add events". The customer was obviously expecting that the app would allow for editing and removing these events, but as the functionality was not on the spec, they had to pay for it.

That was obviously an extreme scenario, but when there is no trust between you and your customer, that's what ends up happening; it comes down to quibbling about the verbiage of specifications or support agreements. Of course, at that company, the conversations around whether or not something was covered by the specification were billable. The customer ended up paying a lot more than if we had simply charged for the time required to fix the bug.

### "This feature is not what we asked for. Why should we pay for something that you failed to understand?"

This is where the conversation around "bugs" really opens up. To what extent can we consider a feature which is working correctly a bug? If there was a miscommunication, or something was not adequately described, or we took something for granted, or they took something for granted, or the full complexities of a feature weren't investigated in the planning phase, should the customer have to pay? In a perfect world, this would be judged on a case-by-case basis, by a neutral third party with no stake in either outcome. Of course, this is never going to happen, and in the past I've seen conversations about "the reasonable assumptions that someone should be able to draw from a passage of text in an email" stretch out of long periods of time.

Conversations like these can cause a breakdown of the relationship with the customer. When naming something a "bug" means that it's free, the customer has a vested interest in naming as many things as possible "bugs", even if the "bug" is simply functionality that was glossed over, implied, or taken for granted in planning. These conversations take a long time to have, and they are rarely productive for either party. They slow things down.

### "This functionality was working fine, but is no longer working. Why should we pay for you to fix your own 'code rot'?"

Sometimes, features that *were* fine mysteriously stop working. Third-party APIs change. Infrastructure stops running smoothly. Regressions. Why should the customer have to pay for unforeseen problems with the continuing health of the app? Much like how the Golden Gate Bridge needs to be repeatedly repainted, apps need maintenance and support to keep running. If there has to be a conversation with the client around the nature of an issue and who should pay for it, especially while the app is not functioning as it should, this again indicates a real problem in the relationship. Also, this is kind of what support agreements are for.

### So what's the solution?

At Made Tech, we bill for all of our time. We usually have an agreed-upon amount of time dedicated to a sprint, and then an additional ongoing support budget if necessary. Our plan is always to wow the customer so much with our initial sprint that any misgivings about having bugs paid for in sprint time disappear. When we don't have to have any of the conversations I've listed above, we can get everything done much faster, and trust grows. Any miscommunications around what a feature should have been are resolved with both parties working towards a solution, rather than pointing fingers; issues are figured out much more quickly when everyone's on the same page. We pride ourselves on the fact that our customers trust us to get on with the job. Our test suites are sound, and we have frequent, open communication with product owners, so true bugs are rare to begin with. When they do appear, they are treated as a natural part of the software development process. Which they are.