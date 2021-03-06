## Talent measurement failure

_Thursday, December 17th 2015_

### Preface
![](https://habrastorage.org/getpro/habr/post_images/400/f8e/3e1/400f8e3e117ded138615d0346677d80d.jpg)

How often have you thought about change your current job, during last few years? Chances are that sometimes, when you get involved into recruitment process, you have to deal with services, so called "talent measurement" and destined to evaluate your ability for one or another job. Whether it be [Codility](https://codility.com/) or [CEB](https://www.cebglobal.com/), they aim a common goal - check your skills in one professional domain or another. Do they accomplish their mission, if so, how good they are, doing it?

### Time is money, nothing personal
The most part of such tests/exercises are roughly timeboxed. I don't know how about you, but regarding me, I hate stress situations, the more stress pressure is, the more my brain freezes. I've never made the competitive programming before, the only thing that I've made against the clock where few cool hackathons in relaxed atmosphere. I'm asking myself why we need time-critical tests/exercises? To check if we're able to piss out some amount of smell code, regarding pointless subject, in delimited amount of time? I don't try to say that the time is worthless, it's important, it's money if you prefer. Upon different scientific studies, the time as a factor of pressure would have not nearly positive influence to developers.

### Format
I don't even remember how many times I faced tests that have contained misprints or awfully compressed images. More and more often I meet measure services that display their questions as images, may be trying avoid some sort of copy/pasting. If you are looking make correct answer to a questions of the test, first, you should be able understand this question. How can you understand it if you have to waste a lot of time trying to decrypt the captcha surging up to your sight.

### The idiocy is getting stronger
In this section I would like demonstrate you few examples of a flagrant negligence, introduced by [CEB](https://www.cebglobal.com/) in their online tests. It is worth noting that, all demonstrated kludges are not characteristic for one particular measurement service. In my practice I've met a lot of such flubs. For example, let's take a look at CEB's _javascript_ test. Approximately in the middle of the test I met a question about conditional _try/catch_. Just check this beauty out:

![](https://habrastorage.org/getpro/habr/post_images/b2f/4ca/a8c/b2f4caa8cdf872d32b1abfd5155cd2d9.png)

Let's see what MDN [says](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try%E2%80%A6%E2%80%8Bcatch) about it:

![](https://habrastorage.org/getpro/habr/post_images/080/263/4e2/0802634e20aa76ee4719592a0c16886a.png)

Next silly question, that I've met, was about _expression closures_ in _javascript_. You don't know what is it? How dare you? Look and learn:

![](https://habrastorage.org/getpro/habr/post_images/739/d5f/2a5/739d5f2a5c0f65313511cd5cbf885706.png)

The MDN has a different [opinion](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Expression_closures):

![](https://habrastorage.org/getpro/habr/post_images/8f8/90f/4ac/8f890f4ac314c77a5476c234016a9187.png)

Just a nonsense about classes. Because of this question, I've lost great lot of time, I read it, at least, 5 times. Even after reading I was unable to understand what's a point. Normally, the ES6/ES2015 standard was finalized in June 2015, but there is only partial implementations of this standard available in _V8_ or _SpiderMonkey_ engines. Before this standard the notion of class was unavailable in _javascript_. But, could anybody tell me what means **prototypical**(it was the right answer) type of class in _javascript_? Furthermore, because of two previous silly questions I was a bit lost. That's a question:

![](https://habrastorage.org/getpro/habr/post_images/c78/cb6/56e/c78cb656e9904042e7f34df83f40bbf8.png)

Let's take a loot at MDN's [explanations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes):

![](https://habrastorage.org/getpro/habr/post_images/89a/b6f/391/89ab6f391f5bf1223abb5c819244426e.png)

For the last question I've not kept the screenshot, unfortunately. It has contained, approximately, following text: "What's the purpose of **escape** function", with a variety of potential answers. According MDN this function is completely [out of date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/escape):

![](https://habrastorage.org/getpro/habr/post_images/d5b/f86/055/d5bf86055e2506c1af9907bc66e8701e.png)

### Summary

Personally, I think that the most part of, so-called, services of talent measurement, are counterproductive for employers and time-consuming and simply wasteful for potential candidates. During my career, I was on both sides of the fence. In my opinion, a quick phone chat, technical exercise and following consideration of results of such exercise can be much more fruitful and productive.