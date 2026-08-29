---
name: update-cross-toolchain-configs
description: Workflow command scaffold for update-cross-toolchain-configs in FFmpeg.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-cross-toolchain-configs

Use this workflow when working on **update-cross-toolchain-configs** in `FFmpeg`.

## Goal

Update configuration files for cross-compilation toolchains across multiple architectures.

## Common Files

- `images/base-linuxmips64/ct-ng-config`
- `images/base-linuxppc64/ct-ng-config`
- `images/base-linuxriscv64/ct-ng-config`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit ct-ng-config files for each relevant architecture under images/base-linux*/ct-ng-config.
- Commit changes with a message describing the toolchain update or feature enablement.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.