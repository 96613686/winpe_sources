# DrvUpdateRemoteAdapterInfo(tagGRAPHICS_DEVICE *)

- ea: `0x14018d35c`
- end: `0x14018d603`
- name: `?DrvUpdateRemoteAdapterInfo@@YAJPEAUtagGRAPHICS_DEVICE@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(struct tagGRAPHICS_DEVICE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14018c750`
- `0x1401f7504`

## callees

- `0x140098c44`
- `0x1400c5dc0`
- `0x14015e96c`
- `0x14018d35c`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14018d56b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018d56b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018d45f`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018d45f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018d4ce`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018d4ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018d4b3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018d4b3`
- `ntoskrnl!ObfDereferenceObject` at `0x14018d582`
- `ntoskrnl!ObfDereferenceObject` at `0x14018d5cb`
- `ntoskrnl!ObfDereferenceObject` at `0x14018d582`
- `ntoskrnl!ObfDereferenceObject` at `0x14018d5cb`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018d3c3`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018d3c3`
- `WIN32K!W32GetSessionState` at `0x14018d39a`
- `WIN32K!W32GetSessionState` at `0x14018d39a`

## pseudocode

```c

```
