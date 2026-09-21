## Thomas Nelson

Infrastructure engineer. Most of what I do sits between the hardware and the
operating system: GPU cluster operations, firmware, bare-metal provisioning, and
the diagnostic tooling that tells you which of those three is actually broken.

Recently that has meant keeping 128-node production GPU clusters running for
customer AI training workloads, and building a deployment and diagnostics
environment from scratch for an industrial hardware manufacturer.

### What I tend to build

Small, boring, single-file tools that run on a machine that is already
misbehaving, over a link that might drop, in front of someone who is having a
bad day. That shapes the choices: no runtime dependencies, one missing binary
never costs you the rest of the output, and anything that changes the state of a
machine records how to change it back.

I write the reasoning into the code. If a comment says why a line is the way it
is, it is usually because the obvious version was tried first and broke
something.

### Public here

- **[gpu-scripts](https://github.com/TIsForThomas/Gpu-scripts)** - quick NVIDIA
  and AMD node health checks: driver state, thermals, power, ECC counters, CUDA
  bandwidth, plus log collection.
- A handful of small Python utilities from earlier on, left up because pretending
  you started at the deep end helps nobody.

Most of my current work is internal tooling for hardware I do not own, so it
lives in private repositories. Happy to walk through any of it.

### Working on

Kubernetes and Terraform, and enough electrical engineering to read a schematic
properly: PCB fundamentals, signal integrity, DC power delivery, and bench
testing with something better than guesswork.
