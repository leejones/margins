# Notes from watching "Rewriting Code and Culture"

* source: https://rubyconf.eventer.com/rubyconf-australia-2015-1223/rewriting-code-and-culture-by-sabrina-leandro-1730
* tags: culture, agile, soap, services, rails, monolith, iteration, continuous delivery, transformation

## Background

> This is the story of a company that survived a much needed transformation of its product and codebase, but most importantly, of its culture. There's no real prescription for being agile. It's about the journey a team takes to discover how to best work together and deliver great products.

> In this presentation, I'll share a candid view of a team trying to overcome a slow product development process. How we refactored our way out of badly coupled code, moved to continuous deployment, and greatly improved our approach to product and software development.

songkick has been around since 2009. Over time it was taking longer and longer to release new features.

These lessons are from what they've learned since the decision to switch to SOA around 3 years ago.

1. know your product - songkick: helping fans around the world go to more concerts
2. know your domain model

> If you don't design your data model, having a service oriented architecture will only break up your code and add latency to it.

### Where to start?

> Start where it hurts the most. That is, where the impact of changes will be seen sooner.

songkick.com was a single Rails app.
Created Ruby service classes inside the existing Rails app.
Weren't trying to change everything at the same time.

## One main goal for the rewrite project

> Have one specific goal for your rewrite project.

Their one main goal at the time:

> Build a new, simplified web app based on core iPhone features so that we can improve the *immediate velocity roadblocks* and move onto building quickly on top of this core foundation.

Improving velocity was the main goal of the rewrite project. Allowed them to focus and reject unrelated changes.

Trying to fix all the things at once will hinder progress.

Whatch out for "this time we'll get everything right".

> Know when it ends
> * define project scope
> * have a clear deadline
> * weekly checkpoints
> * no new features

* they decided what features of the website they wanted to keep (aka rewrite)
* estimated how long it would take
* realized it would take more time than they could afford
* went back and removed features
* evaluated the project weekly
* removed and simplified more features

No new features...

> Until we finished, it was either rewriting or deleting.

Learn to iterate

> Validate your assumptions
> * Changes in master
> * Release incrementally
> * Improve your release process

Instead of starting a new project, they iterated on the existing project while continuously merging to master and releasing incrementally.

It took some time, but they moved closer and closer toward Continuous Delivery.

Gave developers enough context and increased their responsibilities for testing their own code.

## Front-end Architecture

Process started by taking he most popular pages and for each page developers, designers, and product owners:

* defined a name for the page
* defined all of its components (a discrete module of functionality on the page that function independent of other components)
* removed or simplified unused or complex features on that page

Defining a shared language for the components allowed developers, designers, and product managers to more easily communicate. If someone reports a bug in the "event brief" component, the code related to that is likely also named something related event brief.

Simplified controllers by creating a PageModel for each page. Created component classes for each component on that page.

> DRY is for domain models. Duplication in front-end code is okay.

They often made components specific to a single page. Only reused components on multiple pages if they were used exactly the same in all the pages. They avoided conditionals in components. Having discrete components reduced the number presentations bugs significantly.

> Fast release cycle = fast build

The original test suite took hours to run (even when parallelized). They deleted or rewrote the tests so that the most important features were covered by integration tests and the rest were deleted or rewritten as unit tests.

> A slow build discourages refactoring.

Having a fast test suite gives confidence when doing refactoring.

Make the cost of making a small change small.

Tracked error rates daily and followed up on errors quickly.

## First step toward SOA

Moved all ActiveRecord access behind a Services class. Allowed them to get the service interfaces right while everything was still in the same codebase.

## Rewriting Culture

Release frequency increased as well as happiness.

Collaboration between developers, designers, and product managers builds shared understanding. Developers can suggest simpler solutions. Designers and product managers have a better understanding of the cost and tradeoffs involved.

The collaboration helped the rewrite process go faster.

Moved away from product and design iterating for a long time before handing off to developers ("here build this"). Instead, they fostered close collaboration from the start. Clearly defined what we are building and why in kick-off meetings with everyone that will be involved (developers, designers, tests, product owners).

Designers and developers pair with each other instead of communicating with PSD files.

> The browser becomes the artboard.

Collaboration leads to happiness and more.

> Learn to collaborate and work in a multidisciplinary team. The make for happier teams, better, products, and can even improve your code's quality.
