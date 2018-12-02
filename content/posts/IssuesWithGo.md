---
title: "My Issues With Go"
date: 2018-11-12T15:55:32-06:00
draft: true
---

![Ugly go code snippet](/imgs/a.png)

Look at this code snippet! Go has no exceptions and it leads to a very ugly style of programming.
Go lacks immutables, exceptions, inheritance, generics. Its dependency management is a mess (no versioning support), it has a really annoying compile [error](https://corte.si/posts/code/go/go-rant.html) when you have an unused import, and GOPATH takes some getting use to. But by and large Go has been a successful language and I think it is because it makes big promises of concurrency at scale. Callback functions are more readable and enable concurrency in languages like JS, and some goroutine patterns can get quite complex .


Also this [article](http://nomad.uk.net/articles/why-gos-design-is-a-disservice-to-intelligent-programmers.html)
>The key point here is our programmers are Googlers, they’re not researchers. They’re typically, fairly young, fresh out of school, probably learned Java, maybe learned C or C++, probably learned Python. They’re not capable of understanding a brilliant language but we want to use them to build good software. So, the language that we give them has to be easy for them to understand and easy to adopt. – Rob Pike 1


I came across [this](http://tmikov.blogspot.com/2015/02/you-dont-like-googles-go-because-you.html) post that harps on the hubris behind the design of Go . The lack of the inline '?:' operator, the lack of a max function, inability to overload functions, boiler plate code, no collections, and numerous other shortcomings, are all things this author points out ! These aforementioned items are all frustrating, but when it comes to creating servers, networking, and maaaybe web applications, Go could be useful . Though Go failed to replace C++ at Google, it has gained adoption and support! I have taken a liking to C++ recently as I have been doing many coding problems and started a project creating a Raytracer in C++ from scratch.
