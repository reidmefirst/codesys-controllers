# codesys-controllers
A list of all known CoDeSys PLCs and the related programming software along with notes regarding what version, what protocols and ports are used on each.
## background
CoDeSys stands for _Co_ntroller _De_velopment _Sys_tem. It is a 61131 logic runtime used by many different vendors of PLCs. The software handles some programmatic tasks common to logic. While it is not a true operating system (it still relies on some other operating system to run the bare-metal of the PLC, such as vxworks or gnu/linux) it does offer plenty of operating system-like features, such as its own task list, scheduler, memory management, and binary file loader.

A downside to this is that vulnerabilities and attack tools which target one PLC, may end up affecting hundreds of vendors. Since CoDeSys is responsible not only for (somewhat arbitrary) code execution, but also for some custom network protocols that lack authentication for most PLCs, it is a software suite that is ripe for abuse. Such is the case with the Incontroller/Pipedream family of malware. While the malware targets one particular vendor, the tools may be modified ever-so-slightly to target all CoDeSys v3 controllers.

Past scanning and public exploit tools include the nmap scanning module for CoDeSys version 2.

This repository aims to help identify PLCs and other automation controllers which use CoDeSys under the hood. Information should include the make and model of PLC, the version of the runtime used, and the programming ports used to communicate with the CoDeSys runtime.

Some examples: CoDeSys version 2 controllers typically use TCP/1200 for communication. CoDeSys version 3 controllers typically use TCP/11740 and/or UDP/1740. Some vendors use different ports, and this repository should note that where possible.

The controller list in this repo is based on archived data from 3S-Software (now the CoDeSys Group), which used to publish a list of all vendors that used the software.

Since some vendors re-brand the CoDeSys engineering/programming software with their own name, it is worth explicitly mentioning these tools as well. Typically the engineering/programming software has a 'gateway' protocol on TCP/1217, which can be used to remotely access PLCs that are either on the engineering computer's local LAN (if using the non-routable UDP versions of the protocol) or is connected via some other means such as USB or serial links.
