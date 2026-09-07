---
title: "New Workflow"
date: 2026-09-06 8:28:00 -0500
categories: [Devlog, Development Process]
tags: []
description: I now use a docker volume and WSL to host the jekyll theme locally, allowing revisions and proofreads before committing changes to Github. 
---
Hello, Docker!

## Development Iteration
I can now host the website locally, which will allow me to edit in the comfort of my own VS Code, as well as proofreading any changes and editing for structure alongside each post. The fundamental technology behind this is a Docker volume running WSL (Hence the tagline). The Jekyll theme I decided to use is called "Chirpy", is built with Ruby, and will only run locally on Linux systems. Docker provides a container in which I can run this technology, and the volume stores the iterations and allows me to push to Github when the changes are complete. 
### Future Implications
With this new workflow, I can begin development of a post-pipeline consisting of the following steps. 
1. A custom rich-text editor imitating the layout of the website in which I can write my post. 
2. Conversion from the rich-text editor to a markdown document.
3. Markdown document is added to the posts folder and pushed to Github.

## Skills Learned
### Docker
I have a greatly enhanced understanding of this lucrative technology. Important concepts:
* Docker Containers: This creates a new image (file system) built around any operating system. This image is run using Docker Engine and given access to the host computer's compute resources, but does not interact with or "see" the host system's operations in any way. The container can be interacted with through command-line just as with any computer, and can be edited through tools such as VS Code. All of this functionality allows developers to "package" applications in these containers and "ship" them to any device, as all libraries, languages, and dependencies are shipped with the application codebase in the Docker Container. 
* Docker Volumes: Docker volumes cannot interact with the host system's files at all. Volumes - reminiscent of mount points in earlier linux days - are directories within a Docker Container that point back to files on the local system. This allows the container to be closed and reopened without deleting all application progress on the local machine. Volumes are allowing me to iterate the website locally on a Windows system while updates are pushed to Github in parallel, granting general Git-Github functionality and bypassing the mismatched operating systems. 

### Git and Github
I have always been a Git novice. The website section of this project has been done without AI assistance to force me to learn the fundamentals of Git on my own before speeding up the process with agentic tools. 
