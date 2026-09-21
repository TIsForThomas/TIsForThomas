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

### Projects

- **[toast](https://github.com/TIsForThomas/toast)** - one bootable USB that
  syspreps a configured Windows machine, captures the disk, and redeploys it onto
  a drive of a different size. The trick is shrinking NTFS before the block bitmap
  is taken, which is the only moment a smaller-disk restore can be made possible.
  Shell and PowerShell, 56 automated checks against a built ISO.
- **[ami-bios-settings](https://github.com/TIsForThomas/ami-bios-settings)** -
  decode named BIOS settings straight out of a raw UEFI firmware image and diff
  two of them, so configuration drift between units can be proven instead of
  eyeballed. Finds the firmware's own compiled Setup form driver and reads the
  values out of its NVRAM stores.
- **[gpu-rma-diagnostics](https://github.com/TIsForThomas/gpu-rma-diagnostics)** -
  collect everything a GPU vendor asks for on an RMA, from a production node that
  may already be half broken, without leaving the node changed. Every state change
  registers an undo that runs from a trap on any exit.
- **[win11-kvm-lab](https://github.com/TIsForThomas/win11-kvm-lab)** - a
  reproducible Windows 11 IoT LTSC VM on KVM with Secure Boot and emulated TPM 2.0,
  SSH-drivable and rebuildable from scripts. Built so Windows tooling could be
  tested from a Linux host.
- **[gpu-scripts](https://github.com/TIsForThomas/Gpu-scripts)** - quick NVIDIA and
  AMD node health checks: driver state, thermals, power, ECC counters, CUDA
  bandwidth, plus log collection.

Also a handful of small Python utilities from earlier on, left up because
pretending you started at the deep end helps nobody.

### Working on

Kubernetes and Terraform, and enough electrical engineering to read a schematic
properly: PCB fundamentals, signal integrity, DC power delivery, and bench
testing with something better than guesswork.
