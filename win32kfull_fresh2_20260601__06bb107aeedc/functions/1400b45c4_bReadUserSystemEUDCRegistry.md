# bReadUserSystemEUDCRegistry

- ea: `0x1400b45c4`
- end: `0x1400b48fe`
- name: `bReadUserSystemEUDCRegistry`
- size: `826`
- prototype: `__int64 __fastcall(wchar_t *Dst)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400b40c4`

## callees

- `0x1400b45c4`
- `0x1400b4904`
- `0x1400b4a3c`
- `0x14011a60c`
- `0x1402a0c9c`

## import_xrefs

- `ntoskrnl!RtlCreateRegistryKey` at `0x1400b486b`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400b4880`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400b486b`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1400b4880`
- `ntoskrnl!wcsncpy_s` at `0x1400b48ce`
- `ntoskrnl!wcsncpy_s` at `0x1400b48ce`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400b4722`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400b4722`
- `ntoskrnl!_wcsicmp` at `0x1400b484e`
- `ntoskrnl!_wcsicmp` at `0x1400b484e`
- `ntoskrnl!wcsrchr` at `0x1400b481b`
- `ntoskrnl!wcsrchr` at `0x1400b481b`
- `ntoskrnl!ZwClose` at `0x1400b47d1`
- `ntoskrnl!ZwClose` at `0x1400b47e2`
- `ntoskrnl!ZwClose` at `0x1400b47d1`
- `ntoskrnl!ZwClose` at `0x1400b47e2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b48b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b48b0`
- `win32kbase!EngSetLastError` at `0x1400b47a3`
- `win32kbase!EngSetLastError` at `0x1400b47b6`
- `win32kbase!EngSetLastError` at `0x1400b47a3`
- `win32kbase!EngSetLastError` at `0x1400b47b6`
- `win32kbase!Win32AllocPoolZInit` at `0x1400b45f3`
- `win32kbase!Win32AllocPoolZInit` at `0x1400b461c`
- `win32kbase!Win32AllocPoolZInit` at `0x1400b45f3`
- `win32kbase!Win32AllocPoolZInit` at `0x1400b461c`
- `win32kbase!Win32FreePool` at `0x1400b4761`
- `win32kbase!Win32FreePool` at `0x1400b4770`
- `win32kbase!Win32FreePool` at `0x1400b4761`
- `win32kbase!Win32FreePool` at `0x1400b4770`
- `WIN32K!W32GetSessionState` at `0x1400b46ab`
- `WIN32K!W32GetSessionState` at `0x1400b482a`
- `WIN32K!W32GetSessionState` at `0x1400b46ab`
- `WIN32K!W32GetSessionState` at `0x1400b482a`

## pseudocode

```c

```
