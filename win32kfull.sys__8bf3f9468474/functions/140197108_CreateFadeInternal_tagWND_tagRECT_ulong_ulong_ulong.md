# CreateFadeInternal(tagWND *,tagRECT *,ulong,ulong,ulong)

- ea: `0x140197108`
- end: `0x140197746`
- name: `?CreateFadeInternal@@YAPEAUHDC__@@PEAUtagWND@@PEAUtagRECT@@KKK@Z`
- size: `1598`
- prototype: `HDC __usercall@<rax>(struct tagWND *@<rcx>, struct tagRECT *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400a75a4`
- `0x14010a2c0`
- `0x14029febc`

## callees

- `0x14001aac0`
- `0x14002da38`
- `0x14008abf8`
- `0x14008acd0`
- `0x14008fbe8`
- `0x14008fd6c`
- `0x1400905bc`
- `0x140093450`
- `0x140096168`
- `0x1400a5858`
- `0x1400bcaa0`
- `0x1400c138c`
- `0x140197108`
- `0x140197910`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `win32kbase!GreCreateCompatibleDC` at `0x1401972bc`
- `win32kbase!GreCreateCompatibleDC` at `0x1401972bc`
- `win32kbase!GreSetDCOwnerEx` at `0x1401972df`
- `win32kbase!GreSetDCOwnerEx` at `0x1401976eb`
- `win32kbase!GreSetDCOwnerEx` at `0x1401972df`
- `win32kbase!GreSetDCOwnerEx` at `0x1401976eb`
- `win32kbase!GreCleanDC` at `0x14019717e`
- `win32kbase!GreCleanDC` at `0x14019717e`
- `win32kbase!GreSetLayout` at `0x140197197`
- `win32kbase!GreSetLayout` at `0x1401976cd`
- `win32kbase!GreSetLayout` at `0x140197197`
- `win32kbase!GreSetLayout` at `0x1401976cd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401973dc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401973dc`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1401973f5`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1401973f5`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14019744d`
- `win32kbase!GreGetScaledLogPixels` at `0x14019750d`
- `win32kbase!GreGetScaledLogPixels` at `0x1401975d2`
- `win32kbase!GreGetScaledLogPixels` at `0x14019750d`
- `win32kbase!GreGetScaledLogPixels` at `0x1401975d2`
- `win32kbase!GreSelectBitmap` at `0x1401976a5`
- `win32kbase!GreSelectBitmap` at `0x1401976a5`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140197546`
- `win32kbase!LogicalToPhysicalDPIPoint` at `0x140197546`
- `WIN32K!W32GetUserSessionState` at `0x140197151`
- `WIN32K!W32GetUserSessionState` at `0x14019722c`
- `WIN32K!W32GetUserSessionState` at `0x1401972a5`
- `WIN32K!W32GetUserSessionState` at `0x1401973a4`
- `WIN32K!W32GetUserSessionState` at `0x1401973c5`
- `WIN32K!W32GetUserSessionState` at `0x14019746f`
- `WIN32K!W32GetUserSessionState` at `0x140197499`
- `WIN32K!W32GetUserSessionState` at `0x140197151`
- `WIN32K!W32GetUserSessionState` at `0x14019722c`
- `WIN32K!W32GetUserSessionState` at `0x1401972a5`
- `WIN32K!W32GetUserSessionState` at `0x1401973a4`
- `WIN32K!W32GetUserSessionState` at `0x1401973c5`
- `WIN32K!W32GetUserSessionState` at `0x14019746f`
- `WIN32K!W32GetUserSessionState` at `0x140197499`

## pseudocode

```c

```
