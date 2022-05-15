# Virtual Machines

[Virtual machines](https://en.wikipedia.org/wiki/Virtual_machine) and similar tools like containers let you emulate a whole computer system, including the operating system. This can be useful for creating an isolated environment for testing, development, or exploration (e.g. running potentially malicious code).

[Vagrant](https://www.vagrantup.com/) is a tool that lets you describe machine configurations (operating system, services, packages, etc.) in code, and then instantiate VMs with a simple `vagrant up`. [Docker](https://www.docker.com/) is conceptually similar but it uses containers instead.

You can also rent virtual machines on the cloud, and it's a nice way to get instant access to:

- A cheap always-on machine that has a public IP address, used to host services
- A machine with a lot of CPU, disk, RAM, and/or GPU
- Many more machines than you physically have access to (billing is often by the second, so if you want a lot of computing for a short amount of time, it's feasible to rent 1000 computers for a couple of minutes)

Popular services include 
- [Amazon AWS](https://aws.amazon.com/)
- [DigitalOcean](https://www.digitalocean.com/)
- [Google Cloud](https://cloud.google.com/)
- [Microsoft Azure](https://azure.microsoft.com/)

If you're a member of MIT CSAIL, you can get free VMs for research purposes through the [CSAIL OpenStack instance](https://tig.csail.mit.edu/shared-computing/open-stack/).

## Docker 
Docker is based on a more general concept called containers. The main difference between containers and virtual machines is that virtual machines will execute an entire OS stack, including the kernel, even if the kernel is the same as the host machine. Unlike VMs, containers avoid running another instance of the kernel and instead share the kernel with the host. In Linux, this is achieved through a mechanism called LXC, and it makes use of a series of isolation mechanisms to spin up a program that thinks it's running on its own hardware but it's actually sharing the hardware and kernel with the host. Thus, containers have a lower overhead than a full VM. 
On the flip side, containers have a weaker isolation and only work if the host runs the same kernel. For instance if you run Docker on macOS, Docker needs to spin up a Linux virtual machine to get an initial Linux kernel and thus the overhead is still significant. Lastly, Docker is a specific implementation of containers and it is tailored for software deployment. Because of this, it has some quirks: for example, Docker containers will not persist any form of storage between reboots by default.

## What are the advantages and disadvantages of each OS and how can we choose between them (e.g. choosing the best Linux distribution for our purposes)?

Regarding Linux distros, even though there are many, many distros, most of them will behave fairly identically for most use cases. 
Most of Linux and UNIX features and inner workings can be learned in any distro. 
A fundamental difference between distros is how they deal with package updates. 
Some distros, like Arch Linux, use a rolling update policy where things are bleeding-edge but things might break every so often. On the other hand, some distros like Debian, CentOS or Ubuntu LTS releases are much more conservative with releasing updates in their repositories so things are usually more stable at the expense of sacrificing newer features. 
Our recommendation for an easy and stable experience with both desktops and servers is to use Debian or Ubuntu.

Mac OS is a good middle point between Windows and Linux that has a nicely polished interface. However, Mac OS is based on BSD rather than Linux, so some parts of the system and commands are different.
An alternative worth checking is FreeBSD. Even though some programs will not run on FreeBSD, the BSD ecosystem is much less fragmented and better documented than Linux. 
We discourage Windows for anything but for developing Windows applications or if there is some deal breaker feature that you need, like good driver support for gaming. 

For dual boot systems, we think that the most working implementation is macOS' bootcamp and that any other combination can be problematic  on the long run, specially if you combine it with other features like disk encryption. 

