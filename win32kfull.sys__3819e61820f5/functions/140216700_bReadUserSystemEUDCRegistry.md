# bReadUserSystemEUDCRegistry

- ea: `0x140216700`
- end: `0x140216a3a`
- name: `bReadUserSystemEUDCRegistry`
- size: `826`
- prototype: `__int64 __fastcall(wchar_t *Dst)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140216200`

## callees

- `0x1401a22fc`
- `0x140216700`
- `0x140216a40`
- `0x140216b78`
- `0x14029e7cc`

## import_xrefs

- `ntoskrnl!RtlCreateRegistryKey` at `0x1402169a7`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1402169bc`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1402169a7`
- `ntoskrnl!RtlCreateRegistryKey` at `0x1402169bc`
- `ntoskrnl!wcsncpy_s` at `0x140216a0a`
- `ntoskrnl!wcsncpy_s` at `0x140216a0a`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14021685e`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14021685e`
- `ntoskrnl!_wcsicmp` at `0x14021698a`
- `ntoskrnl!_wcsicmp` at `0x14021698a`
- `ntoskrnl!wcsrchr` at `0x140216957`
- `ntoskrnl!wcsrchr` at `0x140216957`
- `ntoskrnl!ZwClose` at `0x14021690d`
- `ntoskrnl!ZwClose` at `0x14021691e`
- `ntoskrnl!ZwClose` at `0x14021690d`
- `ntoskrnl!ZwClose` at `0x14021691e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402169ec`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402169ec`
- `win32kbase!EngSetLastError` at `0x1402168df`
- `win32kbase!EngSetLastError` at `0x1402168f2`
- `win32kbase!EngSetLastError` at `0x1402168df`
- `win32kbase!EngSetLastError` at `0x1402168f2`
- `win32kbase!Win32AllocPoolZInit` at `0x14021672f`
- `win32kbase!Win32AllocPoolZInit` at `0x140216758`
- `win32kbase!Win32AllocPoolZInit` at `0x14021672f`
- `win32kbase!Win32AllocPoolZInit` at `0x140216758`
- `win32kbase!Win32FreePool` at `0x14021689d`
- `win32kbase!Win32FreePool` at `0x1402168ac`
- `win32kbase!Win32FreePool` at `0x14021689d`
- `win32kbase!Win32FreePool` at `0x1402168ac`
- `WIN32K!W32GetSessionState` at `0x1402167e7`
- `WIN32K!W32GetSessionState` at `0x140216966`
- `WIN32K!W32GetSessionState` at `0x1402167e7`
- `WIN32K!W32GetSessionState` at `0x140216966`

## pseudocode

```c

```
