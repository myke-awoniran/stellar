# Further Reading

Resources that informed the thinking behind this research without being formally cited. This list is actively maintained
and will grow as the project progresses.

---

## io_uring

**Efficient I/O with io_uring —> Jens Axboe**
The original design document written by io_uring's author. Covers the architectural rationale behind the dual-ring
model, the submission/completion queue design, and the kernel engineering decisions that make zero-syscall I/O possible.
https://kernel.dk/io_uring.pdf

---

**Ringing in a new asynchronous I/O API —> LWN.net**
LWN's early coverage of io_uring at its introduction into the kernel. Useful for understanding the landscape of async
I/O that io_uring was designed to replace (AIO, libaio) and the specific problems it was solving.
https://lwn.net/Articles/776703/

---

**Why You Should Use io_uring for Network I/O —> Red Hat Developer**
A practitioner-focused article from Red Hat making the case for io_uring in network I/O workloads. Covers the syscall
overhead problem, the epoll comparison, and practical motivation for the readiness-vs-completion transition.
https://developers.redhat.com/articles/2023/04/12/why-you-should-use-iouring-network-io

---

**Missing Manuals: io_uring Worker Pool —> Cloudflare Blog**
Cloudflare's deep-dive into io_uring's internal worker pool; the kernel-side machinery that handles operations that
cannot be completed inline. Essential reading for understanding io_uring's behavior under real network workloads and its
interaction with the kernel thread model.
https://blog.cloudflare.com/missing-manuals-io_uring-worker-pool/

---

**An Introduction to the io_uring Asynchronous I/O Framework —> Oracle Linux Blog**
Oracle's introductory treatment of io_uring from a systems administration and deployment perspective. Useful as a
secondary framing of the framework's capabilities across kernel versions.
https://blogs.oracle.com/linux/an-introduction-to-the-io-uring-asynchronous-io-framework

---

## liburing

**liburing —> Jens Axboe (GitHub)**
The official userspace library for io_uring, maintained by Axboe. The primary interface used in this project's empirical
harness for submitting SQEs and reaping CQEs without manual ring management.
https://github.com/axboe/liburing/

---

## Tiger Style

**Tiger Style — tigerstyle.dev**
The community distillation of TigerBeetle's engineering methodology —> covering static allocation, assertion philosophy,
explicit control flow, and the NASA Power of Ten rules that underpin the development constraints applied in this
codebase. The direct reference for the Tiger Style principles governing this project's benchmark harness.
https://tigerstyle.dev/

---

## Zig

**Introduction to Zig —> Pedro Duarte Faria**
An open-access book covering Zig's core language model, memory semantics, and error handling philosophy. Relevant to
understanding the Tiger Style constraints applied in this codebase — particularly the allocator model and comptime
guarantees.
https://pedropark99.github.io/zig-book/Chapters/01-zig-weird.html

---

_This file is a living document. Links will be added as the research progresses through its empirical and synthesis
phases._