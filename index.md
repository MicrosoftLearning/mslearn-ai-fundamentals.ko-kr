---
title: Microsoft Learn - Azure의 AI 소개 연습
permalink: index.html
layout: home
---

# AI-900: Azure 연습의 AI 소개

이러한 실습 연습은 [Microsoft Learn](https://docs.microsoft.com/training/)의 교육 콘텐츠를 지원하도록 설계되었습니다.

이 연습을 완료하려면 Microsoft Azure 구독이 필요합니다. [https://azure.microsoft.com](https://azure.microsoft.com)에서 무료 평가판에 등록할 수 있습니다.

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Exercises'" %}
| 연습 |
| ------- | 
{% for activity in labs  %}| [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
