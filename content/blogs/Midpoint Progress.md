---
title: "Midpoint Progress"
date: 2024-02-20
draft: false
ShowToc: true
slug: 
category: blog 
summary:
description: 
cover:
  image:
  alt:
  caption: 
  relative: true
showtoc: true
draft: false
--- 


Hello Readers!

As we reach the midpoint of our internship program, it is an opportune moment to assess the progress achieved thus far and delineate the path forward for the upcoming phase. Experience our discussion on our accomplishments, the hurdles we've faced, and our plans for the future.

Goals Achieved in the First Half:
---------------------------------

*   The initial phase saw the successful completion of several tasks:

*   Local Environment Setup: We established a local environment running both MoinMoin 1.9x and MoinMoin 2, providing a sandbox for exploration and testing.
*   Upstream Documentation Review: Extensive review of the upstream documentation shed light on the intricacies of migrating to the latest version, ensuring a solid understanding of the process.
*   Documentation of Differences: A comprehensive document outlining the differences between MoinMoin 1.9x and MoinMoin 2 was compiled, offering valuable insights for the migration journey.
*   Successful Migration: A significant milestone was achieved by successfully creating and migrating a simple wiki page from the old version to the new version, accompanied by detailed documentation of the process.

Challenges Faced:
-----------------

However, as is often the case in any ambiguous project, not every goal was met seamlessly. We encountered challenges while attempting to migrate the whole dump to MoinMoin 2. As an interim target, we decided to focus on upgrading the Debian package moin2, which can be found [here](https://salsa.debian.org/moin-team/moin). Upon investigation, we discovered that the package was behind about 500 commits compared to upstream. To familiarize ourselves better with the codebase of MoinMoin 2, we set out to upgrade it.

Progress Update: Successfully Building the Existing Package Locally:
--------------------------------------------------------------------

I found the Debian build system a bit complex. Successfully building the package involved facing numerous challenges. Concepts unfamiliar to us emerged during the process, requiring time and effort to grasp fully. However, after dedicated learning and troubleshooting, we managed to build the package locally. As the next step, we plan to upgrade it to synchronize it with the upstream version. We're currently progressing with the work and testing for it.

Looking Ahead:
--------------

With the Debian package built locally, our focus now shifts towards upgrading it to align with the upstream version.
