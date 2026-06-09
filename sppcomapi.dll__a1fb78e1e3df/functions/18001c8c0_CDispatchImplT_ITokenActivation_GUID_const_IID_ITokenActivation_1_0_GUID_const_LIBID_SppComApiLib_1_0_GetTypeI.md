# CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001c8c0`
- end: `0x18001ca26`
- name: `?GetTypeInfo@?$CDispatchImplT@UITokenActivation@@$1?IID_ITokenActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800033cc`
- `0x180003520`
- `0x1800038a8`
- `0x180004288`
- `0x180004340`
- `0x180004b00`
- `0x18001c8c0`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<ITokenActivation,&_GUID const IID_ITokenActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 v4; // rsi
  int v5; // edi
  __int64 v6; // r14
  int v7; // r15d
  unsigned int v10; // ebx
  __int64 v11; // rbp
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v17[22]; // [rsp+20h] [rbp-58h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v17[0] = 0;
  v7 = 0;
  if ( !a4 )
  {
    v10 = -2147467261;
LABEL_20:
    v15 = v10;
    goto LABEL_21;
  }
  v11 = a1 + 8;
  if ( !*(_DWORD *)(a1 + 12) || a2 )
  {
    v10 = -2147352565;
    goto LABEL_20;
  }
  v12 = a1 + 24;
  v4 = a1 + 24;
  if ( a1 != -24 )
  {
    CRWLock2T<CEmptyType>::AcquireShared(a1 + 24);
    v5 = 1;
  }
  if ( !CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Find(
          v11,
          a3,
          v17) )
  {
    if ( v12 )
    {
      if ( v5 )
      {
        CRWLock2T<CEmptyType>::ReleaseLockEx(v12);
        v5 = 0;
      }
      CRWLock2T<CEmptyType>::AcquireExclusive(v12);
      v4 = 0;
      v7 = 1;
    }
    v6 = v12;
    if ( !CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Find(
            v11,
            a3,
            v17) )
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Find(
            v11,
            a3,
            v17)
      && !CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Find(
            v11,
            0,
            v17) )
    {
      v10 = -2147319765;
      goto LABEL_20;
    }
  }
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL * v17[0]);
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v13 + 48LL))(v13, &IID_ITokenActivation, a4);
  v10 = v14;
  if ( v14 < 0 )
  {
    v15 = (unsigned int)v14;
LABEL_21:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( v6 && v7 )
    CRWLock2T<CEmptyType>::ReleaseLockEx(v6);
  if ( v4 && v5 )
    CRWLock2T<CEmptyType>::ReleaseLockEx(v4);
  return v10;
}

