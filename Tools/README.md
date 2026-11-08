# Reverse-engineering and security tools

Free-first setup notes for local learning. A paid product is never required to complete the core path in this repository. Tool availability and licensing can change; verify current terms before use.

## Linux / WSL2

| Tool | Function | Cost note |
|---|---|---|
| [Ghidra](https://github.com/NationalSecurityAgency/ghidra) | GUI disassembler and decompiler | Free and open source |
| [radare2](https://github.com/radareorg/radare2) | CLI disassembler and binary analysis | Free and open source |
| [GDB](https://www.gnu.org/software/gdb/) | Native debugger | Free and open source |
| [jadx](https://github.com/skylot/jadx) | Java/Kotlin APK decompiler | Free and open source |
| [apktool](https://apktool.org/) | Decode/rebuild APK resources | Free and open source |
| [Frida](https://frida.re/) | Dynamic instrumentation | Open source; check deployment constraints |
| [pwntools](https://github.com/Gallopsled/pwntools) | CTF and exploit-development framework | Free and open source |
| [Wireshark](https://www.wireshark.org/) | Packet capture and protocol analysis | Free and open source |

## Windows

| Tool | Function | Cost note |
|---|---|---|
| [Ghidra](https://github.com/NationalSecurityAgency/ghidra) | Disassembler/decompiler | Free and open source |
| [x64dbg](https://x64dbg.com/) | x86/x64 debugger | Free and open source |
| [WinDbg](https://learn.microsoft.com/windows-hardware/drivers/debugger/) | Windows debugging | Microsoft-provided tool; check current distribution terms |
| [radare2](https://github.com/radareorg/radare2) | CLI disassembler/debugger | Free and open source |
| [Sysinternals](https://learn.microsoft.com/sysinternals/) | Windows system diagnostics | Free Microsoft utilities |
| [YARA](https://github.com/VirusTotal/yara) | Pattern matching/classification | Free and open source |
| [Volatility 3](https://github.com/volatilityfoundation/volatility3) | Memory forensics framework | Free and open source |
| [Capstone](https://www.capstone-engine.org/) | Disassembly engine | Free and open source |

## Optional or legacy tools

- IDA Pro and paid Binary Ninja editions are commercial options, not requirements. Use Ghidra or radare2 for the free-first path. Verify the limits and permitted use of any free edition before relying on it.
- OllyDbg and Immunity Debugger are legacy Windows debugging options; prefer maintained tools for new work.
- Cuckoo Sandbox and PEStudio have separate installation, support, and licensing considerations. They are not required for the core path.

## Python environment

Avoid installing packages into an operating-system-managed Python environment with `pip --break-system-packages`. Use a virtual environment or `pipx` instead:

```bash
python3 -m venv .venv
. .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install frida-tools pwntools
```

Or install command-line applications in isolated environments with `pipx`, where appropriate. Keep a record of tool and package versions for reproducible experiments.

## Safe lab practice

Run unknown binaries in a disposable, isolated VM or container without personal credentials or shared folders. Do not analyze or execute malware on a primary workstation. Only inspect systems and targets you own or are authorized to test.
