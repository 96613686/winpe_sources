# CComInternalCreatorInitializerT<CElevationConfig,0>::CreateInstance(_GUID const &,void * *)

- ea: `0x18001b530`
- end: `0x18001b6c5`
- name: `?CreateInstance@?$CComInternalCreatorInitializerT@VCElevationConfig@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001adc0`

## callees

- `0x180003020`
- `0x180003520`
- `0x180003838`
- `0x180003ed8`
- `0x180004288`
- `0x180004520`
- `0x18001b530`
- `0x18003c52a`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b53f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b53f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b556`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b556`

## pseudocode

```c
__int64 __fastcall CComInternalCreatorInitializerT<CElevationConfig,0>::CreateInstance(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  _QWORD *v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax

  ProcessHeap = GetProcessHeap();
  v5 = HeapAlloc(ProcessHeap, 0, 0xA8u);
  v6 = (__int64)v5;
  if ( v5 )
  {
    v5[1] = 0;
    v5[2] = 0;
    memset_0(v5 + 3, 0, 0x68u);
    *(_DWORD *)(v6 + 128) = 0;
    memset_0((void *)(v6 & -(__int64)(v6 != -136)), 0, 0xA0u);
    *(_QWORD *)(v6 + 144) = 0;
    *(_QWORD *)v6 = &CUnknownImplT<CElevationConfig,0>::`vftable';
    *(_DWORD *)(v6 + 160) = 1;
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
    *(_QWORD *)(v6 + 152) = 0;
  else
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
      goto LABEL_18;
    v8 = (unsigned int)v10;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18001b530  push    rbx
0x18001b532  push    rbp
0x18001b533  push    rsi
0x18001b534  push    rdi
0x18001b535  sub     rsp, 28h
0x18001b539  mov     rsi, rdx
0x18001b53c  mov     rbp, rcx
0x18001b53f  call    cs:__imp_GetProcessHeap
0x18001b546  nop     dword ptr [rax+rax+00h]
0x18001b54b  xor     edx, edx; dwFlags
0x18001b54d  mov     r8d, 0A8h; dwBytes
0x18001b553  mov     rcx, rax; hHeap
0x18001b556  call    cs:__imp_HeapAlloc
0x18001b55d  nop     dword ptr [rax+rax+00h]
0x18001b562  mov     rbx, rax
0x18001b565  test    rax, rax
0x18001b568  jz      short loc_18001B5DA
0x18001b56a  xor     edx, edx; Val
0x18001b56c  mov     qword ptr [rax+8], 0
0x18001b574  lea     rcx, [rax+18h]; void *
0x18001b578  mov     qword ptr [rax+10h], 0
0x18001b580  lea     r8d, [rdx+68h]; Size
0x18001b584  call    memset_0
0x18001b589  lea     rax, [rbx+88h]
0x18001b590  mov     dword ptr [rbx+80h], 0
0x18001b59a  neg     rax
0x18001b59d  mov     r8d, 0A0h; Size
0x18001b5a3  sbb     rcx, rcx
0x18001b5a6  xor     edx, edx; Val
0x18001b5a8  and     rcx, rbx; void *
0x18001b5ab  call    memset_0
0x18001b5b0  lea     rax, ??_7?$CUnknownImplT@VCElevationConfig@@$0A@@@6B@; const CUnknownImplT<CElevationConfig,0>::`vftable'
0x18001b5b7  mov     qword ptr [rbx+90h], 0
0x18001b5c2  mov     [rbx], rax
0x18001b5c5  mov     dword ptr [rbx+0A0h], 1
0x18001b5cf  lock inc cs:?g_lServerLockCount@?$CComProcessCounter@$0A@@@0JA; long CComProcessCounter<0>::g_lServerLockCount
0x18001b5d6  xor     edi, edi
0x18001b5d8  jmp     short loc_18001B5E8
0x18001b5da  mov     edi, 8007000Eh
0x18001b5df  xor     ebx, ebx
0x18001b5e1  mov     ecx, edi
0x18001b5e3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b5e8  mov     ecx, edi
0x18001b5ea  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b5ef  test    edi, edi
0x18001b5f1  jns     short loc_18001B5FA
0x18001b5f3  mov     ecx, edi
0x18001b5f5  jmp     loc_18001B699
0x18001b5fa  cmp     dword ptr [rbx+80h], 0
0x18001b601  jz      short loc_18001B616
0x18001b603  lea     rcx, [rbx+18h]
0x18001b607  call    ?Done@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Done(void)
0x18001b60c  mov     dword ptr [rbx+80h], 0
0x18001b616  lea     rcx, [rbx+8]
0x18001b61a  xor     edx, edx
0x18001b61c  call    ?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001b621  lea     rcx, [rbx+18h]
0x18001b625  call    ?Init@?$CRWLock2T@VCEmptyType@@@@QEAAJXZ; CRWLock2T<CEmptyType>::Init(void)
0x18001b62a  mov     edi, eax
0x18001b62c  test    eax, eax
0x18001b62e  js      short loc_18001B648
0x18001b630  mov     rcx, rbx
0x18001b633  mov     dword ptr [rbx+80h], 1
0x18001b63d  call    ??$AddTypeLib@$00$0A@@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@IEAAJPEAX@Z; CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::AddTypeLib<1,0>(void *)
0x18001b642  mov     edi, eax
0x18001b644  test    eax, eax
0x18001b646  jns     short loc_18001B64F
0x18001b648  mov     ecx, eax
0x18001b64a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b64f  mov     ecx, edi
0x18001b651  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b656  test    edi, edi
0x18001b658  jns     short loc_18001B663
0x18001b65a  mov     ecx, edi
0x18001b65c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b661  jmp     short loc_18001B66E
0x18001b663  mov     qword ptr [rbx+98h], 0
0x18001b66e  mov     ecx, edi
0x18001b670  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b675  test    edi, edi
0x18001b677  js      loc_18001B5F3
0x18001b67d  mov     rax, [rbx]
0x18001b680  mov     r8, rsi
0x18001b683  mov     rdx, rbp
0x18001b686  mov     rcx, rbx
0x18001b689  mov     rax, [rax]
0x18001b68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b691  mov     edi, eax
0x18001b693  test    eax, eax
0x18001b695  jns     short loc_18001B69E
0x18001b697  mov     ecx, eax
0x18001b699  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b69e  mov     ecx, edi
0x18001b6a0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b6a5  test    rbx, rbx
0x18001b6a8  jz      short loc_18001B6B9
0x18001b6aa  mov     rcx, [rbx]
0x18001b6ad  mov     rax, [rcx+10h]
0x18001b6b1  mov     rcx, rbx
0x18001b6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6b9  mov     eax, edi
0x18001b6bb  add     rsp, 28h
0x18001b6bf  pop     rdi
0x18001b6c0  pop     rsi
0x18001b6c1  pop     rbp
0x18001b6c2  pop     rbx
0x18001b6c3  retn
```
