# DrvUpdateRemoteAdapterInfo(tagGRAPHICS_DEVICE *)

- ea: `0x140192dac`
- end: `0x140193053`
- name: `?DrvUpdateRemoteAdapterInfo@@YAJPEAUtagGRAPHICS_DEVICE@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(struct tagGRAPHICS_DEVICE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x14005d990`
- `0x1401f6d44`

## callees

- `0x14008fa44`
- `0x1400ab4f0`
- `0x14015f35c`
- `0x140192dac`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140192fbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192fbb`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140192eaf`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140192eaf`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140192f1e`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140192f1e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140192f03`
- `ntoskrnl!RtlInitUnicodeString` at `0x140192f03`
- `ntoskrnl!ObfDereferenceObject` at `0x140192fd2`
- `ntoskrnl!ObfDereferenceObject` at `0x14019301b`
- `ntoskrnl!ObfDereferenceObject` at `0x140192fd2`
- `ntoskrnl!ObfDereferenceObject` at `0x14019301b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140192e13`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140192e13`
- `WIN32K!W32GetSessionState` at `0x140192dea`
- `WIN32K!W32GetSessionState` at `0x140192dea`

## pseudocode

```c

```
