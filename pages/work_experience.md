---
layout: page
title: Work Experience
permalink: /work_experience
---

## Continuous Integration (March 2018 - Present)

* Senior Software Engineer (September 2020 - Present)
* Software Engineer II (September 2018 - September 2020)
* Software Engineer (March 2018 - September 2018)

As described [here](https://docs.microsoft.com/en-us/azure/devops/learn/git/git-at-scale), making a Continuous Integration system for the whole Windows codebase is challenging because:

* There's about 4,000 developers in the Windows codebase.
* The repository has 150K to 250K branches.
* We need few minutes to several hours for an incremental build and test. 12h for a full build + validation.

A few highlights of my work on this team:

1. Worked on the virtual team to implement a **new build engine** for our CI system. Instead of using an incremental approach, this new build engine builds most of the repository and caches the outputs to make sure that we build every dependency. My key contributions to this project were:
    1. Lead a sub team of 3 developers to improve the **overhead of the build engine**. First, I identified all of the parts of the system that could be subject to optimization. Then, I mentored 2 junior engineers to work on the performance improvements, while also working on some myself. In the end, we have been able to **reduce 25% of P80 overhead time (30 mins)**. With total improvements underway would reduce overhead by 50%.
    2. Worked on the **rollout for PR builds**, implemented the pipelines, gave the first training to new customers, and established tooling so that onboarding could be made automatic.
    3. Reduced our nightly build capacity for regular builds to only the branches that needed the builds which allowed us to **free around 60% of our nightly build machines**. This made it so we could **ship our new engine to all customers** for nightly builds.
2. Collaborated with another developer to **rewrite the biggest component of our system**. This rewrite allowed us to be able to expand the system with ease. Eventually, this allowed us to onboard **2 more build engines** into our platform.
3. **Mentored 4 junior engineers** which has allowed them to make important contributions to our system.
4. **Worked with several external teams** to make sure to provide them with the best experience for our team.
   1. Met with one team and reduced their timeouts from 60% to 30%.
   2. Worked with another team and allowed them to onboard tests into our platform.
   3. Worked with a third team to allow them to onboard static analysis into our build engine.
   4. Worked with another team to allow for bootability tests in the pipeline. This means patching an existing VHD with the contents of the build and booting it to see if it works.
5. Redesigned several components of our initial system to improve our **P50 overhead from 1-2 hours** to **20 minutes of overhead**.
    1. Remade the entire snapshot selection algorithm. This algorithm takes as input the git commit graph and the previous snapshot builds. With those inputs, it decides which build snapshot would make the build take the shortest time. I first spent a month documenting the existing algorithm and created a 10 pager explaining it. I presented this to the team. After this I created a new algorithm that would **increase performance by 5-10% of the full build time**. This work leveraged my work on the mirroring component to run all of the experiments.
    2. Moved of most components of the system to **Azure microservices** using Azure functions. This has allowed the system to have **~20% build time reduction**.
6. Created a pipeline that takes telemetry from production builds and **creates exact copies of those builds for testing**. This has allowed for **rewriting most components of the system**. Moreover, it has also increased reliability by allowing developers to test their changes with confidence. Work on this component, allowed us to rewrite our biggest component and we were able to test that there were no regressions.
7. Interviewed several candidates for Microsoft's efforts in recruiting for LATAM. I did the maximum number of allowed interviews per year to get talent from universities into Microsoft.

## BuildXL migration (August 2016 - March 2018)

* Software Engineer

This project consisted on moving the whole Windows codebase from using [MsBuild](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild?view=vs-2019) and [NMake](https://docs.microsoft.com/en-us/cpp/build/reference/nmake-reference?view=vs-2019) to use [BuildXL](https://github.com/microsoft/buildxl). I worked mainly with DScript (a TypeScript based language).

1. Trained 2 teams on the usage of DScript and aided in the creation of the SDK for 1/4th of the Windows build logic.
2. Created a compiler to translate from the old MSBuild and NMake source files into DScript. Supported this tool for 9 months.
3. Leveraged an NMake parser to translate the remaining 3/4ths of the old build logic into a DScript SDK.

## Microsoft Internship III (May 2015 - August 2015)

During my third internship I worked on an analyzer to analyze C++ #include directives in the Windows source code. This system worked by using the compiler's precompilation function which allowed to output the code with the replaced include directives. After this, the system looked at the symbol usage and the provenance of said symbols. After that we were able to delete the includes that were not necessary. The problem becomes more complicated after you understand the nuances of the #include directives. The directive basically copies code from one file to another. One of the more difficult examples are outlined here.

## Grupo BMS (September 2014 - August 2015)

I worked as a consultant for Grupo BMS. Me and a team of 2 others were tasked on creating iOS and Android apps for a radio ad sales application.

## Microsoft Internship II (May 2014 - August 2014)

In this internship I was part of a team of 9 interns were we worked on writing an SDK for [BuildXL](https://github.com/microsoft/buildxl).

## Microsoft internship I (May 2013 - August 2013)

In my first internship I worked with an internal tool uploading remote storage consumption information to a data analysis platform.
