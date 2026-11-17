---
title: "What Works? (and What Doesn't) When Using Antigravity and Other Code-Assist Tools"
date: 2026-11-04 17:31:00 -0500
categories: [Devlog, Development Process]
tags: [AI, context engineering, prompt engineering, philosophy]
description: A continuously running blog post summarizing strategies I've attempted and their various success levels. 
---

## New Post Format (how to read)
For those that have followed this blog in the past, this post will deviate pretty significantly from the established format. It is separated into two main lists: what *to do* and what *not to do*. Each will begin with a description of the strategy and a link to a dedicated tutorial post, including the *not to do*. Both lists will have specific criteria with which each strategy will be rated. 

## What TO do with Antigravity
- ### Continuous Documentation
    > [Dedicated Tutorial](https://george.watrous.ws/posts/continuous-documentation/)
    
    **The Concept**: When you start a new project, have Antigravity build a formatted living documentation and update it live with each addition or change.  
    
    **The Benefits**: 
    1. Understandability. In [this post](https://george.watrous.ws/posts/Beginning-Game-Development/#:~:text=the%20development%20process.-,Risks,-The%20enormous%20emergent), I discuss the risks of using AI when developing extensive applications, specifically, the danger of losing track of both the way your code functions and *your original goals for the project*. Keeping up with documentation is much easier than attempting to comb through old chats or reanalyze existing code (even with the help of an agent), streamlining the process of ensuring best-practices, code ethics, and collaboration standards. The documentation can maintain a record of your goals and how each implementation attempts to fulfill them.
    2. Context. One of my favorite Antigravity features so far is the ability to [quote specific documents or chats](https://antigravity.google/docs/features/#mentions-and-quoting). When I notice a bug in the final product, rather than describing exactly what I want to happen, I can easily locate the section of the well-formatted documentation describing the feature at issue, and quote the relevant description with all necessary context. Additionally, overarching goals can be described within the documentation, easily keeping those original goals fresh in context. 
- ### Mathematical Development Model
    > [Dedicated Tutorial](https://george.watrous.ws/posts/mathematical-development-model/)
    
    **The Concept**: Develop a system of translating ideas from language (a subjective medium) into discrete mathematical quantities, and include the interpretation in plain language. 

    **The Benefits**:
    For any application, it is easy to define terms with vague or subjective language, but a mathematical or otherwise deterministic definition will be much more effective and cheaper for the AI to implement. 

## What NOT To Do With Antigravity
- ### Single Conversation
    > [Dedicated Tutorial](https://george.watrous.ws/posts/avoiding-context-fatigue-when-using-agent-management-and-code-assist-systems/)
    
    **The Fallacy**: Often when beginning a project with a code-assist tool, it's easy to continually use a single chat window, or conversation for every modification. This works for small-scale projects and can be beneficial in the short-term by maintaining all necessary context, but when used for a project for longer than a few prompts, the model quickly loses clarity and effectiveness, leading to expensive and time-wasting diversions from the prompt. Additionally, it becomes very difficult to locate important context if you want to return to an idea in a later conversation. 

    **The Lesson**: Prompt engineering is becoming a house-hold term, but *context* engineering has yet to become so widely adopted. Context engineering is the process of maintaining a clean and efficient context window to enable quick and accurate recall in agents and agentic systems. Using a single chat quickly runs into the what I call "context fatigue," a point at which the model is overwhelmed with context and fails to recall relevant information, reason successfully, or make targeted decisions. Separate chats can be used to manage context much more effectively, as explored in [these articles](https://george.watrous.ws/tags/context-engineering/). Here is an [article by Anthropic](https://www.anthropic.com/research/effective-context-engineering-for-ai-agents) on the subject, and this [blog post](https://medium.com/@andrewswhitehouse/context-collapse-in-ai-systems-7374c31a8bc2) is an older but effective look at the consequences of bad context management. 
