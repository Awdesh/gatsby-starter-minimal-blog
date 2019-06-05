---
title: Summary of dev talks from the Dev conference I attended last week.
---

It’s been a while since I have posted an article. I thought this might be a nice article to share while stuff from the conference is still fresh in my memory. The conference was heavily focused on microservices, Kubernetes and cloud platforms. 

I want to share some of the highlights from different sessions so to have a note for myself for the future reference :P

There were a lot of sessions around microservices. I’ll try to summarize my understanding from a lot of different talks on the same topic. The common theme of different talks was to focus on the evaluation of the need for microservices in your architecture. 

Some of the things to consider before choosing microservices architecture.

__Security__ -: Different services need to talk to each other and communicate by sending data over the network. Data in motion between services needs to be encrypted which is something you don’t need to worry in a monolith service architecture.

__Network latency__ -: In Microservices architecture services are going to be spread around the network. Calling one service from another over the network could be slow because of network slowness.

__Observability__ -: Adding centralized telemetry data around different services can be a challenging task.

__Team dynamics__ -: Team dynamics can be tricky with each team working in the silo on their own small piece of service.

__Versioning can be a pain__ -: Different microservices can have different versions based on the feature implementations. It is vital to keep track of which version is compatible with which version of other microservices.

**Some interesting mentions of the tool for microservices in another talk**. 

__Istio__ -: Service mesh to manage micro services.

__Envoy__ -: Side car proxy to enable communication between services in a microservice architecture.

__Mixer__ -: Gather telemetry data from different services.


Another talk was around going from Monolithic architecture to Microservices via mini services. I quickly wrote down the comparison chart in the talk. 

__Mini service__ architecture as I understood is an intermediate between the monolith and microservices architecture in which you neither have a bulky codebase with every possible implementation nor you go crazy by splitting every possible feature into a microservice. 

In mini service, you only split features that require more work/ maintenance or whatever matrix you choose to split.


**Web assembly talk**

I really found this talk very interesting. I have read about web assembly before but never cared to understand it thoroughly. I found the talk to be a quick and good intro to web assembly.

Write code in different languages like C, C++, Go, Rust and have it compile into web assembly directly into the browser. The idea of web assembly is to get native desktop app performance on the browser with the same code base that you have used to write a desktop app thus bypassing rewriting the application in JavaScript.

Think about desktop games, Java applet applications running in the browser without asking the client to download runtime and without developer to port desktop app code to JavaScript.

You do not write code in web assembly rather you compile code in web assembly by using the language compilers.

Node Js 8 or higher supports web assembly.

80% of the browser supports web assembly.

Compiled web assembly is called .wasm which can be imported as an ES6 module.



**Chaos Engineering** was another term that I really found very interesting. Netflix uses it and the idea is to take servers offline from the architecture to see if other servers are able to take load successfully.

There was another interesting talk about **Outcome driven development** which focused on how to achieve efficiency within the engineering team by focusing on the outcome rather than the output.

I got introduced to **Dev SecOps** term in a cloud security talk. The talk was focused on using the security policies in the development environment so to not get surprised eventually when software doesn’t go through validation afterward.
Have a baseline of cloud infrastructure that can be agreed upon by Devs and Security team.


The closing talk was very informative from the director of AWS. The topic of the talk was how to create MLP (most loved product) not MVP. How we create MVP first and then keep adding features into it rather than improving MVP.

There were a lot of great insights about great UI from the work of Dieter Rams, the chief designer of Braun. His Wikipedia page talks about all the good design principles. https://en.wikipedia.org/wiki/Dieter_Rams



This is it. 

Please feel free to send your feedback and comments to add further on the topics or correct me if I went wrong in some of my understanding from the talk.

