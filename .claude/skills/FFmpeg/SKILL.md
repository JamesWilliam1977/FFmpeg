```markdown
# FFmpeg Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns used in the FFmpeg repository, which is primarily written in TypeScript without a specific framework. You'll learn the project's coding conventions, how to manage cross-compilation toolchain configurations, and how to structure and run tests. This guide is ideal for contributors looking to maintain code consistency and follow established workflows.

## Coding Conventions

### File Naming
- **Style:** kebab-case
- **Example:**  
  ```
  video-encoder.ts
  audio-decoder.test.ts
  ```

### Import Style
- **Style:** Relative imports
- **Example:**
  ```typescript
  import { encodeFrame } from './video-encoder';
  import { decodeAudio } from '../audio/audio-decoder';
  ```

### Export Style
- **Style:** Named exports
- **Example:**
  ```typescript
  // video-encoder.ts
  export function encodeFrame(frame: Frame): EncodedFrame { ... }
  ```

## Workflows

### Update Cross Toolchain Configs
**Trigger:** When someone wants to update or enable features in cross-compilation toolchains for multiple architectures (e.g., mips64, ppc64, riscv64).  
**Command:** `/update-cross-toolchain-configs`

1. Edit the `ct-ng-config` files for each relevant architecture:
    - `images/base-linuxmips64/ct-ng-config`
    - `images/base-linuxppc64/ct-ng-config`
    - `images/base-linuxriscv64/ct-ng-config`
2. Make the necessary changes to update the toolchain configuration or enable new features.
3. Commit your changes with a descriptive message, such as:
    ```
    Update mips64 and ppc64 toolchain configs: enable LTO
    ```
4. Push your changes and open a pull request if required.

**Example:**
```bash
# Edit the config for mips64
vim images/base-linuxmips64/ct-ng-config

# After editing, commit your changes
git add images/base-linuxmips64/ct-ng-config
git commit -m "Update mips64 toolchain: enable newlib support"
git push
```

## Testing Patterns

- **Framework:** Unknown (no specific framework detected)
- **File Pattern:** Test files are named with the `.test.` infix.
    - Example: `video-encoder.test.ts`
- **Typical Structure:**  
  Test files are placed alongside implementation files or in dedicated test directories.  
  Example:
  ```
  src/
    video-encoder.ts
    video-encoder.test.ts
  ```

## Commands

| Command                           | Purpose                                                         |
|------------------------------------|-----------------------------------------------------------------|
| /update-cross-toolchain-configs    | Update or enable features in cross-compilation toolchain configs |
```
