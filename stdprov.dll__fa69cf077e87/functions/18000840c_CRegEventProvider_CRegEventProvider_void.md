# CRegEventProvider::~CRegEventProvider(void)

- ea: `0x18000840c`
- end: `0x180008502`
- name: `??1CRegEventProvider@@QEAA@XZ`
- size: `246`
- prototype: `void __fastcall(CRegEventProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008370`

## callees

- `0x18000840c`
- `0x18000b8e0`
- `0x18000ba40`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084e8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800084e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800084ba`

## pseudocode

```c
void __fastcall CRegEventProvider::~CRegEventProvider(CRegEventProvider *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CRegEventProvider::`vftable'{for `IWbemEventProvider'};
  *((_QWORD *)this + 1) = &CRegEventProvider::`vftable'{for `IWbemEventProviderQuerySink'};
  *((_QWORD *)this + 2) = &CRegEventProvider::`vftable'{for `IWbemEventProviderSecurity'};
  *((_QWORD *)this + 3) = &CRegEventProvider::`vftable'{for `IWbemProviderInit'};
  v2 = *((_QWORD *)this + 10);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 7);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  _InterlockedDecrement(&lObj);
  v6 = (void *)*((_QWORD *)this + 9);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 28);
  if ( v7 )
    CloseHandle(v7);
  CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>((CRegEventProvider *)((char *)this + 272));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::~CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>((CRegEventProvider *)((char *)this + 88));
}

```

## disassembly

```asm
0x18000840c  mov     [rsp+arg_0], rcx
0x180008411  push    rbx
0x180008412  sub     rsp, 20h
0x180008416  mov     rbx, rcx
0x180008419  lea     rax, ??_7CRegEventProvider@@6BIWbemEventProvider@@@; const CRegEventProvider::`vftable'{for `IWbemEventProvider'}
0x180008420  mov     [rcx], rax
0x180008423  lea     rax, ??_7CRegEventProvider@@6BIWbemEventProviderQuerySink@@@; const CRegEventProvider::`vftable'{for `IWbemEventProviderQuerySink'}
0x18000842a  mov     [rcx+8], rax
0x18000842e  lea     rax, ??_7CRegEventProvider@@6BIWbemEventProviderSecurity@@@; const CRegEventProvider::`vftable'{for `IWbemEventProviderSecurity'}
0x180008435  mov     [rcx+10h], rax
0x180008439  lea     rax, ??_7CRegEventProvider@@6BIWbemProviderInit@@@; const CRegEventProvider::`vftable'{for `IWbemProviderInit'}
0x180008440  mov     [rcx+18h], rax
0x180008444  mov     rcx, [rcx+50h]
0x180008448  test    rcx, rcx
0x18000844b  jz      short loc_180008459
0x18000844d  mov     rax, [rcx]
0x180008450  mov     rax, [rax+10h]
0x180008454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008459  mov     rcx, [rbx+28h]
0x18000845d  test    rcx, rcx
0x180008460  jz      short loc_18000846E
0x180008462  mov     rax, [rcx]
0x180008465  mov     rax, [rax+10h]
0x180008469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846e  mov     rcx, [rbx+30h]
0x180008472  test    rcx, rcx
0x180008475  jz      short loc_180008483
0x180008477  mov     rax, [rcx]
0x18000847a  mov     rax, [rax+10h]
0x18000847e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008483  mov     rcx, [rbx+38h]
0x180008487  test    rcx, rcx
0x18000848a  jz      short loc_180008498
0x18000848c  mov     rax, [rcx]
0x18000848f  mov     rax, [rax+10h]
0x180008493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008498  lock dec cs:?lObj@@3JA; long lObj
0x18000849f  mov     rcx, [rbx+48h]; hObject
0x1800084a3  test    rcx, rcx
0x1800084a6  jz      short loc_1800084AE
0x1800084a8  call    cs:__imp_CloseHandle
0x1800084ae  mov     rcx, [rbx+0E0h]; hObject
0x1800084b5  test    rcx, rcx
0x1800084b8  jz      short loc_1800084C1
0x1800084ba  call    cs:__imp_CloseHandle
0x1800084c0  nop
0x1800084c1  lea     rcx, [rbx+110h]
0x1800084c8  mov     [rsp+28h+arg_8], rcx
0x1800084cd  call    ??1?$CPointerQueue@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@@@QEAA@XZ; CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>::~CPointerQueue<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>>(void)
0x1800084d2  nop
0x1800084d3  lea     rcx, [rbx+0E8h]; lpCriticalSection
0x1800084da  call    cs:__imp_DeleteCriticalSection
0x1800084e0  nop
0x1800084e1  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x1800084e8  call    cs:__imp_DeleteCriticalSection
0x1800084ee  nop
0x1800084ef  lea     rcx, [rbx+58h]
0x1800084f3  mov     [rsp+28h+arg_0], rcx
0x1800084f8  add     rsp, 20h
0x1800084fc  pop     rbx
0x1800084fd  jmp     ??1?$CPointerArray@VCRegistryEventRequest@@V?$CReferenceManager@VCRegistryEventRequest@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>::~CPointerArray<CRegistryEventRequest,CReferenceManager<CRegistryEventRequest>,CFlexArray>(void)
```
