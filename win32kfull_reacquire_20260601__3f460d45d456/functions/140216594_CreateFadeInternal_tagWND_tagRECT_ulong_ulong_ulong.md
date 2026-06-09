# CreateFadeInternal(tagWND *,tagRECT *,ulong,ulong,ulong)

- ea: `0x140216594`
- end: `0x140216bd2`
- name: `?CreateFadeInternal@@YAPEAUHDC__@@PEAUtagWND@@PEAUtagRECT@@KKK@Z`
- size: `1598`
- prototype: `HDC __usercall@<rax>(struct tagWND *@<rcx>, struct tagRECT *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000a7d4`
- `0x140082c80`
- `0x1402a238c`

## callees

- `0x140013478`
- `0x1400135fc`
- `0x140014234`
- `0x140028978`
- `0x140092c40`
- `0x1400a9a54`
- `0x1400ac768`
- `0x1400e2cb0`
- `0x1400e759c`
- `0x14011c80c`
- `0x14011c8e4`
- `0x1401ae48c`
- `0x140216594`
- `0x140216da0`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `win32kbase!GreCreateCompatibleDC` at `0x140216748`
- `win32kbase!GreCreateCompatibleDC` at `0x140216748`
- `win32kbase!GreSetDCOwnerEx` at `0x14021676b`
- `win32kbase!GreSetDCOwnerEx` at `0x140216b77`
- `win32kbase!GreSetDCOwnerEx` at `0x14021676b`
- `win32kbase!GreSetDCOwnerEx` at `0x140216b77`
- `win32kbase!GreCleanDC` at `0x14021660a`
- `win32kbase!GreCleanDC` at `0x14021660a`
- `win32kbase!GreSetLayout` at `0x140216623`
- `win32kbase!GreSetLayout` at `0x140216b59`
- `win32kbase!GreSetLayout` at `0x140216623`
- `win32kbase!GreSetLayout` at `0x140216b59`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140216868`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140216868`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140216881`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x140216881`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1402168d9`
- `win32kbase!GreGetScaledLogPixels` at `0x140216999`
- `win32kbase!GreGetScaledLogPixels` at `0x140216a5e`
- `win32kbase!GreGetScaledLogPixels` at `0x140216999`
- `win32kbase!GreGetScaledLogPixels` at `0x140216a5e`
- `win32kbase!GreSelectBitmap` at `0x140216b31`
- `win32kbase!GreSelectBitmap` at `0x140216b31`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x1402169d2`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x1402169d2`
- `WIN32K!W32GetUserSessionState` at `0x1402165dd`
- `WIN32K!W32GetUserSessionState` at `0x1402166b8`
- `WIN32K!W32GetUserSessionState` at `0x140216731`
- `WIN32K!W32GetUserSessionState` at `0x140216830`
- `WIN32K!W32GetUserSessionState` at `0x140216851`
- `WIN32K!W32GetUserSessionState` at `0x1402168fb`
- `WIN32K!W32GetUserSessionState` at `0x140216925`
- `WIN32K!W32GetUserSessionState` at `0x1402165dd`
- `WIN32K!W32GetUserSessionState` at `0x1402166b8`
- `WIN32K!W32GetUserSessionState` at `0x140216731`
- `WIN32K!W32GetUserSessionState` at `0x140216830`
- `WIN32K!W32GetUserSessionState` at `0x140216851`
- `WIN32K!W32GetUserSessionState` at `0x1402168fb`
- `WIN32K!W32GetUserSessionState` at `0x140216925`

## pseudocode

```c

```
