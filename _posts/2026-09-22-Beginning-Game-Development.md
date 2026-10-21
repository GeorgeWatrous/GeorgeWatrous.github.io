---
title: "Beginning Game Development"
date: 2026-09-22 20:03:00 -0500
categories: [Devlog, Development Process]
tags: [AI, philosophy]
description: My game development process and first steps, including a work-in-progress game layout and Generative AI strategy.
---

<div style="display: flex; justify-content: center; margin: 2rem 0;">
  <iframe 
    src="{{ '/assets/builds/Build_Version_2/index.html' | relative_url }}" 
    width="1000" 
    height="800" 
    style="border: none; max-width: 100%; border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);"
    allowfullscreen>
  </iframe>
</div>

Hello, Antigravity!

## Generative AI Strategy
This is an enormous topic, and not an easy one to cover in one post. I'll reiterate that these posts are written by hand (which will be explained later), as stated in my [First Post](https://georgewatrous.github.io/posts/First-Post/). The code for the game, on the other, will likely remain almost entirely AI-generated. 
### Necessity
To put it simply, Generative AI will make the impossible possible. I want to create a fully-functioning video game with an accompanying devlog in less than 5 months as an inexperienced developer, with no roots or education in art, graphic design, or game design. To put this in perspective, consider similar projects taken on by small teams:
* [Rain World](https://rainworld.miraheze.org/wiki/Rain_World_Wiki): While I don't mean to put my own small efforts on par with this giant, artistically-driven, undertaking, the concepts are similar. I want to create an immersive world using novel player interactions with largely autonomous and independent non-player-characters. Rain World took nearly 6 years to develop with the help of experienced professional developers. 
* [Hollow Knight](https://www.hollowknight.com/): This game took about 4 years to develop from conception to finished product. It was completed around the same time as Rain World, but leaned more into the Metroidvania genre. This focuses on similar character interactions as a basis to the game's interaction and engagement. Hollow Knight has become very popular among indie game enthusiasts and an increasingly wider community. 

These two projects represent to me the comprisation of what I want to achieve. Rain World contains many highly complex and particular elements developed specifically by its talented creators, Joar Jakobsson and James Therrien, creating a visually and conceptually appealing product evocative of a dream-like urban landscape and complete established ecosystem. Hollow Knight represents a similar world-building effort, with well-tuned art-style, music, and atmosphere, and has been a large commercial success, selling more than 15 million copies, and becoming a staple in the indie game community. 

With this in mind, it becomes difficult to imagine achieving anything meaningful within my limited time, especially with the demands of everyday life remaining in full force. Generative AI seems like the panacea to this dilemma: it can do all the grunt work of creating a complex and extensive video game, writing thousands of lines of code within a few minutes. In terms of business organization, this can act as a team of junior developers, writing general scripts that simply need tailoring to my specific needs. It can also do research, creating concise lists of pros and cons for different approaches, allowing me to sift through the options to find the best practices that will allow scaling and tweaking as the project slowly forms. Finally, it can compensate for my lack of experience in the industry by generating stand-in art, both creating and discovering existing commentaries on tropes and genres, and providing extensive knowledge of available tools to streamline the development process. 
### Risks
The enormous emergent capabilities of modern LLM's are based on their scaling abilities. Without massive data, these are fascinating, but rather unremarkable toys for researchers and computer scientists. When trained on an internet, they become formidable titans of knowledge, proportional to their titanic compute requirements. This, by necessity, makes these models generalists - a trait which is intentionally enhanced by reinforcement learning, since it is vital to prevent bias in the information and decisions produced by the model. A generalist model is exactly what is required to attain the aforementioned time savings, but leaves a large gap in a very important sector: originality. A general model left unguided will often produce essentially an average or homogenization of the existing publications in a genre. 

Nuance is required with this nascent productivity tool. It has been shown in the medical industry (where neural networks have become a valuable, and [beneficial](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2834943) tool) that after consistent use of Generative AI, trained and skilled endoscopists' ADR (adenoma detection rate) dropped significantly from 28.4% to 22.4%. In the same [study](https://pmc.ncbi.nlm.nih.gov/articles/PMC13015734/), a more worrying drop in case volume and available laboratories was recorded following the UK's transition to human papillomavirus primary screening. 

While deskilling isn't nearly as dire for my situation as it is for the healthcare industry, it is adjacent to a rather pernicious threat: if I don't understand the fundamentals of my own project, I will be unable to fix any issues that the AI can't fix on its own. Less dramatic, and more likely, if I lose my original vision to the arbitrary decisions of the AI system, the project will lose originality and intentionality. Absolutely viable to the success of the project is my ability to understand and intentionally select each detail. 

### Development Plan
In order to walk the fine line between insufficient use of AI tools and overuse, I have established a 3-step method.
1. Start on Paper: The easiest way to maintain an intentional approach and sustain my own long-term vision of the project is to begin by sketching and describing the ideas on paper. This also requires a fine balance and a skill to be developed. Paper allows as much detail and tweaking as desired, and can siphon time away from the actual project. It can also be wasted due to insufficient detail or lack of long-term plans. My notebook serves as my way of storing the sentiments and plans I deem imperative to the final product, as well as providing a baseline to compare the results of the AI against. 
2. Prompt Antigravity: After my original plan has been recorded and saved on paper, I draft a prompt describing each detail of what I produced, including images of sketches if necessary. The paper exercise produces the necessary detail to guide the actions and decisions of the multi-agent system (more on that later), and a way of checking and correcting the product. 
3. Understand and Iterate: Antigravity uses "artifacts" to track its own progress and creations, intended to allow the user to understand each line of code it has created. This also allows me to diagnose issues. For example, in this post's featured build, the original movement system was jerky and would have issues while interacting with corners. I was able to isolate the bug, describe it in detail, and work with Antigravity to clean the issue. 

It is important to understand that this is a preliminary and simplistic method. As the project progresses, this process will become more sophisticated and efficient. 

### Philosophy
Generative AI is moving *fast*, and the challenge of the tech industry is to keep pace with these advancements. I believe that the most successful engineers, programmers, scientists, and researchers of the future will be those who can strike the balance I have been attempting to describe. A huge part of this project is attempting to better understand and use AI at multiple levels (from custom-built neural nets to fully-functioning off-the-shelf systems of agents), and maintain pace with the fast-moving world of tech. I believe that the stringent requirements of this project create the push necessary to truly learn to use this technology, and I hope that any readers will be able to learn as much as I do from this undertaking. 

## Fundamental Technology: Antigravity
### Structure
The idea behind [Antigravity](https://antigravity.google/docs/overview) is simple. A network of agents act autonomously on a central prompt with access to local systems and the internet in order to complete the prompt as accurately and completely as possible. This is a pattern of the system that Claude Code originally popularized, and provides the enormous coding ability, speed, and accuracy that shocked the world when Claude Code was released. 

The structure consists of an 'agent harness,' or 'agent manager' that represents the central agent prompted by the human user. This agent then spawns 'subagents,' who are prompted to complete certain tasks deemed necessary by the central agent, including thinking, drafting plans, researching, writing specific code segments, and any intermediate steps. [This](https://antigravity.google/blog/google-antigravity-built-an-os) blog post describes the process for two interesting applications of the remarkable technology: building an OS from scratch and replicating the AlphaGo project. 

All of this occurs within a local folder with access to command-line tools, allowing the agent freedom to create, edit, and test extraordinarily quickly. Antigravity accomplishes this through a "split-plane" structure, in which a local client sends prompts with local context (restricted by specific permissions) to the cloud for processing by the actual models on Google's Cloud infrastructure. The result is sent down with text, code, and specific shell commands. 

* On the local "plane," Antigravity uses a "terminal sandbox" to execute shell commands. This sandbox is built on OS primitives, and therefore avoids any Docker image or virtual machine start-up requirements. It largely functions as a security device in order to restrict any shell commands from being executed out of the sandbox or any specified mount points. (For an explanation on Docker and its constituents, see [this post](https://georgewatrous.github.io/posts/New-Workflow/)). 
* On the Cloud "plane," Google's infrastructure recieves the incoming prompt and context, and runs the agent(s) just as a chatbot would, spawning subagents if prompted. The result is sent back to the local client with shell commands and read-write commands for those files within the sandbox with read-write permissions. The local client can then execute the commands within the terminal sandbox. 

### Security
For those unaware of cybersecurity incidents occuring at companies like [Meta](https://www.cbsnews.com/news/meta-says-ai-model-breached-third-party-company/?ftag=CNM-00-10aab7e&linkId=990576010), [OpenAI](https://en.wikipedia.org/wiki/OpenAI_rogue_agent_breach_of_Hugging_Face), and [Anthropic](https://www.reuters.com/legal/litigation/anthropic-reports-fourth-cybersecurity-incident-with-early-version-claude-2026-09-09/), the emphasis on security and permissions when discussing agentic architecture may seem extreme. It has been shown multiple times, pretty universally, agents will break systems in order to achieve their instructions. For this reason, running agents with access to local systems puts those systems in danger: if agents can break out of isolated sandboxes designed by high-profile corporate labs, running unrestricted agents on local systems can be extremely dangerous even with entirely benign prompts. 

Antigravity has several methods to combat this, in addition to and cooperation with the aforementioned terminal sandbox. In the Antigravity App, users set permissions that will restrict execution of shell commands at different levels, with the highest setting asking the user for permission before executing any shell command (discluding read-write commands for editable files within the sandbox, which work slightly differently). 

### User Interface and Reporting
Antigravity has two main implementations: the standalone app (based on a fork of VS Code), and the CLI (Command Line Interface), which maintains all prompts and communications from the same command line where shell commands can be executed.As of now, I will be using the App as it presents a familiar feel to Visual Studio Code, and I am editing on a Windows device, which is less conducive to a command-line system. 

Since so much happens beneath the surface, reporting and auditing is imperative for human supervision. Antigravity's solution to this issue is "artifacts." This includes Markdown plans, architecture diagrams, and/or images that represent its identified deliverables. The Implementation Plans and Walkthroughs are the most important for my project. Before executing any code edits or structural changes, Antigravity's team of agents prepares an implementation plan that will be reviewed ahead of time and approved or edited by the user (dependent on permissions enabled or disabled by the user). Walkthroughs are generated after code edits, and include detailed explanations of what the agents changed and how it will affect the product. 

As established in the AI philosophy section, I believe that these accountability measures are paramount for me to retain creative control over my project and achieve the result that best maximizes the outcomes of my situation, not a general case or alternate problem. 

## General Application
Antigravity is a wonderful tool, and is my choice for this project based on its interactability with other Google technologies that I use on a regular basis (the same plan covers Google Suite AI as well as other utility devices), but it is NOT the only tool on the market nor is it definitionally superior to its competitors. I appreciate the functionality available in the Antigravity App, and this post describes the methods I believe best suit its use. There is still much to learn, and my methods will no doubt change in the future! 

>"The world alters as we walk in it, so that the years of man's life measure not some small growth or rearrangement or moderation of what he learned in childhood, but a great upheaval... One thing that is new is the prevalence of newness, the changing scale and pace of change, so that the world alters as we walk in it." - Robert J Oppenheimer
