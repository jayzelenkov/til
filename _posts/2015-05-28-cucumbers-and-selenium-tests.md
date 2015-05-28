---
title: Cucumbers and Selenium tests
tags: [JavaScript, "Selenium-WebDriver"]
description: Another framework to run Selenium tests.
---

Selenium-WebDriver offers low-level API to run tests in real browsers. Developers are lazy and don't want to write low-level tests. There are dozens of frameworks that wrap low-level ugly-looking Selenium calls and expose nice public API. Examples include [wd][wd] for javascript and [capybara][capybara] for ruby.

There is one more contender on the ring! It is [robot framework][robot_framework]. Just like other frameworks it exposes a set of nice high-level APIs to access core Selenium functions. Robot's main difference is [Gherkin DSL][gherkin] support out of the box. It makes sense to write cucumber-style tests for the browser.

Robot's development is sponsored by Nokia Networks so it is unlikely to be abandoned any time soon.

Robot is not new. I just happened to discover it recently.


[cucumber]: https://cucumber.io
[gherkin]: https://github.com/cucumber/cucumber/wiki/Gherkin
[wd]: https://github.com/admc/wd
[capybara]: http://jnicklas.github.io/capybara/
[robot_framework]: http://robotframework.org
