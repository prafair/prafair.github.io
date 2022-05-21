---
layout: post
title:  ⏳ Dynamic environments for E2E tests
date:   2022-05-13 17:46:01 +0300
categories: articles
---
When embedding autotests into a pipeline, the question often arises, on which particular instance (bench, website, circuit, etc.) will our autotests be run. As an option, use static instances, but this approach has its drawbacks, for example, problems with test data, performance, etc. <br>

To avoid problems with this, ephemeral or dynamic environments were invented. As a result, when implementing this approach, we get a more stable environment for running tests, parallelization into several environments, cost savings, etc. <br>

The implementation depends on the application itself. If your application is already somehow deployed in the cloud using the "infrastructure as code" approach, then in principle there should be no big problems. <br>


About the problems of static environments: <https://pipelinedriven.org/article/the-four-biggest-issues-with-having-static-environments> <br>

More details about this approach: <br>
<https://ephemeralenvironments.io/> <br>
<https://pipelinedriven.org/article/ephemeral-environment-why-what-how-and-where>