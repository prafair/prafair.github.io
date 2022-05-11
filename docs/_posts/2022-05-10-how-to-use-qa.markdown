---
layout: post
title:  How to properly (not) use testers
date:   2022-05-10 15:09:02 +0300
categories: articles
---
<https://habr.com/ru/company/jugru/blog/661623/> <br>

Recently I came across a text article from the creator of Allure Report, I watched this report in the record. <br>

Main Points: <br>

- Autotests are written in native languages ​​in the same repository. <br>
- Tests run on build. <br>
- Automation is higher than documentation: we do not need manual descriptions, they quickly become outdated. <br>
- Cross-functional teams: people know how to write code and fix the framework, development is interested in testing, and so on. <br>
- Shared infrastructure: testers are also responsible for the test environment. <br>

Yes, in general, it's cool if there is such a team and everything works like clockwork. <br>
Most likely, the main problem will be writing native tests in one repository, as well as running autotests for each PR (MR). This is not done at the snap of a finger, it requires the efforts of the whole team.
If you are using Allure Report / Allure TestOps, then in fact you already get live documentation. There are no particular problems with this. <br>
Team development is, in principle, one of the important areas, here you need to instill good practices from the very beginning, undergo training, just learn from colleagues or other people. <br>


❓ And a question to everyone, have you heard about this approach at all? Or maybe you are already trying to get closer to the ideal team?😊 

_________________
Original post in Telegram  <https://t.me/qa_relia/50>
