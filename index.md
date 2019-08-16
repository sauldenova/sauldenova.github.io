---
layout: home
title: About
permalink: /
---

I'm a Software Engineer II at Microsoft. I'm currently working on setting up microservices for a Continuous Integration system for the Windows codebase.

Here's a list of the projects I've worked on:

### Continuous Integration (March 2018 - Present)

As described [here](https://docs.microsoft.com/en-us/azure/devops/learn/git/git-at-scale), making a Continuous Integration system for the whole Windows codebase has it's own set of challenges because:

* There's about 4,000 developers in the Windows codebase.
* The repository has 150K to 250K branches.
* Few minutes for an incremental build and test. 12h for a full build + validation.

A few highlights of my work on this team:

1. Created a pipeline that takes telemetry from production builds and creates exact copies of those builds for testing. This has allowed for refactoring components of the system. Moreover, it has also increased reliability.
2. Remade the entire snapshot selection algorithm. This algorithm takes as input the git commit graph and the previous rolling builds. With those inputs, it decides which rolling build snapshot would make the build take the shortest time. I first spent a month documenting the existing algorithm and created a 10 pager explaining it. I presented this to the team. After this I created a new algorithm that would increase performance by 5-10% of the full build time. This work leveraged my work on 1 to run all of the experiments.
2. Moved of most components of the system to Azure microservices using Azure functions. This has allowed the system to have ~20% build time reduction.
3. Worked with another team to allow for bootability tests in the pipeline. This means patching an existing VHD with the contents of the build and booting it to see if it works.

### BuildXL migration (August 2016 - March 2018)

This project consisted on moving the whole Windows codebase from using [MsBuild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild?view=vs-2019) and [NMake](https://docs.microsoft.com/en-us/cpp/build/reference/nmake-reference?view=vs-2019) to use [BuildXL](https://github.com/microsoft/buildxl). I worked mainly with DScript (a TypeScript based language).

1. Trained 2 teams on the usage of DScript and aided in the creation of the SDK for 1/4th of the Windows build logic.
2. Created a compiler to translate from the old MSBuild and NMake source files into DScript. Supported this tool for 9 months.
3. Leveraged an NMake parser to translate the remaining 3/4ths of the old build logic into a DScript SDK.