# Code continuation: scoop-bucket

## Goal and immutable starting point

Continue the code and integration work from the published repository, without needing a local chat, private reports or installed agent skills.

- GitHub repository: `danieljustus/scoop-bucket`.
- Branch: `handoff/20260930-cloud`.
- Base code commit before this document/checkpoint: `98db8d77e149d787ed348435f9de1a0efa5ffe91`.
- Working directory for every command below: the checked-out repository root.
- Publication does not authorize a merge, release, tag, destructive cleanup or paid service.
- Continuation draft PR: #2. Keep it draft until its code/acceptance gates are independently satisfied.

Preserve tracked distribution manifests. Earlier archive/checksum inspection is not repeated by a JSON syntax check. Release immutability and real Windows/Scoop installation remain separate decisions.

## Requirements, decisions and next task

Decide the release-immutability contract before changing publication metadata. Manifest syntax does not prove remote payload immutability or a Windows installation.

Keep products and their optional modules standalone. Preserve exact dependency pins, snake_case contracts, data integrity, authorization and MCP stdout discipline. Keep frozen fixture evidence and original Oracle ancestry unchanged until an explicit preservation design is accepted. Do not rewrite history, force-push, bypass branch protection, delete unique work, close unproven issues or reinterpret a passing subset as complete acceptance.

- No existing candidate PR was recorded for the selected code base.

## Setup and scoped verification

Clone the existing public repository, checkout `handoff/20260930-cloud`, verify its current remote HEAD, and read this file before making changes. Never substitute another branch or silently mix the alternatives.

```sh
git clone --branch handoff/20260930-cloud https://github.com/danieljustus/scoop-bucket.git
cd scoop-bucket
git rev-parse HEAD
git ls-remote --exit-code origin refs/heads/handoff/20260930-cloud
git status --porcelain=v1 -uall
```

Locally observed toolchains: Git 2.54.0, gh 2.102.0, Rust/Cargo 1.98.0, Go 1.27.1, Node 22.22.3, Ruby 2.6.10, Swift 6.4, regular Xcode. Rust repositories pin their toolchain in `rust-toolchain.toml`; honor the checked-in manifests. Go Oracle regeneration must use the exact Go version required by its own manifest/generator, not this observed machine version. Native Swift requires full Xcode. Package-manager caches are rebuildable, not required private inputs.

Scoped reproduction commands, not a claim of the complete product suite:

```sh
python3 -c "import json,subprocess; fs=subprocess.check_output(['git','ls-files','--','*.json'],text=True).splitlines(); assert fs; [json.load(open(p)) for p in fs]; print('JSON manifests checked:',len(fs))"
```

Build command (not claimed executed unless listed in verification):

```sh
No build: tracked Scoop JSON manifests are the distribution input.
```

Start/help command (not executed for live services/devices):

```sh
No service start; Windows/Scoop installation requires separate real-platform verification.
```

For Rust, optional resource limits are `CARGO_BUILD_JOBS=2`, `CARGO_PROFILE_TEST_DEBUG=0`, `CARGO_PROFILE_DEV_DEBUG=0`. `CARGO_TARGET_DIR` may name a fresh build-output directory on stable storage; it is never a source, fixture or configuration input. Do not reuse a build-target directory between code variants when validating changed tests. Each fresh verification uses its own build output. No provider/API secret is required for these scoped mock/unit checks. Do not use real credential, document, broker or router state. Do not enable paid model fallback.

## Dependencies and exclusions

Tracked lockfiles, manifests, generators and fixtures are the reproducible input. Build outputs (`target`, `.build`, `node_modules`, `dist`), dependency caches, coverage output and generated binaries are deliberately excluded and rebuilt. Older unrelated branches, private audit/planning reports, harness settings, personal records, real credential contents, local stores and original unrelated credential-store WIP are excluded, not hidden dependencies of the checks above. No raw chat or private memory is published.

Pinned Git dependency commits found in the selected top-level manifest: none in the inspected top-level manifests. Package managers must resolve these through public repositories; a fresh-checkout failure to fetch any is a concrete reproducibility blocker, not permission to alter a pin.

Real deployments, physical devices and Windows package installation are not part of the scoped local checks. Network access to GitHub and applicable package registries is required for dependency setup. Production access, signing credentials and live-service secrets must be separately supplied through approved secret management, never this repository. No cloud job is launched by this document.



## Verification record

Prepublication secret-pattern/outgoing-history scans succeeded for the selected base. Exact WIP path/byte comparison is required for checkpoint variants. Product-acceptance and target-cloud runtime are **not checked** by these records.

No new source code was changed on this branch; the fresh remote-clone command results will be recorded below.

Fresh remote-clone verification was executed locally on macOS at published checkpoint `21933ab0a3547afb26f71cb1fb1dea45c8cf4f56`. The repository was cloned directly from GitHub, without copied worktree files, stashes or source/configuration overrides. The following scoped command chain exited **0**:

```sh
python3 -c "import json,subprocess; fs=subprocess.check_output(['git','ls-files','--','*.json'],text=True).splitlines(); assert fs; [json.load(open(p)) for p in fs]; print('JSON manifests checked:',len(fs))"
```

Rust compilation used two jobs, disabled dev/test debug info and a distinct build-output directory for each variant. Those output directories contained no required source or fixture inputs. Package manager dependency caches were allowed; application state and credentials were not supplied. This verifies repository-contained inputs and these scoped checks, not every product test or native acceptance criterion. Final documentation changes do not change the tested source; the published final HEAD must still be verified before continuation. Target cloud runtime, permissions, secrets and network gates: **not checked**.

## Copyable continuation request

Work in `danieljustus/scoop-bucket` on `handoff/20260930-cloud`. Verify the exact remote HEAD given by the final publication record, read `docs/handoffs/end-work-cloud.md`, run the setup and scoped checks, then: Decide the release-immutability contract before changing publication metadata. Manifest syntax does not prove remote payload immutability or a Windows installation. Respect all preservation and integration gates above.
