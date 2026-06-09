# NtGdiExtFloodFillImpl(HDC__ *,int,int,ulong,uint)

- ea: `0x140325260`
- end: `0x140326177`
- name: `?NtGdiExtFloodFillImpl@@YAHPEAUHDC__@@HHKI@Z`
- size: `3863`
- prototype: `__int64 __fastcall(Gre::Base *, LONG, LONG, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `43`
- tags: `authz_impersonation`

## callers

- `0x140326b00`

## callees

- `0x140014234`
- `0x1400151b8`
- `0x14004d08c`
- `0x140056bc8`
- `0x14005b820`
- `0x14005d010`
- `0x14005f4f4`
- `0x140067410`
- `0x1400684f8`
- `0x1400697e4`
- `0x140069bc8`
- `0x14006bd2c`
- `0x140077348`
- `0x140079b44`
- `0x14008aa50`
- `0x14009be70`
- `0x1400a4eb4`
- `0x1400a87ec`
- `0x1400aaa28`
- `0x1400ae480`
- `0x140107614`
- `0x140111b88`
- `0x14011ea9c`
- `0x14011ee44`
- `0x14011efa0`
- `0x14011f038`
- `0x14018f558`
- `0x1401acf04`
- `0x1401c8cf4`
- `0x1401cf360`
- `0x1401d5250`
- `0x1401d567c`
- `0x1401e2ed0`
- `0x140213198`
- `0x140231ee4`
- `0x1402691a0`
- `0x140325260`
- `0x14032623c`
- `0x1403266ac`
- `0x1403269e4`
- `0x140326b20`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `win32kbase!UserEnterUserCritSec` at `0x140325459`
- `win32kbase!UserEnterUserCritSec` at `0x140325459`
- `win32kbase!UserLeaveUserCritSec` at `0x1403255c4`
- `win32kbase!UserLeaveUserCritSec` at `0x1403255c4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1403252a1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1403258f9`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1403252a1`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1403258f9`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140325b8b`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140325bd5`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140326010`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140326082`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1403260cf`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140325b8b`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140325bd5`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140326010`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140326082`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x1403260cf`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14032538c`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14032538c`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140325366`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140325366`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14032569a`
- `win32kbase!ulGetNearestIndexFromColorref` at `0x14032569a`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1403258c7`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x1403258c7`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1403259e9`
- `win32kbase!?vSet@RGNOBJ@@QEAAXQEBU_RECTL@@@Z` at `0x1403259e9`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140325a05`
- `win32kbase!?bMerge@RGNOBJ@@QEAAHAEAV1@0E@Z` at `0x140325a05`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140325398`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140325445`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140325563`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x140325578`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x14032558e`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1403255a3`
- `win32kbase!GreReleaseSemaphoreExclusiveInternal` at `0x1403255b8`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140325a23`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140325ef0`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140325a23`
- `win32kbase!?bOffset@RGNOBJ@@QEAAHPEBU_POINTL@@@Z` at `0x140325ef0`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1403257fc`
- `win32kbase!?vSync@PDEVOBJ@@QEAAXPEAU_SURFOBJ@@PEAU_RECTL@@K@Z` at `0x1403257fc`
- `win32kbase!EngSetLastError` at `0x140325fe4`
- `win32kbase!EngSetLastError` at `0x14032603d`
- `win32kbase!EngSetLastError` at `0x140326060`
- `win32kbase!EngSetLastError` at `0x1403260a0`
- `win32kbase!EngSetLastError` at `0x1403260bf`
- `win32kbase!EngSetLastError` at `0x1403260f1`
- `win32kbase!EngSetLastError` at `0x140326132`
- `win32kbase!EngSetLastError` at `0x140325fe4`
- `win32kbase!EngSetLastError` at `0x14032603d`
- `win32kbase!EngSetLastError` at `0x140326060`
- `win32kbase!EngSetLastError` at `0x1403260a0`
- `win32kbase!EngSetLastError` at `0x1403260bf`
- `win32kbase!EngSetLastError` at `0x1403260f1`
- `win32kbase!EngSetLastError` at `0x140326132`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140325626`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x140325626`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1403255ed`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x1403255ed`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x14032571e`
- `win32kbase!?vInitBrush@EBRUSHOBJ@@QEAAXPEAVDC@@PEAVBRUSH@@VXEPALOBJ@@2PEAVSURFACE@@H@Z` at `0x14032571e`
- `win32kbase!GreDCSelectBrush` at `0x1403253e2`
- `win32kbase!GreDCSelectBrush` at `0x140325492`
- `win32kbase!GreDCSelectBrush` at `0x1403253e2`
- `win32kbase!GreDCSelectBrush` at `0x140325492`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x140325b49`
- `win32kbase!?vDelete@EBRUSHOBJ@@QEAAXXZ` at `0x140325b49`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_POINTL@@@Z` at `0x14032579e`
- `win32kbase!?bInside@RGNOBJ@@QEAAHPEAU_POINTL@@@Z` at `0x14032579e`
- `win32kbase!GreDCSelectPen` at `0x14032540c`
- `win32kbase!GreDCSelectPen` at `0x1403254bc`
- `win32kbase!GreDCSelectPen` at `0x14032540c`
- `win32kbase!GreDCSelectPen` at `0x1403254bc`
- `win32kbase!ulIndexToRGB` at `0x140325af8`
- `win32kbase!ulIndexToRGB` at `0x140325af8`

## pseudocode

```c

```
