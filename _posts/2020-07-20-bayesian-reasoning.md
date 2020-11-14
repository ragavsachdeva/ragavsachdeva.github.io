---
layout: post
title:  Bayesian Reasoning
date: 2020-07-20
comments: True
description: Let me start by painting a picture. You wake up one fine morning feeling a bit sick. If you’re like me, you’d normally ignore it – hoping that you’ll get better soon enough. However, it’s 2020 and everything is unreal, so you decide to ...
---

Let me start by painting a picture. You wake up one fine morning feeling a bit sick. If you’re like me, you’d normally ignore it – hoping that you’ll get better soon enough. However, [it’s 2020 and everything is unreal](https://en.wikipedia.org/wiki/2020){:target="\_blank"}, so you decide to pay the doctor a visit (y’know, just in case). The doctor isn’t quite sure what’s wrong with you either and runs an assortment of tests. To your dismay, it turns out you tested positive for a very rare and deleterious condition called _Disease X_ ([of course it had to be ‘X’](https://www.psychologytoday.com/au/blog/evolution-the-self/201603/whats-so-fascinating-about-the-letter-x){:target="\_blank"}). You are absolutely devastated; I didn’t say I’d paint a _pretty_ picture, did I?

You start to consider yourself “the unluckiest person in the world”. I mean, Disease X is so rare, what are the odds of you contracting it?

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0" style="text-align: center">
        <img class="img-fluid rounded" src="{{ site.baseurl }}/assets/img/posts/2020-07-20-bayesian-reasoning/1.svg">
    </div>
</div>

Okay, so maybe you’re not the unluckiest person in _the_ world but still very, very unfortunate. You pinch yourself in order to wake up from this frightening nightmare but alas, it is all too real. You ask the doctor how reliable these results are and find out that this test is accurate $$99.9\%$$ of the time (i.e. the test comes back positive for $$99.9\%$$ of the people who have the disease and incorrectly comes back positive for $$0.01\%$$ of the people who don’t have the disease). As you hear this, your eyes light up with hope!

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0" style="text-align: center">
        <img class="img-fluid rounded" src="{{ site.baseurl }}/assets/img/posts/2020-07-20-bayesian-reasoning/2.svg">
    </div>
</div>

Believe it or not, in this picture of yours that I’m painting, you’re a lot smarter than you give yourself credit for. In that brief moment when you heard those numbers, you did some crazy maths in your head and realised that the probability of you actually having Disease X is not $$99.9\%$$. In fact, it is much, much lower.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0" style="text-align: center">
        <img class="img-fluid rounded" src="{{ site.baseurl }}/assets/img/posts/2020-07-20-bayesian-reasoning/3.svg">
    </div>
</div>


It’s because the you in my narrative knows about this beautiful formula called Bayes’ Theorem. Now, rather than me shoving this Bayes’ rule down your throat and asking you to trust me that it’s true, let’s try to establish a line of reasoning that may help you see why the likelihood that you have Disease X is actually much lower than $$99.9\%$$.

Imagine there are $$2,000,000$$ people (including you) and we’d like to find out who amongst them have Disease X. In the light of this, all $$2M$$ people take the test. We know the test correctly identifies $$99.9\%$$ of the people who have the disease (say, $$n$$ people actually have the disease) i.e. it will correctly identify $$0.999 \times n$$ people. On the other hand, the test incorrectly flags $$0.01\%$$ of the people who do not have the disease i.e. $$0.0001 \times (2,000,000 - n)$$ people who do not have the disease would be incorrectly tested positive.

Now, remember when your doctor said that the odds of contracting Disease X are one in a million? Working under this assumption, let’s say only $$2$$ out of these $$2,000,000$$ people actually have Disease X i.e. $$n=2$$. Now, the test will correctly identify $$0.999 \times 2 \approx 2$$ people. In other words, we can rest assured that both the people who have Disease X will very likely be tested positive. However, $$0.0001 \times (2,000,000 - 2) \approx 200$$ people would be falsely flagged as positives. Ergo, in total $$202$$ people out of $$2,000,000$$ would be tested positive. If you happened to be one of these $$202$$ people, what are the chances that you actually have Disease X? Bingo! It’s $$2$$ in $$202$$ or $$1$$ in $$101$$ ($$\approx 0.99\%$$) i.e. less than $$1\%$$. No wonder your eyes lit up.

If this is the first time you’ve encountered such a line of reasoning, it may seem very counterintuitive and you might argue

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0" style="text-align: center">
        <img class="img-fluid rounded" src="{{ site.baseurl }}/assets/img/posts/2020-07-20-bayesian-reasoning/4.svg">
    </div>
</div>


and you could almost be forgiven for believing that. However, consider this – before you took the test, the odds that you had Disease X were $$1$$ in $$1,000,000$$ i.e. $$0.0001\%$$. After you got back a positive test, your new odds (that we calculated above) were nearly $$1\%$$. In other words your chances of having the disease shot up by a factor of $$10,000$$ (from $$0.0001\%$$ to $$1\%$$). Therefore, it is not unreasonable to believe you are more likely to have the disease; it’s just that the odds are not as severe as you may think.

The biggest takeaway here is: **The manifestation of some sort of evidence does not completely determine new beliefs but rather it updates prior beliefs**. In the scenario above, your prior belief would have been “as a random person, the chances of you having contracted Disease X are $$1$$ in $$1,000,000$$”. With the revelation of new evidence (testing positive for the test), your belief would get updated to “given that you tested positive for the disease, the chances of you having it are now $$1$$ in $$101$$”. This is exactly the intuition behind Bayes’ theorem and if you deliberate over it, it’s not just a mere mathematical rule but a whole paradigm of thought.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0" style="text-align: center">
        <img class="img-fluid rounded" src="{{ site.baseurl }}/assets/img/posts/2020-07-20-bayesian-reasoning/5.svg">
    </div>
</div>


If you still have trouble digesting it, I have another hyperbole for you. Imagine if the doctor told you, “Hey, I don’t mean to alarm you but you tested positive for the [Heart Virus](https://dragonball.fandom.com/wiki/Heart_Virus){:target="\_blank"}. The test results are $$99.999999\%$$ reliable”. Even if you didn’t know anything about Bayes’ theorem, there is no way you’d actually believe that you have the Heart Virus (mainly because it’s a fictional disease and this isn’t Dragon Ball Z). But the test came back positive and it is $$99.999999\%$$ accurate? Shouldn’t you be a bit worried? Well, no matter how accurate the evidence is, since your prior belief tells you that the probability of you actually having the Heart Virus is $$0\%$$ (considering it is not even a real disease), nothing can convince you otherwise (and rightfully so).

Bayesian reasoning is such a powerful concept and we [intuitively tend to use it in our everyday lives without realising it](https://www.abc.net.au/news/science/2018-09-19/bayes-theorem-probability-luck-explained/10243134){:target="\_blank"}. Ironically, however, when you introduce numbers into the mix, most people tend to either get disproportionately influenced by them or misinterpret their implication.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0" style="text-align: center">
        <img class="img-fluid rounded" src="{{ site.baseurl }}/assets/img/posts/2020-07-20-bayesian-reasoning/6.svg">
    </div>
</div>

As a matter of fact, I already have. The calculations that we did above to compute probability of you having Disease X given that you tested positive implicitly made use of the Bayes’ Theorem. All that’s left is to establish some notations. I highly recommend watching [this video by 3Blue1Brown](https://www.youtube.com/watch?v=HZGCoVF3YvM){:target="\_blank"} if you're interested in learning more.

Until next time!