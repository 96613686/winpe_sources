# CWlanProfileStore::~CWlanProfileStore(void)

- ea: `0x180029bf4`
- end: `0x180029cc1`
- name: `??1CWlanProfileStore@@UEAA@XZ`
- size: `205`
- prototype: `void __fastcall(CWlanProfileStore *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180029f00`

## callees

- `0x18000cfd4`
- `0x180011124`
- `0x180029bf4`
- `0x18002bf24`
- `0x18002c6ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c76`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029c1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029c98`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029cab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029c1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029c98`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029cab`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029c61`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180029c61`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180029c54`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180029c54`

## pseudocode

```c
void __fastcall CWlanProfileStore::~CWlanProfileStore(CWlanProfileStore *this)
{
  BOOL v2; // eax

  *(_QWORD *)this = &CWlanProfileStore::`vftable'{for `CProfileStore'};
  *((_QWORD *)this + 1) = &CWlanProfileStore::`vftable'{for `CServiceStatusListener'};
  CWlanProfileStore::UninitializeWlan(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 872));
  ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::RemoveAll((char *)this + 800);
  *((_QWORD *)this + 30) = &CServiceMonitor::`vftable';
  if ( *((_QWORD *)this + 97) )
  {
    if ( *((_QWORD *)this + 99) )
      UnsubscribeServiceChangeNotifications();
    v2 = CloseServiceHandle(*((SC_HANDLE *)this + 97));
    *((_QWORD *)this + 97) = 0;
    if ( !v2 )
      GetLastError();
  }
  ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll((char *)this + 184);
  ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll((char *)this + 136);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>((char *)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &CProfileStore::`vftable';
}

```

## disassembly

```asm
0x180029bf4  push    rbx
0x180029bf6  sub     rsp, 20h
0x180029bfa  mov     rbx, rcx
0x180029bfd  lea     rax, ??_7CWlanProfileStore@@6BCProfileStore@@@; const CWlanProfileStore::`vftable'{for `CProfileStore'}
0x180029c04  mov     [rcx], rax
0x180029c07  lea     rax, ??_7CWlanProfileStore@@6BCServiceStatusListener@@@; const CWlanProfileStore::`vftable'{for `CServiceStatusListener'}
0x180029c0e  mov     [rcx+8], rax
0x180029c12  call    ?UninitializeWlan@CWlanProfileStore@@IEAAXXZ; CWlanProfileStore::UninitializeWlan(void)
0x180029c17  lea     rcx, [rbx+368h]; lpCriticalSection
0x180029c1e  call    cs:__imp_DeleteCriticalSection
0x180029c24  lea     rcx, [rbx+320h]
0x180029c2b  call    ?RemoveAll@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@QEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::RemoveAll(void)
0x180029c30  lea     rax, ??_7CServiceMonitor@@6B@; const CServiceMonitor::`vftable'
0x180029c37  mov     [rbx+0F0h], rax
0x180029c3e  cmp     qword ptr [rbx+308h], 0
0x180029c46  jz      short loc_180029C7C
0x180029c48  mov     rcx, [rbx+318h]
0x180029c4f  test    rcx, rcx
0x180029c52  jz      short loc_180029C5A
0x180029c54  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180029c5a  mov     rcx, [rbx+308h]; hSCObject
0x180029c61  call    cs:__imp_CloseServiceHandle
0x180029c67  mov     qword ptr [rbx+308h], 0
0x180029c72  test    eax, eax
0x180029c74  jnz     short loc_180029C7C
0x180029c76  call    cs:__imp_GetLastError
0x180029c7c  lea     rcx, [rbx+0B8h]
0x180029c83  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x180029c88  lea     rcx, [rbx+88h]
0x180029c8f  call    ?RemoveAll@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAll(void)
0x180029c94  lea     rcx, [rbx+60h]; lpCriticalSection
0x180029c98  call    cs:__imp_DeleteCriticalSection
0x180029c9e  lea     rcx, [rbx+40h]
0x180029ca2  call    ??1?$CAtlArray@VCAdapter@@V?$CElementTraits@VCAdapter@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>::~CAtlArray<CAdapter,ATL::CElementTraits<CAdapter>>(void)
0x180029ca7  lea     rcx, [rbx+18h]; lpCriticalSection
0x180029cab  call    cs:__imp_DeleteCriticalSection
0x180029cb1  lea     rax, ??_7CProfileStore@@6B@; const CProfileStore::`vftable'
0x180029cb8  mov     [rbx], rax
0x180029cbb  add     rsp, 20h
0x180029cbf  pop     rbx
0x180029cc0  retn
```
