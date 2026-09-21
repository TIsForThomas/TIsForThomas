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

**[toast](https://github.com/TIsForThomas/toast)** is a purpose-built suite for
sysprepping and capturing Windows images, on one bootable USB. We send it to
customers. They set a machine up the way they want it, run one file, then boot
the stick. It generalizes Windows, builds the answer file out of their answers,
captures the disk and powers off. Four steps and a one-page guide on the drive.

It doubles as recovery media. Once their image is on the drive, that drive puts
it back onto a unit whose SSD was swapped or died, and the replacement doesn't
have to match the original size. NTFS gets shrunk before the block bitmap is
taken, which is what makes the smaller-disk restore possible at all. Shell and
PowerShell, 56 tests against a built ISO.

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

### Testing

Everything at the production level here is built with the assistance of Claude Code 
via a command line Ubuntu Linux server. The future of software development, and really 
any and all computer management, is AI with human oversight.

### Learning

Electrical engineering fundamentals: PCB design, schematics, signal integrity,
DC power delivery. Kubernetes, Terraform, Ansible.
