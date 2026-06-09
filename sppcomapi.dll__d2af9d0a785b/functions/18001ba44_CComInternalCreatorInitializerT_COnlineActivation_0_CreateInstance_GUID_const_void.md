# CComInternalCreatorInitializerT<COnlineActivation,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001ba44`
- end: `0x18001bbd6`
- name: `?CreateInstance@?$CComInternalCreatorInitializerT@VCOnlineActivation@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001aee0`

## callees

- `0x180003020`
- `0x180003520`
- `0x180003838`
- `0x180003ed8`
- `0x180004288`
- `0x180004520`
- `0x18001ba44`
- `0x18003c52a`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ba53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ba53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ba6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ba6a`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorInitializerT<COnlineActivation,0>::CreateInstance(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0xA0u);
  v6 = (__int64)v5;
  if ( v5 )
  {
    v5[1] = 0;
    v5[2] = 0;
    memset_0(v5 + 3, 0, 0x68u);
    *(_DWORD *)(v6 + 128) = 0;
    *(_QWORD *)(v6 + 144) = 0;
    memset_0((void *)(v6 & -(__int64)(v6 != -152)), 0, 0x98u);
    *(_QWORD *)v6 = &CUnknownImplT<COnlineActivation,0>::`vftable'{for `CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>'};
    *(_QWORD *)(v6 + 136) = &CUnknownImplT<COnlineActivation,0>::`vftable'{for `CElevationConfigurable'};
    *(_DWORD *)(v6 + 152) = 1;
    _InterlockedIncrement(&CComProcessCounter<0>::g_lServerLockCount);
    v7 = 0;
  }
  else
  {
    v7 = -2147024882;
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_5;
  if ( *(_DWORD *)(v6 + 128) )
  {
    CRWLock2T<CEmptyType>::Done(v6 + 24);
    *(_DWORD *)(v6 + 128) = 0;
  }
  CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize(
    v6 + 8,
    0);
  v9 = CRWLock2T<CEmptyType>::Init(v6 + 24);
  v7 = v9;
  if ( v9 < 0
    || (*(_DWORD *)(v6 + 128) = 1,
        v9 = CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(v6),
        v7 = v9,
        v9 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
LABEL_5:
    v8 = v7;
  }
  else
  {
    v10 = (**(__int64 (__fastcall ***)(__int64, __int64, __int64))v6)(v6, a1, a2);
    v7 = v10;
    if ( v10 >= 0 )
      goto LABEL_17;
    v8 = (unsigned int)v10;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18001ba44  push    rbx
0x18001ba46  push    rbp
0x18001ba47  push    rsi
0x18001ba48  push    rdi
0x18001ba49  sub     rsp, 28h
0x18001ba4d  mov     rsi, rdx
0x18001ba50  mov     rbp, rcx
0x18001ba53  call    cs:__imp_GetProcessHeap
0x18001ba5a  nop     dword ptr [rax+rax+00h]
0x18001ba5f  xor     edx, edx; dwFlags
0x18001ba61  mov     r8d, 0A0h; dwBytes
0x18001ba67  mov     rcx, rax; hHeap
0x18001ba6a  call    cs:__imp_HeapAlloc
0x18001ba71  nop     dword ptr [rax+rax+00h]
0x18001ba76  mov     rbx, rax
0x18001ba79  test    rax, rax
0x18001ba7c  jz      short loc_18001BAFC
0x18001ba7e  xor     edx, edx; Val
0x18001ba80  mov     qword ptr [rax+8], 0
0x18001ba88  lea     rcx, [rax+18h]; void *
0x18001ba8c  mov     qword ptr [rax+10h], 0
0x18001ba94  lea     r8d, [rdx+68h]; Size
0x18001ba98  call    memset_0
0x18001ba9d  lea     rax, [rbx+98h]
0x18001baa4  mov     dword ptr [rbx+80h], 0
0x18001baae  neg     rax
0x18001bab1  mov     qword ptr [rbx+90h], 0
0x18001babc  mov     r8d, 98h; Size
0x18001bac2  sbb     rcx, rcx
0x18001bac5  xor     edx, edx; Val
0x18001bac7  and     rcx, rbx; void *
0x18001baca  call    memset_0
0x18001bacf  lea     rax, ??_7?$CUnknownImplT@VCOnlineActivation@@$0A@@@6B?$CDispatchImplT@UIOnlineActivation@@$1?IID_IOnlineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@@; const CUnknownImplT<COnlineActivation,0>::`vftable'{for `CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>'}
0x18001bad6  mov     [rbx], rax
0x18001bad9  lea     rax, ??_7?$CUnknownImplT@VCOnlineActivation@@$0A@@@6BCElevationConfigurable@@@; const CUnknownImplT<COnlineActivation,0>::`vftable'{for `CElevationConfigurable'}
0x18001bae0  mov     [rbx+88h], rax
0x18001bae7  mov     dword ptr [rbx+98h], 1
0x18001baf1  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001baf8  xor     edi, edi
0x18001bafa  jmp     short loc_18001BB0A
0x18001bafc  mov     edi, 8007000Eh
0x18001bb01  xor     ebx, ebx
0x18001bb03  mov     ecx, edi
0x18001bb05  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bb0a  mov     ecx, edi
0x18001bb0c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bb11  test    edi, edi
0x18001bb13  jns     short loc_18001BB1C
0x18001bb15  mov     ecx, edi
0x18001bb17  jmp     loc_18001BBAA
0x18001bb1c  cmp     dword ptr [rbx+80h], 0
0x18001bb23  jz      short loc_18001BB38
0x18001bb25  lea     rcx, [rbx+18h]
0x18001bb29  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x18001bb2e  mov     dword ptr [rbx+80h], 0
0x18001bb38  lea     rcx, [rbx+8]
0x18001bb3c  xor     edx, edx
0x18001bb3e  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001bb43  lea     rcx, [rbx+18h]
0x18001bb47  call    ?Init@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Init(void)
0x18001bb4c  mov     edi, eax
0x18001bb4e  test    eax, eax
0x18001bb50  js      short loc_18001BB6A
0x18001bb52  mov     rcx, rbx
0x18001bb55  mov     dword ptr [rbx+80h], 1
0x18001bb5f  call    ??$AddTypeLib@$00$0A@@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@IEAAJPEAX@Z; CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(void *)
0x18001bb64  mov     edi, eax
0x18001bb66  test    eax, eax
0x18001bb68  jns     short loc_18001BB71
0x18001bb6a  mov     ecx, eax
0x18001bb6c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bb71  mov     ecx, edi
0x18001bb73  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bb78  test    edi, edi
0x18001bb7a  jns     short loc_18001BB83
0x18001bb7c  mov     ecx, edi
0x18001bb7e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bb83  mov     ecx, edi
0x18001bb85  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bb8a  test    edi, edi
0x18001bb8c  js      short loc_18001BB15
0x18001bb8e  mov     rax, [rbx]
0x18001bb91  mov     r8, rsi
0x18001bb94  mov     rdx, rbp
0x18001bb97  mov     rcx, rbx
0x18001bb9a  mov     rax, [rax]
0x18001bb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bba2  mov     edi, eax
0x18001bba4  test    eax, eax
0x18001bba6  jns     short loc_18001BBAF
0x18001bba8  mov     ecx, eax
0x18001bbaa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001bbaf  mov     ecx, edi
0x18001bbb1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001bbb6  test    rbx, rbx
0x18001bbb9  jz      short loc_18001BBCA
0x18001bbbb  mov     rcx, [rbx]
0x18001bbbe  mov     rax, [rcx+10h]
0x18001bbc2  mov     rcx, rbx
0x18001bbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbca  mov     eax, edi
0x18001bbcc  add     rsp, 28h
0x18001bbd0  pop     rdi
0x18001bbd1  pop     rsi
0x18001bbd2  pop     rbp
0x18001bbd3  pop     rbx
0x18001bbd4  retn
```
