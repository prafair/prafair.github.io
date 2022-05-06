---
layout: post
title:  Preparing an application for test automation
date:   2022-03-10 12:14:00 +0300
categories: automation application habr
---
One of the key success factors for automation is application testability. Testability makes autotests easier and faster to write. For example, for an API, these are public methods, and for a UI, this is an HTML page.

0. **Application ready**
It happens that they automate too early, and as a result, then they are engaged in rewriting. Ask questions as early as possible, whether the main pages are ready for automation, whether it is advisable to take it to work, whether the logic or layout will change the next day, etc.

1. **Availability of documentation**
Documentation helps you quickly find the information you need, for example, to create test data via the API. Swagger and Storybook make it easy to document API and UI components, respectively.

Based on the specifications, you can [generate](https://habr.com/ru/company/jugru/blog/525298/) tests. Using the Storybook, you can find out the desired state of the component and its purpose.

Also, based on the documentation, you can build coverage with autotests, as described in the example of the [swagger-coverage](https://habr.com/ru/company/jugru/blog/491844) tool.

2. **Arranging data-* attributes**
Reliable locators are needed to reduce the number of falling tests if the frontend changes, and to conveniently locate elements in the DOM.

Less susceptible to change are data-* attributes, such as data-test="element".

Not so long ago, at the Heisenbug conference, in the report ["How Testid-strategy defeated PageObject and BDD / Cucumber monsters"](https://www.youtube.com/watch?v=w5EgCZgj5yE), it was told about the advantage of this approach in conjunction with the Allure Report.

You can use other locators if they exist. Priority can be viewed in the [Testing Library](https://testing-library.com/docs/queries/about/#priority). First of all, we consider locators close to the user. Immediately a bonus to those who follow the accessibility of the product.

3. **If possible, turn off animations for the duration of the run**
When running autotests, there is often a problem with animations that interfere with clicks and other actions.

It's good practice to disable these animations entirely if possible.

4. **Parallel launch**
As the number of autotests grows, one way to reduce runtime is through parallelization. You can parallelize in many ways, for example, through streams or parallel jobs. You need to be careful when running in parallel, you need to make sure that the application does not crash and that there are no slowdowns or unexpected errors.

5. **Third-party dependencies**
Various third-party dependencies can be found on architectural diagrams or other documentation. It is difficult to control them, so it is problematic to adjust them for tests.

For example, for a third-party API, you can use [Wiremock](https://wiremock.org/) or [MockWebServer](https://github.com/square/okhttp/tree/master/mockwebserver) as a mock server. Thus, autotests will be more stable.

6. **Logs**
Logs are our assistants in the analysis and analysis of the results of autotests after the run. Dealing with the causes of falls becomes easier.

The application should have clear and accessible logs, ideally in one place and be able to attach them to a specific test.

Some frameworks allow you to attach logs from different sources to the autotest. Such sources can be information from the browser console or information from the server.

7. **Application response time**
At the global level, a timeout is usually set for all waits in tests. It can be calculated experimentally.

The response time should not exceed the specified timeout, otherwise the tests will constantly fall and you need to constantly deal with them.

The best solution here would be a discussion about improving performance, perhaps there are some problems and need to be solved.

**Conclusion**
Based on the above tips, you can facilitate the automation of application testing.

_________________
Original post in Habr (Russian) - <https://habr.com/ru/post/654959/>
