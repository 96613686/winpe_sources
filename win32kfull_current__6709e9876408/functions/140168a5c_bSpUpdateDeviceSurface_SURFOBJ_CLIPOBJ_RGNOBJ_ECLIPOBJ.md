# bSpUpdateDeviceSurface(_SURFOBJ *,_CLIPOBJ * *,RGNOBJ &,ECLIPOBJ *)

- ea: `0x140168a5c`
- end: `0x140168dc5`
- name: `?bSpUpdateDeviceSurface@@YAHPEAU_SURFOBJ@@PEAPEAU_CLIPOBJ@@AEAVRGNOBJ@@PEAVECLIPOBJ@@@Z`
- size: `873`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, struct _CLIPOBJ **, struct RGNOBJ *, struct ECLIPOBJ *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x14014eab4`

## callees

- `0x140066c94`
- `0x140069bc8`
- `0x140077348`
- `0x140079b44`
- `0x14008cfa0`
- `0x140099490`
- `0x14009b430`
- `0x14009d1d0`
- `0x1400ae480`
- `0x140168a5c`
- `0x140168dcc`
- `0x140168e10`
- `0x1401f7a24`
- `0x140304760`
- `0x140343080`

## import_xrefs

- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168ab2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168acd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168adc`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168ab2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168acd`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140168adc`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140168b1e`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140168bba`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140168da2`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140168bae`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140168d96`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140168bae`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140168d96`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140168b87`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140168d6f`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140168b87`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140168d6f`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140168b53`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140168b53`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140168d1b`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x140168d1b`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140168cd5`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140168cd5`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140168cfe`
- `win32kbase!?vSwap@RGNOBJ@@QEAAXPEAV1@@Z` at `0x140168cfe`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140168c5a`
- `win32kbase!?bCopy@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140168c5a`
- `win32kbase!?ReleaseLock@GreInnermostPushLock@@QEBAXXZ` at `0x140168d53`
- `win32kbase!?ReleaseLock@GreInnermostPushLock@@QEBAXXZ` at `0x140168d53`
- `win32kbase!?bEqual@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140168c27`
- `win32kbase!?bEqual@RGNOBJ@@QEAAHAEAV1@@Z` at `0x140168c27`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140168cbc`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140168cbc`

## pseudocode

```c

```
