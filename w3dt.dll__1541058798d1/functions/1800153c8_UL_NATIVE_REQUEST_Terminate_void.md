# UL_NATIVE_REQUEST::Terminate(void)

- ea: `0x1800153c8`
- end: `0x18001542c`
- name: `?Terminate@UL_NATIVE_REQUEST@@SAXXZ`
- size: `100`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001060`
- `0x180015a40`

## callees

- `0x180013544`
- `0x1800153c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800153d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800153d3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015416`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015416`

## pseudocode

```c
void UL_NATIVE_REQUEST::Terminate(void)
{
  DeleteCriticalSection(&UL_NATIVE_REQUEST::sm_csRequestList);
  if ( UL_NATIVE_REQUEST::sm_pachNativeRequests )
  {
    ALLOC_CACHE_HANDLER::`scalar deleting destructor'(UL_NATIVE_REQUEST::sm_pachNativeRequests);
    UL_NATIVE_REQUEST::sm_pachNativeRequests = 0;
  }
  if ( UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush )
    UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush = 0;
  if ( UL_NATIVE_REQUEST::sm_hHttpApi )
  {
    FreeLibrary(UL_NATIVE_REQUEST::sm_hHttpApi);
    UL_NATIVE_REQUEST::sm_hHttpApi = 0;
  }
}

```

## disassembly

```asm
0x1800153c8  sub     rsp, 28h
0x1800153cc  lea     rcx, ?sm_csRequestList@UL_NATIVE_REQUEST@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800153d3  call    cs:__imp_DeleteCriticalSection
0x1800153d9  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; this
0x1800153e0  test    rcx, rcx
0x1800153e3  jz      short loc_1800153F5
0x1800153e5  call    ??_GALLOC_CACHE_HANDLER@@QEAAPEAXI@Z; ALLOC_CACHE_HANDLER::`scalar deleting destructor'(uint)
0x1800153ea  mov     cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x1800153f5  cmp     cs:?sm_pfnHttpDeclarePush@UL_NATIVE_REQUEST@@0P6AKPEAX_KW4_HTTP_VERB@@PEBGPEBDPEAU_HTTP_REQUEST_HEADERS@@@ZEA, 0; ulong (*UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush)(void *,unsigned __int64,_HTTP_VERB,ushort const *,char const *,_HTTP_REQUEST_HEADERS *)
0x1800153fd  jz      short loc_18001540A
0x1800153ff  mov     cs:?sm_pfnHttpDeclarePush@UL_NATIVE_REQUEST@@0P6AKPEAX_KW4_HTTP_VERB@@PEBGPEBDPEAU_HTTP_REQUEST_HEADERS@@@ZEA, 0; ulong (*UL_NATIVE_REQUEST::sm_pfnHttpDeclarePush)(void *,unsigned __int64,_HTTP_VERB,ushort const *,char const *,_HTTP_REQUEST_HEADERS *)
0x18001540a  mov     rcx, cs:?sm_hHttpApi@UL_NATIVE_REQUEST@@0PEAUHINSTANCE__@@EA; hLibModule
0x180015411  test    rcx, rcx
0x180015414  jz      short loc_180015427
0x180015416  call    cs:__imp_FreeLibrary
0x18001541c  mov     cs:?sm_hHttpApi@UL_NATIVE_REQUEST@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * UL_NATIVE_REQUEST::sm_hHttpApi
0x180015427  add     rsp, 28h
0x18001542b  retn
```
