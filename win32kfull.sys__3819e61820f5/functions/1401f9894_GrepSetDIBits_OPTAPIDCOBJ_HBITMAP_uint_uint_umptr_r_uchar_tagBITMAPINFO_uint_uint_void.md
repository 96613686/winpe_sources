# GrepSetDIBits(OPTAPIDCOBJ &,HBITMAP__ *,uint,uint,umptr_r<uchar> &,tagBITMAPINFO *,uint,uint,void *)

- ea: `0x1401f9894`
- end: `0x1401f9c6d`
- name: `?GrepSetDIBits@@YAHAEAVOPTAPIDCOBJ@@PEAUHBITMAP__@@IIAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@IIPEAX@Z`
- size: `985`
- prototype: `__int64 __usercall@<rax>(OPTAPIDCOBJ *this@<rcx>, __int64, __int64, int, int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401f96f8`
- `0x140328180`

## callees

- `0x14005fb0c`
- `0x140062bf4`
- `0x1400661bc`
- `0x14007eef8`
- `0x14009654c`
- `0x140134f38`
- `0x1401537d0`
- `0x140153ac4`
- `0x1401f9894`

## import_xrefs

- `win32kbase!GreSelectPalette` at `0x1401f9a05`
- `win32kbase!GreSelectPalette` at `0x1401f9af2`
- `win32kbase!GreSelectPalette` at `0x1401f9b75`
- `win32kbase!GreSelectPalette` at `0x1401f9a05`
- `win32kbase!GreSelectPalette` at `0x1401f9af2`
- `win32kbase!GreSelectPalette` at `0x1401f9b75`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401f9900`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401f9900`
- `win32kbase!HmgShareLock` at `0x1401f994d`
- `win32kbase!HmgShareLock` at `0x1401f994d`
- `win32kbase!PushThreadGuardedObject` at `0x1401f9935`
- `win32kbase!PushThreadGuardedObject` at `0x1401f9935`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401f9994`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x1401f9b3a`
- `win32kbase!EngSetLastError` at `0x1401f9b21`
- `win32kbase!EngSetLastError` at `0x1401f9ba4`
- `win32kbase!EngSetLastError` at `0x1401f9c53`
- `win32kbase!EngSetLastError` at `0x1401f9b21`
- `win32kbase!EngSetLastError` at `0x1401f9ba4`
- `win32kbase!EngSetLastError` at `0x1401f9c53`
- `win32kbase!GrepDeleteDC` at `0x1401f9b0b`
- `win32kbase!GrepDeleteDC` at `0x1401f9b89`
- `win32kbase!GrepDeleteDC` at `0x1401f9b0b`
- `win32kbase!GrepDeleteDC` at `0x1401f9b89`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x1401f99a8`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x1401f99a8`
- `win32kbase!GreSelectBitmap` at `0x1401f9a35`
- `win32kbase!GreSelectBitmap` at `0x1401f9ad5`
- `win32kbase!GreSelectBitmap` at `0x1401f9a35`
- `win32kbase!GreSelectBitmap` at `0x1401f9ad5`

## pseudocode

```c

```
