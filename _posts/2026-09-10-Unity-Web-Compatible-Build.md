---
title: "Unity Web-Compatible Build"
date: 2026-09-06 20:03:00 -0500
categories: [Devlog, Development Process]
tags: [Docker, Git]
description: Interactive Web-compatible Unity builds create entirely javascript-powered HTML pages that can be run in-browser on the static Github Pages site. 
---

Hello, Javascript!

## Development Iteration
One advantage of working with a game engine, rather than coding from scratch, is the multi-platform support. Unity's Web Build Support module automatically builds an HTML-Javascript-CSS application that can run in any browser. Without this functionality, it would be impossible to post a working game prototype without rebuilding the website with a backend or embedding the game while hosting it on another site. 
## Fundamental Technology
Unity is a very complex technology, and much of the software is proprietary, but this brief overview will provide some insight into the fundamentals of the game engine. This overview focuses on the pipelines Unity uses to build game executables for different machines and platforms. Unity uses the term "scripting backends" to describe these processes.
### Context
To understand the philosophy and strategy behind the development of Unity's scripting backends, some background knowledge surrounding Microsoft's [.NET Framework](https://dotnet.microsoft.com/en-us/learn/dotnet/what-is-dotnet-framework) and [Common Language Infrastructure](https://ecma-international.org/publications-and-standards/standards/ecma-335/) (CIL) is necessary. 

Microsoft's .NET Framework - the original implementation of the modern .NET Core - is a software development platform intended to run various applications (websites, services, and generic desktop apps) on Windows machines. It was released alongside C# and CLI, specifications for both of which were published and maintained by standards bodies such as [ECMA International](https://ecma-international.org/). 
* CLI: Common Language Infrastructure is a set of specifications regarding basic operative elements of cooperating languages; for example, CLI defines exactly how objects such as integers operate so that they remain identical in function across languages (these specifications are known as Common Type System). Common Language Specification is an associated set of rules governing libraries. Participating languages, such as C#, F#, and Visual Basic, compile into a Common Intermediate Language (CIL) - the initialisms are pretty annoying, but they are learnable, and used quite often - which is run using the Common Language Runtime (CLR). 
The .NET Framework is a software development platform designed to run CLI-developed applications on any Windows device. However, many developers wanted to expand their applications beyond the Windows ecosystem. This issue was addressed by Mono.

[Mono](https://www.mono-project.com/) was developed as an open-source<sup>1</sup>, clean-room<sup>2</sup> alternative to the .NET Framework. It created a software development platform that would run CLI on Windows, Mac, or Linux, using the same just-in-time<sup>2</sup> compiler system. Later, Microsoft began to officially support and sponsor the Mono project, and created its own .NET Core based on the Mono project's cross-platform functionality. 


### Process
  The game engine "builds" executables of the game using two different pipelines :
  1. Mono: The original scripting backend was forked from the open source Mono project. The cross-platform utility of a single high-level language: C# was attractive to the young Unity Corporation. 
  2. IL2CPP (Intermediate Language to C++): This was a later attempt to pull away from the just-in-time compiler used by the CLR. Instead of delivering files to multiple devices in CIL, Unity developed the in-house, proprietary, IL2CPP software, which compiled CIL into C++, the native language almost the entire engine was built in. The generated C++ code could then be compiled ahead of time for the target system and delivered as machine-ready code. 

## Result
This interactive display is not embedded from another website, but hosted as a static Web-compatible game. Unity's pipelines have expanded from just Windows, Mac, and Linux to almost any framework including the HTML-CSS-Javascript standard used in web development. 

<div style="display: flex; justify-content: center; margin: 2rem 0;">
  <iframe 
    src="{{ '/assets/builds/index.html' | relative_url }}" 
    width="1000" 
    height="800" 
    style="border: none; max-width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);"
    allowfullscreen>
  </iframe>
</div>

### Definitions:
1. Open-source: This refers to code licensing. An open-source project allows contributors and users to view or edit the source code, often in attempt to build a community of contributors to maintain a useful project. 
2. Clean-room: This is a method of reverse-engineering in which developers will outline just the functionality of the original software, aiming to emulate it without touching any of the source code from the original project. When this technique is executed correctly, it avoids any licensing or intellectual property conflicts. 
3. Just-in-time Compiler: Instead of translating the entire program beforehand or reading it line by line, this compiler converts parts of the code right as they are needed and saves the result in memory. This allows the same CIL file to run on any computer using the CLR for that system, while maintaining efficiency. 

>"The applications of knowledge ... reveal the unity of all knowledge. In a new situation almost anything and everything you ever learned might be applicable, and the artificial divisions seem to vanish." - Richard Hamming
