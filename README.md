## Thomas Nelson

Infrastructure engineer. Most of the work is troubleshooting: finding out why a
machine, a fleet or an image does not do what it should, and then building the
tooling that makes the answer repeatable instead of a one-time fix. That spans
firmware and BIOS, provisioning and imaging, GPU and accelerator hardware, and
the Linux and Windows sides of each.

Currently a Hardware Applications Engineer at an industrial and medical computer
manufacturer. Internally that is the deployment and diagnostics infrastructure
used by order fulfillment and RMA, and the escalation point for hardware, software
and compatibility problems across the product lines. Externally it is the
technical side of sales and customer support: pre-sales evaluations and the
blockers attached to them, software partner certifications, and working with
customers on OS images and configurations that have to satisfy their own
regulatory and operational requirements.

Previously ran hardware operations for 128-node production GPU clusters serving
customer AI training and inference workloads, covering fleet-wide firmware
campaigns, BMC and IPMI management, InfiniBand and RoCE fabric, and bare-metal
provisioning with MAAS. Two of the projects below come from that period.

### Projects

**[toast](https://github.com/TIsForThomas/toast)**
A bootable USB kit sent to customers, who run it on a machine they have set up
themselves. It generalizes the Windows installation, captures the disk with
Clonezilla, and can redeploy that image onto a drive of a different size. Written
to be run once, unattended, by someone who has never seen it before. The
NTFS volume is shrunk before the block bitmap is taken, which is what makes a
restore onto a smaller disk possible, and is returned to full size on every exit
path. Shell and PowerShell, with 56 automated checks that run against a built ISO.

**[ami-bios-settings](https://github.com/TIsForThomas/ami-bios-settings)**
Decodes named BIOS settings from a raw AMI Aptio firmware image and diffs two of
them, so configuration drift between units of the same model can be measured
rather than estimated. Locates the firmware's compiled Setup form driver, recovers
each question's prompt text, NVRAM store and byte offset from its IFR forms, and
reads the values from the store. Includes sequence-based alignment for comparing
different firmware builds, where question IDs and byte offsets are reassigned on
recompile.

**[gpu-rma-diagnostics](https://github.com/TIsForThomas/gpu-rma-diagnostics)**
Collects the system, GPU and vendor diagnostics required for an NVIDIA or AMD RMA
in a single run. Optional field diagnostics require unloading the driver, so any
service stopped or configuration written is registered on a revert stack that runs
from a trap on every exit path, and is recorded in the output archive.

**[win11-kvm-lab](https://github.com/TIsForThomas/win11-kvm-lab)**
A reproducible Windows 11 IoT Enterprise LTSC virtual machine on KVM with Secure
Boot and an emulated TPM 2.0, driven over SSH and rebuildable from scripts. Gives
deployment tooling a Windows target to be tested against from a Linux host.

**[gpu-scripts](https://github.com/TIsForThomas/Gpu-scripts)**
Health checks for NVIDIA and AMD GPU nodes: driver state, thermals, power, ECC
counters, CUDA bandwidth, and log collection.

The remaining public repositories are small Python utilities from earlier
learning projects.

### How these were built

My production projects are built with the assistance of Claude Code. I treat it
as a standard part of the toolchain rather than a novelty, and I expect most
software development to work this way before long. The leverage is substantial,
and it moves the constraint off how quickly code can be written and onto how
carefully it gets verified.

Which is why verification is visible in these repositories rather than assumed.
They ship with test suites that exercise the real scripts against a built
artifact rather than a copy of them, and a defect is reproduced before it is
written down as one.

### Currently working on

Electrical engineering fundamentals including PCB design, schematic reading,
signal integrity and DC power delivery, alongside Kubernetes, Terraform and
Ansible.
