# CComInternalCreatorInitializerT<COfflineActivation,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b864`
- end: `0x18001ba3c`
- name: `?CreateInstance@?$CComInternalCreatorInitializerT@VCOfflineActivation@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ae80`

## callees

- `0x180003020`
- `0x180003520`
- `0x180003838`
- `0x180003ed8`
- `0x180004288`
- `0x180004520`
- `0x18001b864`
- `0x18001f8cc`
- `0x18003c52a`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b873`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b88a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b88a`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorInitializerT<COfflineActivation,0>::CreateInstance(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0xF0u);
  v6 = (__int64)v5;
  if ( v5 )
  {
    v5[1] = 0;
    v5[2] = 0;
    memset_0(v5 + 3, 0, 0x68u);
    *(_DWORD *)(v6 + 128) = 0;
    *(_QWORD *)(v6 + 144) = 0;
    memset_0((void *)(v6 & -(__int64)(v6 != -152)), 0, 0xE8u);
    *(_QWORD *)(v6 + 160) = 0;
    *(_QWORD *)(v6 + 152) = &CPhoneActivationBook::`vftable';
    *(_QWORD *)v6 = &CUnknownImplT<COfflineActivation,0>::`vftable'{for `CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>'};
    *(_QWORD *)(v6 + 136) = &CUnknownImplT<COfflineActivation,0>::`vftable'{for `CElevationConfigurable'};
    *(_QWORD *)(v6 + 168) = 0;
    *(_QWORD *)(v6 + 184) = 0;
    *(_DWORD *)(v6 + 232) = 1;
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
  if ( (v7 & 0x80000000) == 0 )
  {
    v11 = CPhoneActivationBook::Initialize((CPhoneActivationBook *)(v6 + 152));
    v7 = v11;
    if ( v11 >= 0 )
      goto LABEL_16;
    v10 = (unsigned int)v11;
  }
  else
  {
    v10 = v7;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( (v7 & 0x80000000) != 0 )
  {
LABEL_5:
    v8 = v7;
    goto LABEL_19;
  }
  v12 = (**(__int64 (__fastcall ***)(__int64, __int64, __int64))v6)(v6, a1, a2);
  v7 = v12;
  if ( v12 >= 0 )
    goto LABEL_20;
  v8 = (unsigned int)v12;
LABEL_19:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18001b864  push    rbx
0x18001b866  push    rbp
0x18001b867  push    rsi
0x18001b868  push    rdi
0x18001b869  sub     rsp, 28h
0x18001b86d  mov     rsi, rdx
0x18001b870  mov     rbp, rcx
0x18001b873  call    cs:__imp_GetProcessHeap
0x18001b87a  nop     dword ptr [rax+rax+00h]
0x18001b87f  xor     edx, edx; dwFlags
0x18001b881  mov     r8d, 0F0h; dwBytes
0x18001b887  mov     rcx, rax; hHeap
0x18001b88a  call    cs:__imp_HeapAlloc
0x18001b891  nop     dword ptr [rax+rax+00h]
0x18001b896  mov     rbx, rax
0x18001b899  test    rax, rax
0x18001b89c  jz      loc_18001B948
0x18001b8a2  xor     edx, edx; Val
0x18001b8a4  mov     qword ptr [rax+8], 0
0x18001b8ac  lea     rcx, [rax+18h]; void *
0x18001b8b0  mov     qword ptr [rax+10h], 0
0x18001b8b8  lea     r8d, [rdx+68h]; Size
0x18001b8bc  call    memset_0
0x18001b8c1  lea     rdi, [rbx+98h]
0x18001b8c8  mov     dword ptr [rbx+80h], 0
0x18001b8d2  mov     rax, rdi
0x18001b8d5  mov     qword ptr [rbx+90h], 0
0x18001b8e0  neg     rax
0x18001b8e3  mov     r8d, 0E8h; Size
0x18001b8e9  sbb     rcx, rcx
0x18001b8ec  xor     edx, edx; Val
0x18001b8ee  and     rcx, rbx; void *
0x18001b8f1  call    memset_0
0x18001b8f6  lea     rax, ??_7CPhoneActivationBook@@6B@; const CPhoneActivationBook::`vftable'
0x18001b8fd  mov     qword ptr [rdi+8], 0
0x18001b905  mov     [rdi], rax
0x18001b908  lea     rax, ??_7?$CUnknownImplT@VCOfflineActivation@@$0A@@@6B?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@@; const CUnknownImplT<COfflineActivation,0>::`vftable'{for `CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>'}
0x18001b90f  mov     [rbx], rax
0x18001b912  lea     rax, ??_7?$CUnknownImplT@VCOfflineActivation@@$0A@@@6BCElevationConfigurable@@@; const CUnknownImplT<COfflineActivation,0>::`vftable'{for `CElevationConfigurable'}
0x18001b919  mov     [rbx+88h], rax
0x18001b920  mov     qword ptr [rdi+10h], 0
0x18001b928  mov     qword ptr [rbx+0B8h], 0
0x18001b933  mov     dword ptr [rbx+0E8h], 1
0x18001b93d  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b944  xor     edi, edi
0x18001b946  jmp     short loc_18001B956
0x18001b948  mov     edi, 8007000Eh
0x18001b94d  xor     ebx, ebx
0x18001b94f  mov     ecx, edi
0x18001b951  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b956  mov     ecx, edi
0x18001b958  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b95d  test    edi, edi
0x18001b95f  jns     short loc_18001B968
0x18001b961  mov     ecx, edi
0x18001b963  jmp     loc_18001BA10
0x18001b968  cmp     dword ptr [rbx+80h], 0
0x18001b96f  jz      short loc_18001B984
0x18001b971  lea     rcx, [rbx+18h]
0x18001b975  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x18001b97a  mov     dword ptr [rbx+80h], 0
0x18001b984  lea     rcx, [rbx+8]
0x18001b988  xor     edx, edx
0x18001b98a  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001b98f  lea     rcx, [rbx+18h]
0x18001b993  call    ?Init@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Init(void)
0x18001b998  mov     edi, eax
0x18001b99a  test    eax, eax
0x18001b99c  js      short loc_18001B9B6
0x18001b99e  mov     rcx, rbx
0x18001b9a1  mov     dword ptr [rbx+80h], 1
0x18001b9ab  call    ??$AddTypeLib@$00$0A@@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@IEAAJPEAX@Z; CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(void *)
0x18001b9b0  mov     edi, eax
0x18001b9b2  test    eax, eax
0x18001b9b4  jns     short loc_18001B9BD
0x18001b9b6  mov     ecx, eax
0x18001b9b8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b9bd  mov     ecx, edi
0x18001b9bf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b9c4  test    edi, edi
0x18001b9c6  jns     short loc_18001B9CC
0x18001b9c8  mov     ecx, edi
0x18001b9ca  jmp     short loc_18001B9E0
0x18001b9cc  lea     rcx, [rbx+98h]; this
0x18001b9d3  call    ?Initialize@CPhoneActivationBook@@QEAAJXZ; CPhoneActivationBook::Initialize(void)
0x18001b9d8  mov     edi, eax
0x18001b9da  test    eax, eax
0x18001b9dc  jns     short loc_18001B9E5
0x18001b9de  mov     ecx, eax
0x18001b9e0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b9e5  mov     ecx, edi
0x18001b9e7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b9ec  test    edi, edi
0x18001b9ee  js      loc_18001B961
0x18001b9f4  mov     rax, [rbx]
0x18001b9f7  mov     r8, rsi
0x18001b9fa  mov     rdx, rbp
0x18001b9fd  mov     rcx, rbx
0x18001ba00  mov     rax, [rax]
0x18001ba03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba08  mov     edi, eax
0x18001ba0a  test    eax, eax
0x18001ba0c  jns     short loc_18001BA15
0x18001ba0e  mov     ecx, eax
0x18001ba10  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ba15  mov     ecx, edi
0x18001ba17  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ba1c  test    rbx, rbx
0x18001ba1f  jz      short loc_18001BA30
0x18001ba21  mov     rcx, [rbx]
0x18001ba24  mov     rax, [rcx+10h]
0x18001ba28  mov     rcx, rbx
0x18001ba2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba30  mov     eax, edi
0x18001ba32  add     rsp, 28h
0x18001ba36  pop     rdi
0x18001ba37  pop     rsi
0x18001ba38  pop     rbp
0x18001ba39  pop     rbx
0x18001ba3a  retn
```
