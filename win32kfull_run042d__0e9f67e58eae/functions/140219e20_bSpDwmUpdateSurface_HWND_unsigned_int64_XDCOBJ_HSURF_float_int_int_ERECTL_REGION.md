# bSpDwmUpdateSurface(HWND__ *,unsigned __int64,XDCOBJ &,HSURF__ *,float,int,int,ERECTL &,REGION *)

- ea: `0x140219e20`
- end: `0x14021a4f0`
- name: `?bSpDwmUpdateSurface@@YAHPEAUHWND__@@_KAEAVXDCOBJ@@PEAUHSURF__@@MHHAEAVERECTL@@PEAVREGION@@@Z`
- size: `1744`
- prototype: `__int64 __fastcall(HWND, unsigned __int64, struct XDCOBJ *, HSURF, float, int, int, struct ERECTL *, struct REGION *)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x14006487c`
- `0x140219b90`

## callees

- `0x14005d010`
- `0x1400684f8`
- `0x14006bd2c`
- `0x14008cfa0`
- `0x14009a40c`
- `0x14009d1d0`
- `0x140112588`
- `0x14011bd90`
- `0x1401bd3b8`
- `0x1401d737c`
- `0x1402051f8`
- `0x140219e20`
- `0x140235784`
- `0x14026db38`
- `0x140342fa0`
- `0x140343080`

## import_xrefs

- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14021a450`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14021a450`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14021a14e`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14021a14e`
- `ntoskrnl!ObDuplicateObject` at `0x14021a09f`
- `ntoskrnl!ObDuplicateObject` at `0x14021a09f`
- `ntoskrnl!MmUnmapViewOfSection` at `0x14021a475`
- `ntoskrnl!MmUnmapViewOfSection` at `0x14021a475`
- `ntoskrnl!MmMapViewOfSection` at `0x14021a19f`
- `ntoskrnl!MmMapViewOfSection` at `0x14021a19f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14021a0db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14021a0db`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140219eb6`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140219eb6`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a15c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a463`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a15c`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021a463`
- `ntoskrnl!ZwClose` at `0x14021a0f3`
- `ntoskrnl!ZwClose` at `0x14021a0f3`
- `ntoskrnl!MmSectionObjectType` at `0x14021a0b1`
- `ntoskrnl!ObfDereferenceObject` at `0x14021a489`
- `ntoskrnl!ObfDereferenceObject` at `0x14021a489`
- `win32kbase!UserReferenceDwmApiPort` at `0x140219f87`
- `win32kbase!UserReferenceDwmApiPort` at `0x140219f87`
- `win32kbase!UserLeaveUserCritSec` at `0x140219f96`
- `win32kbase!UserLeaveUserCritSec` at `0x140219f96`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021a4b7`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021a4b7`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14021a4a7`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021a1ea`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021a1ea`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14021a428`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14021a428`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14021a353`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14021a353`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14021a038`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14021a038`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021a297`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021a297`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021a238`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021a238`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x14021a404`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x14021a404`
- `win32kbase!?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z` at `0x14021a2fa`
- `win32kbase!?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z` at `0x14021a2fa`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021a26c`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021a26c`
- `win32kbase!UserEnterUserCritSecShared` at `0x140219f6c`
- `win32kbase!UserEnterUserCritSecShared` at `0x140219f6c`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021a128`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021a43b`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021a128`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021a43b`
- `win32kbase!UserReferenceDwmProcess` at `0x140219f78`
- `win32kbase!UserReferenceDwmProcess` at `0x140219f78`
- `win32kbase!UserDereferenceDwmApiPort` at `0x14021a010`
- `win32kbase!UserDereferenceDwmApiPort` at `0x14021a010`
- `win32kbase!UserDereferenceDwmProcess` at `0x14021a109`
- `win32kbase!UserDereferenceDwmProcess` at `0x14021a109`

## pseudocode

```c

```
