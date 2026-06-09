# GrepSetDIBits(OPTAPIDCOBJ &,HBITMAP__ *,uint,uint,umptr_r<uchar> &,tagBITMAPINFO *,uint,uint,void *)

- ea: `0x140113840`
- end: `0x140113c19`
- name: `?GrepSetDIBits@@YAHAEAVOPTAPIDCOBJ@@PEAUHBITMAP__@@IIAEAV?$umptr_r@E@@PEAUtagBITMAPINFO@@IIPEAX@Z`
- size: `985`
- prototype: `__int64 __usercall@<rax>(OPTAPIDCOBJ *this@<rcx>, __int64, __int64, int, int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401156c8`
- `0x140329590`

## callees

- `0x140054780`
- `0x140054a74`
- `0x14005b820`
- `0x140062138`
- `0x1400684f8`
- `0x14009a40c`
- `0x1400acb4c`
- `0x140112314`
- `0x140113840`

## import_xrefs

- `win32kbase!GreSelectPalette` at `0x1401139b1`
- `win32kbase!GreSelectPalette` at `0x140113a9e`
- `win32kbase!GreSelectPalette` at `0x140113b21`
- `win32kbase!GreSelectPalette` at `0x1401139b1`
- `win32kbase!GreSelectPalette` at `0x140113a9e`
- `win32kbase!GreSelectPalette` at `0x140113b21`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401138ac`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1401138ac`
- `win32kbase!HmgShareLock` at `0x1401138f9`
- `win32kbase!HmgShareLock` at `0x1401138f9`
- `win32kbase!PushThreadGuardedObject` at `0x1401138e1`
- `win32kbase!PushThreadGuardedObject` at `0x1401138e1`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140113940`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140113ae6`
- `win32kbase!EngSetLastError` at `0x140113acd`
- `win32kbase!EngSetLastError` at `0x140113b50`
- `win32kbase!EngSetLastError` at `0x140113bff`
- `win32kbase!EngSetLastError` at `0x140113acd`
- `win32kbase!EngSetLastError` at `0x140113b50`
- `win32kbase!EngSetLastError` at `0x140113bff`
- `win32kbase!GrepDeleteDC` at `0x140113ab7`
- `win32kbase!GrepDeleteDC` at `0x140113b35`
- `win32kbase!GrepDeleteDC` at `0x140113ab7`
- `win32kbase!GrepDeleteDC` at `0x140113b35`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x140113954`
- `win32kbase!?GrepCreateCompatibleDC@@YAPEAUHDC__@@AEAVOPTAPIDCOBJ@@@Z` at `0x140113954`
- `win32kbase!GreSelectBitmap` at `0x1401139e1`
- `win32kbase!GreSelectBitmap` at `0x140113a81`
- `win32kbase!GreSelectBitmap` at `0x1401139e1`
- `win32kbase!GreSelectBitmap` at `0x140113a81`

## pseudocode

```c

```
