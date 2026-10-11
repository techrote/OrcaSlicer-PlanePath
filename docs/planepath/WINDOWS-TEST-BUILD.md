# Windows x64 PlanePath test build

This is a development/testing build of the PlanePath derivative, **not an official OrcaSlicer release**.

## Scope at this checkpoint

The `main` source at `b3f021e44764655352e348532de8e47b6d3ff485` contains accepted PP-001/PP-002 work:
- real upstream OrcaSlicer source with a local build/CI baseline;
- native Hilbert/PlanePath conformance fixtures and integration tests.

**Do not expect a dynamic Lua pattern selector or user-installable curve packages here.** Those are scheduled in later PP-003–PP-017 issues. This build exercises the current native baseline and demonstrates that the fork packages and launches.

## Download and launch

1. Open [PlanePath Windows x64 Test Build Actions](../../actions/workflows/planepath_windows_test_build.yml).
2. Select a successful run on `test-build/windows-x64-20261011` (or a later opted-in `test-build/**` branch).
3. Under *Artifacts*, download the `OrcaSlicer_Windows_*_x64_portable` artifact. GitHub requires login to download Actions artifacts. An installer artifact may also be present, but the portable form is preferred for a first test.
4. Extract the downloaded artifact into a **new directory**, preserving its complete file/directory layout. Run `OrcaSlicer.exe` from the extracted application directory. Do not launch the executable without its bundled resources and DLLs.
5. Back up your existing OrcaSlicer profiles/projects before experimenting; use the portable/test build separately from your everyday installation.

The portable artifact is uploaded by the upstream-derived `build_orca.yml` process. The output directory is `build/OrcaSlicer` and includes the application and required resources. Artifacts expire under the repository's GitHub Actions retention policy.

## Acceptance / smoke checks

- CI: Windows build-script test suite passes.
- CI: Windows x64 build succeeds; the portable application artifact is nonempty.
- CI: the `[FillPlanePath]` focused suite and the broader OrcaSlicer unit-test suite pass (test job is in the same workflow).
- Local Windows GUI: application launches with resources, the normal profile wizard opens, and a basic STL imports and slices.
- Local geometry: slice a simple rectangular object with native Hilbert where supported, then a complex/holed object; compare g-code preview and print estimates against a stock OrcaSlicer build. Verify ordinary non-PlanePath slicing still works.
- Do **not** use experimental test output for unattended printing without inspecting G-code and first-layer behaviour.

Use the action run's commit SHA when filing bugs, and attach screenshots plus an STL/3MF or minimal reproduction where useful. This is an unsigned development build, not a published/signed release package.
