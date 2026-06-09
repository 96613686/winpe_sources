# DrvUpdateRemoteAdapterInfo(tagGRAPHICS_DEVICE *)

- ea: `0x14018fc1c`
- end: `0x14018fec3`
- name: `?DrvUpdateRemoteAdapterInfo@@YAJPEAUtagGRAPHICS_DEVICE@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(struct tagGRAPHICS_DEVICE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14018f010`
- `0x1401f75a4`

## callees

- `0x14009e334`
- `0x1400d4e00`
- `0x1401618b8`
- `0x14018fc1c`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14018fe2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018fe2b`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018fd1f`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14018fd1f`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018fd8e`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018fd8e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018fd73`
- `ntoskrnl!RtlInitUnicodeString` at `0x14018fd73`
- `ntoskrnl!ObfDereferenceObject` at `0x14018fe42`
- `ntoskrnl!ObfDereferenceObject` at `0x14018fe8b`
- `ntoskrnl!ObfDereferenceObject` at `0x14018fe42`
- `ntoskrnl!ObfDereferenceObject` at `0x14018fe8b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018fc83`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14018fc83`
- `WIN32K!W32GetSessionState` at `0x14018fc5a`
- `WIN32K!W32GetSessionState` at `0x14018fc5a`

## pseudocode

```c

```
