# Fuzzing experiments

This directory is for **actual, reproducible fuzzing work**. Do not add a result merely because a tool was installed or a target was launched.

## Free-first toolchain

- AFL++: coverage-guided fuzzing for instrumented/native targets.
- libFuzzer: in-process coverage-guided fuzzing with compiler instrumentation.
- AddressSanitizer and UndefinedBehaviorSanitizer: help detect memory-safety and undefined-behavior defects during testing.
- GDB: inspect and debug minimized crash cases.

Use a local toy target, a deliberately vulnerable training target, or a target you are authorized to test. Never fuzz a third-party service or production endpoint without explicit permission and a defined scope.

## Minimum experiment record

1. **Question and scope:** what behavior or bug class is being tested, and why is the target authorized?
2. **Target identity:** source revision/commit, build flags, compiler version, architecture, and target hash when relevant.
3. **Harness and corpus:** exact harness, seed corpus origin, mutations/options, and any dictionaries.
4. **Environment:** OS/kernel, tool versions, resource limits, and exact commands.
5. **Result:** executions, duration, coverage data if available, unique crash count, and sanitizer output.
6. **Reproduction:** minimized input, exact replay command, and whether the crash reproduces consistently.
7. **Root cause and impact:** source location and technical explanation. Do not equate a crash with exploitable impact.
8. **Fix and regression:** patch, regression test, and confirmation that the input no longer triggers the defect.
9. **Limitations:** untested configurations, false-positive possibility, and remaining uncertainty.

## Suggested local workflow

```bash
# Build a small owned C target with sanitizers (example flags)
clang -g -O1 -fno-omit-frame-pointer \
  -fsanitize=address,undefined target.c -o target

# Run a harness with AFL++ (example; adapt to the actual target)
afl-clang-fast -g -O1 -fsanitize=address,undefined target.c -o target
mkdir -p corpus findings
afl-fuzz -i corpus -o findings -- ./target @@
```

The commands are examples, not proof that a target or harness already exists in this repository. Keep generated corpora and large crash outputs out of Git unless a small, sanitized reproducer is intentionally part of the research record.