```

## disassembly

```asm
0x18001c8c0  mov     [rsp+arg_18], r9
0x18001c8c5  push    rbx
0x18001c8c6  push    rbp
0x18001c8c7  push    rsi
0x18001c8c8  push    rdi
0x18001c8c9  push    r12
0x18001c8cb  push    r13
0x18001c8cd  push    r14
0x18001c8cf  push    r15
0x18001c8d1  sub     rsp, 38h
0x18001c8d5  xor     esi, esi
0x18001c8d7  xor     edi, edi
0x18001c8d9  xor     r14d, r14d
0x18001c8dc  mov     [rsp+78h+var_58], esi
0x18001c8e0  xor     r15d, r15d
0x18001c8e3  mov     r12d, r8d
0x18001c8e6  mov     r13, rcx
0x18001c8e9  test    r9, r9
0x18001c8ec  jnz     short loc_18001C8F8
0x18001c8ee  mov     ebx, 80004003h
0x18001c8f3  jmp     loc_18001C9E1
0x18001c8f8  lea     rbp, [rcx+8]
0x18001c8fc  cmp     [rbp+4], esi
0x18001c8ff  jz      loc_18001C9DC
0x18001c905  test    edx, edx
0x18001c907  jnz     loc_18001C9DC
0x18001c90d  lea     rbx, [rcx+18h]
0x18001c911  mov     rsi, rbx
0x18001c914  test    rbx, rbx
0x18001c917  jz      short loc_18001C926
0x18001c919  mov     rcx, rbx
0x18001c91c  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001c921  mov     edi, 1
0x18001c926  lea     r8, [rsp+78h+var_58]
0x18001c92b  mov     edx, r12d
0x18001c92e  mov     rcx, rbp
0x18001c931  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c936  test    al, al
0x18001c938  jnz     short loc_18001C9A7
0x18001c93a  test    rbx, rbx
0x18001c93d  jz      short loc_18001C95B
0x18001c93f  test    edi, edi
0x18001c941  jz      short loc_18001C94D
0x18001c943  mov     rcx, rbx
0x18001c946  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c94b  xor     edi, edi
0x18001c94d  mov     rcx, rbx
0x18001c950  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001c955  xor     esi, esi
0x18001c957  lea     r15d, [rsi+1]
0x18001c95b  lea     r8, [rsp+78h+var_58]
0x18001c960  mov     edx, r12d
0x18001c963  mov     rcx, rbp
0x18001c966  mov     r14, rbx
0x18001c969  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c96e  test    al, al
0x18001c970  jnz     short loc_18001C979
0x18001c972  xor     ecx, ecx
0x18001c974  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c979  lea     r8, [rsp+78h+var_58]
0x18001c97e  mov     edx, r12d
0x18001c981  mov     rcx, rbp
0x18001c984  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c989  test    al, al
0x18001c98b  jnz     short loc_18001C9A7
0x18001c98d  lea     r8, [rsp+78h+var_58]
0x18001c992  xor     edx, edx
0x18001c994  mov     rcx, rbp
0x18001c997  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c99c  test    al, al
0x18001c99e  jnz     short loc_18001C9A7
0x18001c9a0  mov     ebx, 8002802Bh
0x18001c9a5  jmp     short loc_18001C9E1
0x18001c9a7  mov     rcx, [r13+10h]
0x18001c9ab  lea     rdx, IID_ITokenActivation
0x18001c9b2  movsxd  rax, [rsp+78h+var_58]
0x18001c9b7  mov     r8, [rsp+78h+arg_18]
0x18001c9bf  add     rax, rax
0x18001c9c2  mov     rcx, [rcx+rax*8]
0x18001c9c6  mov     rax, [rcx]
0x18001c9c9  mov     rax, [rax+30h]
0x18001c9cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9d2  mov     ebx, eax
0x18001c9d4  test    eax, eax
0x18001c9d6  jns     short loc_18001C9E8
0x18001c9d8  mov     ecx, eax
0x18001c9da  jmp     short loc_18001C9E3
0x18001c9dc  mov     ebx, 8002000Bh
0x18001c9e1  mov     ecx, ebx
0x18001c9e3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c9e8  mov     ecx, ebx
0x18001c9ea  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c9ef  test    r14, r14
0x18001c9f2  jz      short loc_18001CA01
0x18001c9f4  test    r15d, r15d
0x18001c9f7  jz      short loc_18001CA01
0x18001c9f9  mov     rcx, r14
0x18001c9fc  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001ca01  test    rsi, rsi
0x18001ca04  jz      short loc_18001CA12
0x18001ca06  test    edi, edi
0x18001ca08  jz      short loc_18001CA12
0x18001ca0a  mov     rcx, rsi
0x18001ca0d  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001ca12  mov     eax, ebx
0x18001ca14  add     rsp, 38h
0x18001ca18  pop     r15
0x18001ca1a  pop     r14
0x18001ca1c  pop     r13
0x18001ca1e  pop     r12
0x18001ca20  pop     rdi
0x18001ca21  pop     rsi
0x18001ca22  pop     rbp
0x18001ca23  pop     rbx
0x18001ca24  retn
```
