# Modification Map: external/CLI11

## Source: BlissOS android-x86 reference (external/CLI11)
- BlissOS reference: android-generic/CLI11 commit 23c52b0 (simple cc_library_headers)
- UPSTREAM commits: 
  - cf35f47 (initial KhillOS port - basic Android.bp)
  - d63ebed (AOSP 17 conventions - extended Android.bp)
- Upstream base: CLIUtils/CLI11 v2.7.2 (tag cbd58a3)

## Modifications Applied to UPSTREAM/external_CLI11 (khillos-17 branch)

### 1. Android.bp Build System (EXTENDED from BlissOS)
**File:** `Android.bp` (extended from BlissOS version)
- BlissOS: Basic `cc_library_headers` with `vendor_available: true`
- **UPSTREAM:** Extended with AOSP 17 conventions (reference: external/fmtlib/Android.bp):
  - Package-level license configuration with `default_applicable_licenses`
  - License module with `visibility: [":__subpackages__"]`
  - Added `product_available`, `ramdisk_available`, `vendor_ramdisk_available`, `recovery_available`
  - Added `native_bridge_supported`
  - Added `target` config (linux_bionic + windows)
  - Added `min_sdk_version: "29"`, `sdk_version: "current"`
  - Added `apex_available` with `//apex_available:anyapex` + `//apex_available:platform`
  - Kept `host_supported: true`, `vendor_available: true`
  - Kept `cflags: ["-Wall", "-Werror"]` (from BlissOS)

### 2. AOSP 17 Compliance Metadata Files (NEW)
**Files:** `METADATA`, `NOTICE`, `MODULE_LICENSE_BSD`, `OWNERS`
- METADATA: Package metadata per AOSP external_updater format
- NOTICE: Short license notice
- MODULE_LICENSE_BSD: SPDX identifier for Soong license module
- OWNERS: Standard AOSP OWNERS file

### 3. SPDX Headers - ALREADY PRESENT
All source/header files already have SPDX-License-Identifier: BSD-3-Clause headers.
No additional SPDX headers needed.

## Summary
- **Total files modified:** 5 (Android.bp + 4 new metadata files)
- **Source files unchanged:** Yes (all already have SPDX headers)
- **Logic/behavior changes:** None
- **Build system changes:** Extended Android.bp with AOSP 17 conventions (functional equivalent + more)
