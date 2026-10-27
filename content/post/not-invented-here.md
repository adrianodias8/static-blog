---
title: Not Invented Here (Yet) 🦀
description: I rewrote my static site generator. Then I didn't stop. A field report from somewhere inside the vibe-coding trenches.
dateFormatted: October 27th, 2026
---

![A terminal listing tools being rewritten](/assets/images/posts/not-invented-here.png)

So. Funny thing happened on the way to having a simple blog.

You may remember my first post, where I explained that I'd chosen static sites because I'm lazy—sorry, *efficient*—and didn't want to maintain anything. A reasonable position. A position I held for roughly as long as it took for the Tailwind build to break in a way the error message declined to explain.

Reader, I did not debug it. I rewrote the whole generator in Rust.

## 🧱 The Current Inventory

Here's the honest state of my "I just want a simple blog" project:

- **[Statico](https://github.com/adrianodias8/statico)** — a static site generator. Replaces Static by DevDojo. It builds this very page. ✅ Done, actually works, I'm using it right now.
- **berth** — a free, open-source take on OrbStack. Docker and Linux on Apple Silicon, straight onto Virtualization.framework. Because I looked at my container tooling and thought "how hard can it be." 🚧
- **[rustyphp](https://github.com/adrianodias8/rustyphp)** — a PHP engine. In Rust. I want you to sit with that one for a moment, because I certainly have. 🚧
- **[turboclaw](https://github.com/adrianodias8/turboclaw)** — my own flavour of AI coding agent, because apparently the ones that exist are someone else's. 🚧

I write Drupal and Laravel for a living. PHP has paid for every meal I have eaten in a decade. And here I am, at a terminal, implementing its engine. For fun. Voluntarily.

At some point "not invented here" stopped being a joke about other teams and became a description of my weekends.

## 🎤 In My Defence, DHH Started It

Here's where I'd like to shift some blame.

At Rails World 2026, DHH gave a keynote about how 37signals is building software now — there's a good [write-up over at Rustify](https://rustify.rs/articles/rails-world-2026-keynote-dhh-hey-rust-ai-agents). The short version, as I understood it through the haze of my own enthusiasm:

They've gone **"pencils down"** — meaning the normal workflow is no longer a human typing the implementation. A human decides what should exist, an agent writes it, the human reviews what came back.

He reckons Rust is unpleasant to read and write by hand, but that this matters a great deal less when a human isn't the one doing the typing. Meanwhile it's fast, which you get to keep forever.

They rewrote the HEY mail server core in Rust and reported something like 99% less CPU and 95% less memory. He was upfront that these are their own numbers from their own workload, so season to taste — but even if you halve it twice, that's still an absurd result.

And the number that really got me: around 150,000 lines of code in a single month, against a historical average of roughly 30,000 lines of production Ruby *per year*. The Rustify write-up is careful to point out that counting lines is a famously terrible way to measure productivity, which is true, and which I ignored instantly because it was telling me what I wanted to hear.

So. A man with considerably more credibility than me says the constraint has moved. Rewriting your tools is no longer obviously insane.

I took this as a personal licence. I don't think it was issued as one.

## 🫠 The Part Where I Admit I Might Be Losing It

Let me be honest about the other side of this, because the post would be a lie otherwise.

There's a specific feeling when an agent hands you 2,000 lines of working Rust in a language whose borrow checker you've argued with maybe twice. It passes. The tests are green. The benchmarks are genuinely good.

And a small voice asks: *do you understand this?*

Sometimes yes. Sometimes I understand it the way you understand a city you've only seen from a train. I know the shape. I could not give directions.

I keep catching myself in a loop that goes:

1. Notice minor annoyance in existing tool.
2. Think "I could rewrite this."
3. **Actually rewrite it**, because now that's a Tuesday evening rather than a six-month project.
4. Now maintain it. Forever. Alone.

Step four is doing a tremendous amount of silent work there. Statico is lovely right now because I wrote it last week. Ask me about maintaining it in two years when someone files a genuinely good bug report about a Tailwind v5 edge case I've never heard of.

The honest summary: I cannot currently tell whether I'm being unusually productive or unusually unhinged. The outputs look identical from inside.

## 🏄 Until Then: Vibe Code Everything

So here's where I've landed, and I accept it is not a rigorous position:

I'm going to keep going. Full send. Vibe code everything.

Partly because it's the most fun I've had programming in years, and I think that counts for more than people admit. Partly because the tools I've ended up with are genuinely better *for me* — Statico does exactly what I want, has no Node in it, and builds this site in under a second, because it was built by someone with a sample size of one user and strong opinions about that user.

And partly because if the constraint really has moved, the people who find out first will be the ones who went and poked it.

I'll reassess when something catches fire. It'll be fine. Probably. 🦀

## 🔮 Next: Local Models, and a Very Expensive Laptop

Which brings me to the next thing I'm going to be insufferable about.

I've been dabbling with running models locally, and so far it's been equal parts "oh, that's genuinely useful" and "why is this eating my entire machine." Both of these problems may be solved by throwing money at them, which is my favourite kind of problem.

A MacBook Pro M5 Max with 128GB of unified memory arrives later this week. 🎉

That is an amount of RAM that would have run a small hosting company, and I intend to spend it asking local models to write Rust I will then nod at knowingly.

I'm planning to write up what I actually find, honestly — which models are genuinely usable at that memory, what the speeds really look like rather than what the benchmarks claim, and whether local models are good enough yet to do the sort of work I've been handing to the cloud. Including the bits that don't work, because those posts are more useful and nobody writes them.

Assuming the laptop arrives, and assuming I haven't started rewriting macOS by then.

Stay tuned for more rambling!
