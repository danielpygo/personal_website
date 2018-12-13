---
title: "My Issues With Go"
date: 2018-10-23T15:55:32-06:00
draft: false
---

![Ugly go code snippet](/imgs/a.png)

Look at this code snippet! This is pretty standard actually. Go has no exceptions and it leads to a very ugly style of programming sometimes.
Go also lacks immutables, inheritance and generics. Its dependency management is a mess (no versioning support, yes really), it has a really annoying compile time [error](https://corte.si/posts/code/go/go-rant.html) when you have an unused import, and GOPATH takes some getting use to. But by and large Go has been a successful language and I think it is because it makes grandiose promises of concurrency. These aforementioned items are all frustrating, but when it comes to creating servers, networking, and web applications, Go is very useful.

Also this [article](http://nomad.uk.net/articles/why-gos-design-is-a-disservice-to-intelligent-programmers.html)


*The key point here is our programmers are Googlers, they’re not researchers. They’re typically, fairly young, fresh out of school, probably learned Java, maybe learned C or C++, probably learned Python. They’re not capable of understanding a brilliant language but we want to use them to build good software. So, the language that we give them has to be easy for them to understand and easy to adopt. – Rob Pike 1*

I mean how condescending and out of touch does he sound? C++ is taught in schools and young, hungry developers, especially the ones at Google, are totally able to wrap their brain around C++ .

I came across [this](http://tmikov.blogspot.com/2015/02/you-dont-like-googles-go-because-you.html) post that harps on the hubris behind the design of Go . The lack of the inline '?:' operator, inability to overload functions, boiler plate code, no collections, and numerous other shortcomings, are all things this author points out !


But this whole discussion about Go really begs the question: Would Go have been successful without Google?


With any tool, it is important to research disadvantages, issues and shortcomings. A lot of Go programmers I think get caught up in this though "At first I was confused by X, but actually it is genius!!" trap - I've said things like this. The fact is that there are valid criticisms of Go and sometimes it is important to trust your own instincts and judgement .
