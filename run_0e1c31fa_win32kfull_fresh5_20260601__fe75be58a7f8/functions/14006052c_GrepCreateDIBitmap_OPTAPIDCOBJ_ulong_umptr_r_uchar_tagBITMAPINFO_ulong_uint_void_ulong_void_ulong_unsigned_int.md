# GrepCreateDIBitmap(OPTAPIDCOBJ &,ulong,umptr_r<uchar> &,tagBITMAPINFO *,ulong,uint,void *,ulong,void *,ulong,unsigned __int64,void * *)

- ea: `0x14006052c`
- end: `0x140060dd0`
- name: `?GrepCreateDIBitmap@@YA?AVSURFREF@@AEAVOPTAPIDCOBJ@@KAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@KIPEAXK3K_KPEAPEAX@Z`
- size: `2212`
- prototype: `__int64 __usercall@<rax>(SURFREF *this@<rcx>, OPTAPIDCOBJ *@<rdx>, __int64, unsigned int, int, __int64, int, __int64, int, __int64, __int64)`
- caller_count: `7`
- callee_count: `21`
- tags: ``

## callers

- `0x140060dd8`
- `0x140060f30`
- `0x140131a44`
- `0x140151b9c`
- `0x140152f20`
- `0x140289980`
- `0x1403225d4`

## callees

- `0x14006052c`
- `0x140062148`
- `0x140062bf4`
- `0x1400661bc`
- `0x14007eef8`
- `0x140093534`
- `0x140134f38`
- `0x140150ff8`
- `0x140155e34`
- `0x1401562a4`
- `0x14019b754`
- `0x1401a546c`
- `0x1401ad688`
- `0x1401ad764`
- `0x1401d906c`
- `0x1401e6db0`
- `0x140249ccc`
- `0x14029ebb0`
- `0x140317908`
- `0x140318010`
- `0x140342240`

## import_xrefs

- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140060abc`
- `win32kbase!??1SURFMEM@@QEAA@XZ` at `0x140060abc`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140060b34`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140060cb4`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140060996`
- `win32kbase!?bCreateDIB@SURFMEM@@QEAAHPEAU_DEVBITMAPINFO@@PEAX1K1_KHHH@Z` at `0x140060996`
- `win32kbase!IsDEVLOCKMappingEnabled` at `0x140060b66`
- `win32kbase!IsDEVLOCKMappingEnabled` at `0x140060b66`
- `win32kbase!EngSetLastError` at `0x140060584`
- `win32kbase!EngSetLastError` at `0x140060a97`
- `win32kbase!EngSetLastError` at `0x140060bd4`
- `win32kbase!EngSetLastError` at `0x140060daa`
- `win32kbase!EngSetLastError` at `0x140060584`
- `win32kbase!EngSetLastError` at `0x140060a97`
- `win32kbase!EngSetLastError` at `0x140060bd4`
- `win32kbase!EngSetLastError` at `0x140060daa`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14006087f`
- `win32kbase!??1PALMEMOBJ@@QEAA@XZ` at `0x14006087f`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140060857`
- `win32kbase!?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z` at `0x140060857`
- `win32kbase!AllocFreeTmpBuffer` at `0x140060a80`
- `win32kbase!AllocFreeTmpBuffer` at `0x140060bbd`
- `win32kbase!AllocFreeTmpBuffer` at `0x140060a80`
- `win32kbase!AllocFreeTmpBuffer` at `0x140060bbd`
- `win32kbase!FreeTmpBuffer` at `0x140060b23`
- `win32kbase!FreeTmpBuffer` at `0x140060c2d`
- `win32kbase!FreeTmpBuffer` at `0x140060b23`
- `win32kbase!FreeTmpBuffer` at `0x140060c2d`
- `win32kbase!?pvBitsSafe@SURFACE@@QEAAPEAXXZ` at `0x140060b7e`
- `win32kbase!?pvBitsSafe@SURFACE@@QEAAPEAXXZ` at `0x140060b7e`

## pseudocode

```c

```
