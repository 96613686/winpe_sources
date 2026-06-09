# CComInternalCreatorInitializerT<CLicensingStateTools,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b6cc`
- end: `0x18001b85e`
- name: `?CreateInstance@?$CComInternalCreatorInitializerT@VCLicensingStateTools@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ae20`

## callees

- `0x180003020`
- `0x180003520`
- `0x180003838`
- `0x180003ed8`
- `0x180004288`
- `0x180004520`
- `0x18001b6cc`
- `0x18003c52a`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b6db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b6db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b6f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b6f2`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorInitializerT<CLicensingStateTools,0>::CreateInstance(__int64 a1, __int64 a2)
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
    *(_QWORD *)v6 = &CUnknownImplT<CLicensingStateTools,0>::`vftable'{for `CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>'};
    *(_QWORD *)(v6 + 136) = &CUnknownImplT<CLicensingStateTools,0>::`vftable'{for `CElevationConfigurable'};
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
0x18001b6cc  push    rbx
0x18001b6ce  push    rbp
0x18001b6cf  push    rsi
0x18001b6d0  push    rdi
0x18001b6d1  sub     rsp, 28h
0x18001b6d5  mov     rsi, rdx
0x18001b6d8  mov     rbp, rcx
0x18001b6db  call    cs:__imp_GetProcessHeap
0x18001b6e2  nop     dword ptr [rax+rax+00h]
0x18001b6e7  xor     edx, edx; dwFlags
0x18001b6e9  mov     r8d, 0A0h; dwBytes
0x18001b6ef  mov     rcx, rax; hHeap
0x18001b6f2  call    cs:__imp_HeapAlloc
0x18001b6f9  nop     dword ptr [rax+rax+00h]
0x18001b6fe  mov     rbx, rax
0x18001b701  test    rax, rax
0x18001b704  jz      short loc_18001B784
0x18001b706  xor     edx, edx; Val
0x18001b708  mov     qword ptr [rax+8], 0
0x18001b710  lea     rcx, [rax+18h]; void *
0x18001b714  mov     qword ptr [rax+10h], 0
0x18001b71c  lea     r8d, [rdx+68h]; Size
0x18001b720  call    memset_0
0x18001b725  lea     rax, [rbx+98h]
0x18001b72c  mov     dword ptr [rbx+80h], 0
0x18001b736  neg     rax
0x18001b739  mov     qword ptr [rbx+90h], 0
0x18001b744  mov     r8d, 98h; Size
0x18001b74a  sbb     rcx, rcx
0x18001b74d  xor     edx, edx; Val
0x18001b74f  and     rcx, rbx; void *
0x18001b752  call    memset_0
0x18001b757  lea     rax, ??_7?$CUnknownImplT@VCLicensingStateTools@@$0A@@@6B?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@@; const CUnknownImplT<CLicensingStateTools,0>::`vftable'{for `CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>'}
0x18001b75e  mov     [rbx], rax
0x18001b761  lea     rax, ??_7?$CUnknownImplT@VCLicensingStateTools@@$0A@@@6BCElevationConfigurable@@@; const CUnknownImplT<CLicensingStateTools,0>::`vftable'{for `CElevationConfigurable'}
0x18001b768  mov     [rbx+88h], rax
0x18001b76f  mov     dword ptr [rbx+98h], 1
0x18001b779  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b780  xor     edi, edi
0x18001b782  jmp     short loc_18001B792
0x18001b784  mov     edi, 8007000Eh
0x18001b789  xor     ebx, ebx
0x18001b78b  mov     ecx, edi
0x18001b78d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b792  mov     ecx, edi
0x18001b794  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b799  test    edi, edi
0x18001b79b  jns     short loc_18001B7A4
0x18001b79d  mov     ecx, edi
0x18001b79f  jmp     loc_18001B832
0x18001b7a4  cmp     dword ptr [rbx+80h], 0
0x18001b7ab  jz      short loc_18001B7C0
0x18001b7ad  lea     rcx, [rbx+18h]
0x18001b7b1  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x18001b7b6  mov     dword ptr [rbx+80h], 0
0x18001b7c0  lea     rcx, [rbx+8]
0x18001b7c4  xor     edx, edx
0x18001b7c6  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001b7cb  lea     rcx, [rbx+18h]
0x18001b7cf  call    ?Init@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Init(void)
0x18001b7d4  mov     edi, eax
0x18001b7d6  test    eax, eax
0x18001b7d8  js      short loc_18001B7F2
0x18001b7da  mov     rcx, rbx
0x18001b7dd  mov     dword ptr [rbx+80h], 1
0x18001b7e7  call    ??$AddTypeLib@$00$0A@@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@IEAAJPEAX@Z; CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(void *)
0x18001b7ec  mov     edi, eax
0x18001b7ee  test    eax, eax
0x18001b7f0  jns     short loc_18001B7F9
0x18001b7f2  mov     ecx, eax
0x18001b7f4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b7f9  mov     ecx, edi
0x18001b7fb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b800  test    edi, edi
0x18001b802  jns     short loc_18001B80B
0x18001b804  mov     ecx, edi
0x18001b806  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b80b  mov     ecx, edi
0x18001b80d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b812  test    edi, edi
0x18001b814  js      short loc_18001B79D
0x18001b816  mov     rax, [rbx]
0x18001b819  mov     r8, rsi
0x18001b81c  mov     rdx, rbp
0x18001b81f  mov     rcx, rbx
0x18001b822  mov     rax, [rax]
0x18001b825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b82a  mov     edi, eax
0x18001b82c  test    eax, eax
0x18001b82e  jns     short loc_18001B837
0x18001b830  mov     ecx, eax
0x18001b832  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b837  mov     ecx, edi
0x18001b839  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b83e  test    rbx, rbx
0x18001b841  jz      short loc_18001B852
0x18001b843  mov     rcx, [rbx]
0x18001b846  mov     rax, [rcx+10h]
0x18001b84a  mov     rcx, rbx
0x18001b84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b852  mov     eax, edi
0x18001b854  add     rsp, 28h
0x18001b858  pop     rdi
0x18001b859  pop     rsi
0x18001b85a  pop     rbp
0x18001b85b  pop     rbx
0x18001b85c  retn
```
