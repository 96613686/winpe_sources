# CreateXlateObject(void *,long,XEPALOBJ,XEPALOBJ,XEPALOBJ,XEPALOBJ,ulong,ulong,ulong,ulong)

- ea: `0x1400512b0`
- end: `0x140051dea`
- name: `?CreateXlateObject@@YAPEAVXLATE@@PEAXJVXEPALOBJ@@111KKKK@Z`
- size: `2874`
- prototype: `_DWORD *(void *, int, __int64, ...)`
- caller_count: `7`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140050d10`
- `0x140054a74`
- `0x140058784`
- `0x140060b1c`
- `0x140062340`
- `0x1400a55dc`
- `0x140306290`

## callees

- `0x1400512b0`
- `0x140051df0`
- `0x14009a40c`
- `0x14019f4d4`
- `0x1401cf394`
- `0x140298e20`
- `0x14029b070`
- `0x140343080`
- `0x140343500`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x14005155b`
- `ntoskrnl!KeIsAttachedProcess` at `0x14005155b`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400517ed`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x1400517ed`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400517df`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400517fc`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400517df`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400517fc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400517d0`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400517d0`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140051572`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140051572`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005131a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005137f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005131a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005137f`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x1400515a4`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x1400515a4`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140051546`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140051546`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400518b2`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400518d5`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14005191c`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x140051976`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400518b2`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x1400518d5`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14005191c`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x140051976`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1400513a0`
- `win32kbase!GreAcquireSemaphoreInternal` at `0x1400513a0`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1400515b0`
- `win32kbase!AllocThreadBufferWithTag` at `0x1400512ee`
- `win32kbase!AllocThreadBufferWithTag` at `0x1400512ee`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051782`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051cea`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051d13`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051d69`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051db9`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051782`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051cea`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051d13`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051d69`
- `win32kbase!?ulDispatchGFPEFunction@XEPALOBJ@@QEAAKW4GFPE_FUNCTION_ID@@K@Z` at `0x140051db9`

## pseudocode

```c

```
