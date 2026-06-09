# NtGdiExtFloodFillImpl(HDC__ *,int,int,ulong,uint)

- ea: `0x140323e4c`
- end: `0x140324d6d`
- name: `?NtGdiExtFloodFillImpl@@YAHPEAUHDC__@@HHKI@Z`
- size: `3873`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation`

## callers

- `0x1403256f0`

## callees

- `0x140052ec4`
- `0x1400620a8`
- `0x140062bf4`
- `0x140063ee0`
- `0x14006b9d4`
- `0x14006c84c`
- `0x14006d5e4`
- `0x140077d74`
- `0x14007eef8`
- `0x140080590`
- `0x140084b4c`
- `0x14008c42c`
- `0x14008c4c4`
- `0x14008c4fc`
- `0x14008eb28`
- `0x1400905bc`
- `0x140092d48`
- `0x140094418`
- `0x140097e80`
- `0x1400f8e58`
- `0x1400fb65c`
- `0x1401347ac`
- `0x140137980`
- `0x140155c24`
- `0x1401562a4`
- `0x14016c040`
- `0x140183ad8`
- `0x1401b1e94`
- `0x1401cc8e4`
- `0x1401d8c44`
- `0x1401e6150`
- `0x140212938`
- `0x140231324`
- `0x14024bf4c`
- `0x140265c80`
- `0x140303af4`
- `0x140323e4c`
- `0x140324e30`
- `0x1403252a0`
- `0x1403255d8`
- `0x140325710`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `win32kbase!UserEnterUserCritSec` at `0x140324045`
- `win32kbase!UserEnterUserCritSec` at `0x140324045`
- `win32kbase!UserLeaveUserCritSec` at `0x1403241b5`
- `win32kbase!UserLeaveUserCritSec` at `0x1403241b5`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140323e8d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1403244ef`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140323e8d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1403244ef`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324781`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1403247cb`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324c06`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324c78`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324cc5`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324781`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1403247cb`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324c06`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324c78`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140324cc5`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140323f78`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140323f78`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140323f52`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140323f52`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x140324290`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x140324290`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1403244bd`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1403244bd`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1403245df`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1403245df`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1403245fb`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x1403245fb`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140323f84`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140324031`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140324154`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140324169`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14032417f`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140324194`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1403241a9`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140324619`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140324ae6`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140324619`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140324ae6`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1403243f2`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1403243f2`
- `win32kbase!EngSetLastError` at `0x140324bda`
- `win32kbase!EngSetLastError` at `0x140324c33`
- `win32kbase!EngSetLastError` at `0x140324c56`
- `win32kbase!EngSetLastError` at `0x140324c96`
- `win32kbase!EngSetLastError` at `0x140324cb5`
- `win32kbase!EngSetLastError` at `0x140324ce7`
- `win32kbase!EngSetLastError` at `0x140324d28`
- `win32kbase!EngSetLastError` at `0x140324bda`
- `win32kbase!EngSetLastError` at `0x140324c33`
- `win32kbase!EngSetLastError` at `0x140324c56`
- `win32kbase!EngSetLastError` at `0x140324c96`
- `win32kbase!EngSetLastError` at `0x140324cb5`
- `win32kbase!EngSetLastError` at `0x140324ce7`
- `win32kbase!EngSetLastError` at `0x140324d28`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14032421c`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14032421c`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1403241e3`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1403241e3`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140324314`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x140324314`
- `win32kbase!GreDCSelectBrush` at `0x140323fce`
- `win32kbase!GreDCSelectBrush` at `0x14032407e`
- `win32kbase!GreDCSelectBrush` at `0x140323fce`
- `win32kbase!GreDCSelectBrush` at `0x14032407e`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x14032473f`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x14032473f`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_POINTL@@@Z` at `0x140324394`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_POINTL@@@Z` at `0x140324394`
- `win32kbase!GreDCSelectPen` at `0x140323ff8`
- `win32kbase!GreDCSelectPen` at `0x1403240a8`
- `win32kbase!GreDCSelectPen` at `0x140323ff8`
- `win32kbase!GreDCSelectPen` at `0x1403240a8`
- `win32kbase!ulIndexToRGB` at `0x1403246ee`
- `win32kbase!ulIndexToRGB` at `0x1403246ee`

## pseudocode

```c

```
