# EngCreateWnd

- ea: `0x14028d890`
- end: `0x14028de0b`
- name: `EngCreateWnd`
- size: `1403`
- prototype: `WNDOBJ *__stdcall(SURFOBJ *pso, HWND hwnd, WNDOBJCHANGEPROC pfn, FLONG fl, INT iPixelFormat)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14033b4e0`

## callees

- `0x1400ae480`
- `0x1401f7a24`
- `0x14028d890`
- `0x14028de14`
- `0x14028df0c`
- `0x14028df60`
- `0x1402b12ec`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14028d91a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14028d91a`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028d9d8`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028ddba`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028d9d8`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14028ddba`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028d9b3`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028dd95`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028d9b3`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14028dd95`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028daf7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028dbe4`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028dc23`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028daf7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028dbe4`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x14028dc23`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14028dad0`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14028dbbd`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14028dbfc`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14028dad0`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14028dbbd`
- `win32kbase!??0RGNMEMOBJ@@QEAA@XZ` at `0x14028dbfc`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14028d9e4`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14028ddc6`
- `win32kbase!GreCreateSemaphore` at `0x14028dc2f`
- `win32kbase!GreCreateSemaphore` at `0x14028dc2f`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14028db0f`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14028dc62`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14028db0f`
- `win32kbase!?vStamp@REGION@@AEAAXXZ` at `0x14028dc62`
- `win32kbase!?vReferencePdev@PDEVOBJ@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14028dd6c`
- `win32kbase!?vReferencePdev@PDEVOBJ@@QEAAXAEAUSESSION_GLOBALS@Base@Gre@@@Z` at `0x14028dd6c`
- `win32kbase!UserIsUserCritSecIn` at `0x14028d8f9`
- `win32kbase!UserIsUserCritSecIn` at `0x14028d8f9`
- `win32kbase!Win32AllocPoolZInit` at `0x14028da29`
- `win32kbase!Win32AllocPoolZInit` at `0x14028daaf`
- `win32kbase!Win32AllocPoolZInit` at `0x14028db9b`
- `win32kbase!Win32AllocPoolZInit` at `0x14028da29`
- `win32kbase!Win32AllocPoolZInit` at `0x14028daaf`
- `win32kbase!Win32AllocPoolZInit` at `0x14028db9b`
- `WIN32K!W32GetSessionState` at `0x14028d938`
- `WIN32K!W32GetSessionState` at `0x14028d938`

## pseudocode

```c

```
