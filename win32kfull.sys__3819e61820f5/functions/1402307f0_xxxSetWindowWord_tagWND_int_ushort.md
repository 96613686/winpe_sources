# xxxSetWindowWord(tagWND *,int,ushort)

- ea: `0x1402307f0`
- end: `0x140230d10`
- name: `?xxxSetWindowWord@@YAGPEAUtagWND@@HG@Z`
- size: `1312`
- prototype: `unsigned __int16 __fastcall(struct tagWND *, int, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140230760`

## callees

- `0x1400c2a10`
- `0x1402307f0`
- `0x1402913f0`
- `0x1402e920c`
- `0x1403d2204`

## import_xrefs

- `ntoskrnl!KeDetachProcess` at `0x140230b13`
- `ntoskrnl!KeDetachProcess` at `0x140230b7b`
- `ntoskrnl!KeDetachProcess` at `0x140230cd8`
- `ntoskrnl!KeDetachProcess` at `0x140230b13`
- `ntoskrnl!KeDetachProcess` at `0x140230b7b`
- `ntoskrnl!KeDetachProcess` at `0x140230cd8`
- `ntoskrnl!KeAttachProcess` at `0x14023093a`
- `ntoskrnl!KeAttachProcess` at `0x140230a6a`
- `ntoskrnl!KeAttachProcess` at `0x14023093a`
- `ntoskrnl!KeAttachProcess` at `0x140230a6a`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140230899`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402308ca`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140230905`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402309bf`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402309f5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140230a35`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140230899`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402308ca`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140230905`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402309bf`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1402309f5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140230a35`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1402308f5`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140230a25`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x1402308f5`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x140230a25`
- `WIN32K!W32GetUserSessionState` at `0x140230a94`
- `WIN32K!W32GetUserSessionState` at `0x140230ab7`
- `WIN32K!W32GetUserSessionState` at `0x140230bf4`
- `WIN32K!W32GetUserSessionState` at `0x140230a94`
- `WIN32K!W32GetUserSessionState` at `0x140230ab7`
- `WIN32K!W32GetUserSessionState` at `0x140230bf4`

## pseudocode

```c

```
