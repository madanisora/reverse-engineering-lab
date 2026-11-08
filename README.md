# Reverse Engineering Lab

A practical workspace for reverse-engineering tooling notes and **separate, reproducible technical experiments**. This repository is intended to grow through analysis artifacts, harnesses, scripts, fuzzing runs, crash reproducers, and root-cause reports—not by duplicating every practice write-up.

## Repository map

| Path | Purpose |
|---|---|
| [`CTF/`](CTF/) | Challenge artifacts retained with source attribution and short pointers to canonical write-ups. |
| [`Tools/`](Tools/README.md) | Free-first tool setup notes. |
| [`Resources/`](Resources/README.md) | Practice, competition, and authorized vulnerability-research resources. |
| [`Fuzzing/`](Fuzzing/README.md) | Fuzzing workflow and the minimum information needed to reproduce an experiment. |

## Relationship to the other repositories

- [`ctf-writeups`](https://github.com/madanisora/ctf-writeups) is the **only canonical home for full independent-practice write-ups** such as XorGate and muhemed crackme. This repository links to those write-ups rather than keeping duplicate copies.
- [`ctf-track-record`](https://github.com/madanisora/ctf-track-record) records official CTF events actually attended. It is not a practice log.
- [`Security-learning-roadmap`](https://github.com/madanisora/Security-learning-roadmap) is the learning reference index, not evidence of completed work.

## Research record standard

For each experiment, record the question, target and authorization, environment, exact tool/compiler versions, commands, input corpus or test case, observed result, relevant logs, artifact hashes, root cause, fix, regression test, and limitations. Do not claim that a crash proves exploitable impact without further analysis.

Use only targets you own or are explicitly authorized to test. Do not commit credentials, private data, access tokens, production crash dumps containing secrets, or artifacts whose redistribution is not permitted.

## Current scope

The challenge archives already present in `CTF/` are retained as supplied. Check the challenge platform's current publication and redistribution rules before sharing those binaries in a public repository. The presence of an archive here does not grant redistribution rights.
