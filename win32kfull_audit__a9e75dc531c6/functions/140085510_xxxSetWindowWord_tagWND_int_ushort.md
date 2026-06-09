# xxxSetWindowWord(tagWND *,int,ushort)

- ea: `0x140085510`
- end: `0x140085a30`
- name: `?xxxSetWindowWord@@YAGPEAUtagWND@@HG@Z`
- size: `1312`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140085480`

## callees

- `0x140085510`
- `0x14008676c`
- `0x1400e8c20`
- `0x1402938dc`
- `0x1403d3204`

## import_xrefs

- `ntoskrnl!KeDetachProcess` at `0x140085833`
- `ntoskrnl!KeDetachProcess` at `0x14008589b`
- `ntoskrnl!KeDetachProcess` at `0x1400859f8`
- `ntoskrnl!KeDetachProcess` at `0x140085833`
- `ntoskrnl!KeDetachProcess` at `0x14008589b`
- `ntoskrnl!KeDetachProcess` at `0x1400859f8`
- `ntoskrnl!KeAttachProcess` at `0x14008565a`
- `ntoskrnl!KeAttachProcess` at `0x14008578a`
- `ntoskrnl!KeAttachProcess` at `0x14008565a`
- `ntoskrnl!KeAttachProcess` at `0x14008578a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400855b9`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400855ea`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140085625`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400856df`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140085715`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140085755`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400855b9`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400855ea`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140085625`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400856df`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140085715`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140085755`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140085615`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140085745`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140085615`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140085745`
- `WIN32K!W32GetUserSessionState` at `0x1400857b4`
- `WIN32K!W32GetUserSessionState` at `0x1400857d7`
- `WIN32K!W32GetUserSessionState` at `0x140085914`
- `WIN32K!W32GetUserSessionState` at `0x1400857b4`
- `WIN32K!W32GetUserSessionState` at `0x1400857d7`
- `WIN32K!W32GetUserSessionState` at `0x140085914`

## pseudocode

```c

```
