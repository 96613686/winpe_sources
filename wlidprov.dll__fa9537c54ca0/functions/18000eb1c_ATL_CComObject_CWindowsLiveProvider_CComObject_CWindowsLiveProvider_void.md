# ATL::CComObject<CWindowsLiveProvider>::~CComObject<CWindowsLiveProvider>(void)

- ea: `0x18000eb1c`
- end: `0x18000ebbc`
- name: `??1?$CComObject@VCWindowsLiveProvider@@@ATL@@UEAA@XZ`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000eae0`

## callees

- `0x18000eb1c`
- `0x18000ebc4`
- `0x18000ec10`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eb93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ebb0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000eb93`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ebb0`

## pseudocode

```c
void __fastcall ATL::CComObject<CWindowsLiveProvider>::~CComObject<CWindowsLiveProvider>(__int64 a1)
{
  *(_DWORD *)(a1 + 48) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IIdentityProvider'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IAssociatedIdentityProvider'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IConnectedIdentityProvider'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IIdentityAuthentication'};
  *(_QWORD *)(a1 + 32) = &ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IKeyChangeProvider'};
  *(_QWORD *)(a1 + 40) = &ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IMigratedIdentityConnector'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CAutoRefPtr<SmartWLIDHandle>::Deinit(a1 + 224);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  ATL::CAtlMap<unsigned long,CWLIDNotifyItem *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CWLIDNotifyItem *>>::RemoveAll(a1 + 104);
  if ( *(_BYTE *)(a1 + 96) )
  {
    *(_BYTE *)(a1 + 96) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  }
}

```

## disassembly

```asm
0x18000eb1c  push    rbx
0x18000eb1e  sub     rsp, 20h
0x18000eb22  mov     dword ptr [rcx+30h], 0C0000001h
0x18000eb29  lea     rax, ??_7?$CComObject@VCWindowsLiveProvider@@@ATL@@6BIIdentityProvider@@@; const ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IIdentityProvider'}
0x18000eb30  mov     [rcx], rax
0x18000eb33  mov     rbx, rcx
0x18000eb36  lea     rax, ??_7?$CComObject@VCWindowsLiveProvider@@@ATL@@6BIAssociatedIdentityProvider@@@; const ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IAssociatedIdentityProvider'}
0x18000eb3d  mov     [rcx+8], rax
0x18000eb41  lea     rax, ??_7?$CComObject@VCWindowsLiveProvider@@@ATL@@6BIConnectedIdentityProvider@@@; const ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IConnectedIdentityProvider'}
0x18000eb48  mov     [rcx+10h], rax
0x18000eb4c  lea     rax, ??_7?$CComObject@VCWindowsLiveProvider@@@ATL@@6BIIdentityAuthentication@@@; const ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IIdentityAuthentication'}
0x18000eb53  mov     [rcx+18h], rax
0x18000eb57  lea     rax, ??_7?$CComObject@VCWindowsLiveProvider@@@ATL@@6BIKeyChangeProvider@@@; const ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IKeyChangeProvider'}
0x18000eb5e  mov     [rcx+20h], rax
0x18000eb62  lea     rax, ??_7?$CComObject@VCWindowsLiveProvider@@@ATL@@6BIMigratedIdentityConnector@@@; const ATL::CComObject<CWindowsLiveProvider>::`vftable'{for `IMigratedIdentityConnector'}
0x18000eb69  mov     [rcx+28h], rax
0x18000eb6d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000eb74  mov     rax, [rcx]
0x18000eb77  mov     rax, [rax+10h]
0x18000eb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb80  lea     rcx, [rbx+0E0h]
0x18000eb87  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x18000eb8c  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x18000eb93  call    cs:__imp_DeleteCriticalSection
0x18000eb99  lea     rcx, [rbx+68h]
0x18000eb9d  call    ?RemoveAll@?$CAtlMap@KPEAVCWLIDNotifyItem@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCWLIDNotifyItem@@@3@@ATL@@QEAAXXZ; ATL::CAtlMap<ulong,CWLIDNotifyItem *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CWLIDNotifyItem *>>::RemoveAll(void)
0x18000eba2  lea     rcx, [rbx+38h]; lpCriticalSection
0x18000eba6  cmp     byte ptr [rcx+28h], 0
0x18000ebaa  jz      short loc_18000EBB6
0x18000ebac  mov     byte ptr [rcx+28h], 0
0x18000ebb0  call    cs:__imp_DeleteCriticalSection
0x18000ebb6  add     rsp, 20h
0x18000ebba  pop     rbx
0x18000ebbb  retn
```
