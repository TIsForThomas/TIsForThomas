## Thomas Nelson

Infrastructure engineer. I work out why machines don't do what they're supposed
to, then build the tooling so nobody has to work it out twice. Firmware and BIOS,
imaging and provisioning, GPU hardware, Linux and Windows.

Right now I'm a Hardware Applications Engineer at an industrial and medical
computer manufacturer. I own and manage the deployment and diagnostics infrastructure 
every unit on every bench runs on and take the senior escalations. A lot of my week
is customer-facing: pre-sales evaluations, software partner certifications, and
getting customer images and unit configurations to meet their requirements.

Before this I ran hardware operations on 128-node GPU clusters doing customer AI
training. Firmware campaigns, BMC and IPMI, InfiniBand and RoCE, bare-metal
provisioning with MAAS.

### Projects

**[toast](https://github.com/TIsForThomas/toast)** is a USB kit we send to
customers. They run it on a machine they've set up themselves; it syspreps
Windows, captures the disk, and can put that image back onto a smaller drive.
NTFS has to be shrunk before the block bitmap is taken, which is the whole trick.
Shell and PowerShell, 56 tests against a built ISO.

**[ami-bios-settings](https://github.com/TIsForThomas/ami-bios-settings)** reads
named BIOS settings out of a raw AMI Aptio firmware image and diffs two of them.
Finds the compiled Setup form driver, pulls each question's prompt, NVRAM store
and byte offset out of its IFR forms, then reads the value. Also aligns captures
from different firmware builds, where a recompile renumbers everything.

**[gpu-rma-diagnostics](https://github.com/TIsForThomas/gpu-rma-diagnostics)**
gathers what NVIDIA or AMD want for an RMA in one pass. Field diagnostics need the
driver unloaded, so anything it stops or writes goes on a revert stack that fires
from a trap on any exit, and lands in the archive as a record.

**[win11-kvm-lab](https://github.com/TIsForThomas/win11-kvm-lab)** is Windows 11
IoT LTSC on KVM with Secure Boot and an emulated TPM, driven over SSH, rebuilt
from scripts. Gives me a Windows target to test against from Linux.

**[gpu-scripts](https://github.com/TIsForThomas/Gpu-scripts)** is health checks for
NVIDIA and AMD nodes. Driver state, thermals, power, ECC counters, CUDA bandwidth,
log collection.

The other public repos are small Python utilities from earlier learning projects.

### How I build

All my production work is done with Claude Code. It's part of the toolchain now
and I think most development ends up there. It also means I ship more code than I
used to, so I test more of it. These repos come with suites that run the real
scripts, and I reproduce a bug before I write it down as one.

### Learning

Electrical engineering fundamentals: PCB design, schematics, signal integrity,
DC power delivery. Kubernetes, Terraform, Ansible.
