# bSpDwmUpdateSurface(HWND__ *,unsigned __int64,XDCOBJ &,HSURF__ *,float,int,int,ERECTL &,REGION *)

- ea: `0x14021a74c`
- end: `0x14021ae3c`
- name: `?bSpDwmUpdateSurface@@YAHPEAUHWND__@@_KAEAVXDCOBJ@@PEAUHSURF__@@MHHAEAVERECTL@@PEAVREGION@@@Z`
- size: `1776`
- prototype: `__int64 __fastcall(HWND, unsigned __int64, struct XDCOBJ *, HSURF, float, int, int, struct ERECTL *, struct REGION *)`
- caller_count: `2`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x14006876c`
- `0x14021a474`

## callees

- `0x14005fb0c`
- `0x140062bf4`
- `0x14006ec10`
- `0x1400704e0`
- `0x140080590`
- `0x140089c08`
- `0x140134fe0`
- `0x1401c0fa8`
- `0x1401d906c`
- `0x1402040b8`
- `0x14021a74c`
- `0x140235334`
- `0x14026a7c8`
- `0x140303af4`
- `0x140341ff0`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14021ad9c`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x14021ad9c`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14021aa90`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x14021aa90`
- `ntoskrnl!ObDuplicateObject` at `0x14021a9dd`
- `ntoskrnl!ObDuplicateObject` at `0x14021a9dd`
- `ntoskrnl!MmUnmapViewOfSection` at `0x14021adc1`
- `ntoskrnl!MmUnmapViewOfSection` at `0x14021adc1`
- `ntoskrnl!MmMapViewOfSection` at `0x14021aae2`
- `ntoskrnl!MmMapViewOfSection` at `0x14021aae2`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14021aa1c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14021aa1c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14021a7e7`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14021a7e7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021aa9e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021adaf`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021aa9e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14021adaf`
- `ntoskrnl!ZwClose` at `0x14021aa34`
- `ntoskrnl!ZwClose` at `0x14021aa34`
- `ntoskrnl!MmSectionObjectType` at `0x14021a9f2`
- `ntoskrnl!ObfDereferenceObject` at `0x14021add5`
- `ntoskrnl!ObfDereferenceObject` at `0x14021add5`
- `win32kbase!UserReferenceDwmApiPort` at `0x14021a8bd`
- `win32kbase!UserReferenceDwmApiPort` at `0x14021a8bd`
- `win32kbase!UserLeaveUserCritSec` at `0x14021a8cc`
- `win32kbase!UserLeaveUserCritSec` at `0x14021a8cc`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021ae03`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x14021ae03`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14021adf3`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021ab31`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x14021ab31`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14021ad74`
- `win32kbase!?vDeleteRGNOBJ@RGNOBJ@@QEAAXXZ` at `0x14021ad74`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14021ac9a`
- `win32kbase!?vSetup@XCLIPOBJ@@QEAAXPEAVREGION@@AEBVERECTL@@H@Z` at `0x14021ac9a`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14021a978`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x14021a978`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021abda`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14021abda`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021ab7f`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x14021ab7f`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x14021ad50`
- `win32kbase!?bUnMap@SURFREFVIEW@@QEAAHXZ` at `0x14021ad50`
- `win32kbase!?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z` at `0x14021ac41`
- `win32kbase!?bMap@SURFREFVIEW@@QEAAHPEAU_SURFOBJ@@@Z` at `0x14021ac41`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021abaf`
- `win32kbase!?vUnrefPalette@XEPALOBJ@@QEAAXXZ` at `0x14021abaf`
- `win32kbase!UserEnterUserCritSecShared` at `0x14021a8a2`
- `win32kbase!UserEnterUserCritSecShared` at `0x14021a8a2`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021aa6a`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021ad87`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021aa6a`
- `win32kbase!IsSURFMEMMappingEnabled` at `0x14021ad87`
- `win32kbase!UserReferenceDwmProcess` at `0x14021a8ae`
- `win32kbase!UserReferenceDwmProcess` at `0x14021a8ae`
- `win32kbase!UserDereferenceDwmApiPort` at `0x14021a94b`
- `win32kbase!UserDereferenceDwmApiPort` at `0x14021a94b`
- `win32kbase!UserDereferenceDwmProcess` at `0x14021aa4d`
- `win32kbase!UserDereferenceDwmProcess` at `0x14021aa4d`

## pseudocode

```c

```
