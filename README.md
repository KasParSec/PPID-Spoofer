# PPID-Spoofer
## Overview

This project is a simple Windows PPID (Parent Process ID) spoofing utility implemented in C.
It allows you to create a new process under a parent process of your choice.


## How It Works (High-Level)

Retrieves the Windows system directory (%windir%\System32) and sets it as the working directory.

Initializes a PROC_THREAD_ATTRIBUTE_LIST.

Opens a handle to the target parent process using its PID.

Updates the process attribute list with PROC_THREAD_ATTRIBUTE_PARENT_PROCESS.

Spawns a new process using CreateProcessA with EXTENDED_STARTUPINFO_PRESENT.

The newly created process appears as a child of the specified parent PID.

## Usage
```
ppid_spoofer.exe <Application.exe> <ParentPID>
```
Example
```
ppid_spoofer.exe notepad.exe 4562
```
This launches notepad.exe as if it were spawned by the process with PID 4562.
