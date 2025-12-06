---
title: "My Journey Through the LFX Linux Kernel Mentorship Program"
date: 2025-12-06
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
My Journey Through the LFX Linux Kernel Mentorship Program
==========================================================

When I first decided to apply for the Linux Foundation's LFX kernel mentorship program, I knew it would be tough. At the beginning, there were 12 tasks I had to complete to show I understood the basics of kernel development and to get accepted into the program. They helped me understand what I was getting into.

Now that the mentorship is almost over, I can say this experience changed how I think about working with the Linux kernel. While I'll talk about my specific code contributions later, I wanted to first share the learning journey itself and the resources that made it possible.

Starting Small and Building Knowledge
-------------------------------------

My mentorship journey started with understanding the broader Linux kernel first. I read documentation and learned the basics of how everything works. Once I had a good foundation, I chose DRM (Direct Rendering Manager) drivers. Instead of jumping straight into writing code, I spent time reading documentation and looking at how other developers solved problems in the DRM subsystem. By studying existing patches and understanding the community's discussions around them, I was mostly reading real code written by experienced developers and seeing how reviewers gave feedback.

The Tools That Made Learning Possible
-------------------------------------

As I dug deeper, I realized I needed tools to actually understand what was happening in the kernel. This is where the practical side of development started.

QEMU and GDB became my main debugging partners. QEMU let me run a Linux system inside my computer as a virtual machine, and GDB let me pause that kernel and look inside it step by step. There are other debugging tools available, but GDB was the one I used most.

Resources:

*   [GDB usage — QEMU documentation](https://qemu-project.gitlab.io/qemu/system/gdb.html)
*   [Setting up QEMU-KVM for kernel development](https://www.collabora.com/news-and-blog/blog/2017/01/16/setting-up-qemu-kvm-for-kernel-development/)
*   [Syzkaller Ubuntu host setup guide](https://github.com/google/syzkaller/blob/master/docs/linux/setup_ubuntu-host_qemu-vm_x86-64-kernel.md)

Syzkaller is another tool that was crucial to my learning. It automatically fuzzes the kernel, running thousands of test cases to find bugs that humans would never think to test. When syzkaller finds a bug, it gives you a reproducible test case, but understanding that bug in your local environment is another challenge.

You can check out this post from Moon Lee, a mentee from a previous term. The blog post "Proof of Execution: Reproducing Syzbot Bugs in Local Kernel" shows exactly how to take bugs that syzkaller finds and reproduce them locally:

Resources:

*   [Proof of Execution: Reproducing Syzbot Bugs in Local Kernel](https://www.linkedin.com/pulse/proof-execution-reproducing-syzbot-bugs-local-kernel-moon-hee-lee-081bc/)
*   [Syzkaller: Fuzzing the kernel](https://www.collabora.com/news-and-blog/blog/2020/03/26/syzkaller-fuzzing-the-kernel/)

Understanding the Kernel and Drivers
------------------------------------

To understand how the kernel actually works, I read parts of the books like "Understanding the Linux Kernel" and "Linux Insides". For drivers, the Linux Device Drivers book available online was really helpful. Since I was focused on DRM, the official DRM documentation gave me the specifics I needed. When I needed to browse and understand existing code, **cscope** became my main tool.

Resources:

*   [Understanding the Linux Kernel (book)](https://doc.lagout.org/operating%20system%20/linux/Understanding%20Linux%20Kernel.pdf)
*   [Linux Insides (free online)](https://0xax.gitbooks.io/linux-insides/content/)
*   [Linux Device Drivers (3rd Edition)](https://lwn.net/Kernel/LDD3/)
*   [DRM Introduction](https://docs.kernel.org/gpu/introduction.html)
*   [Kernel Documentation](https://docs.kernel.org/)

Learning from the Community
---------------------------

Lore.kernel.org is where all kernel discussions happen. By reading patches and the feedback developers give on them. LWN (Linux Weekly News) is also a great resource to stay updated.

*   [LWN (Linux Weekly News)](https://lwn.net)

The Linux Foundation also hosted mentorship sessions with experienced kernel developers

*   [LF Live: Mentorship Series](https://events.linuxfoundation.org/lf-live-mentorship-series/)


The Linux kernel community is actually really nice to people who show up with real interest and respect for how things work. In a future post, I'll go into detail about the specific things I've been working on. If you're thinking about working on the Linux kernel: these tools and resources will be helpful. All you need is curiosity, time, and willingness to learn how things actually work.
