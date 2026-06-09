# CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001c5e0`
- end: `0x18001c746`
- name: `?GetTypeInfo@?$CDispatchImplT@UIOfflineActivation@@$1?IID_IOfflineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
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
- `0x18001c5e0`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<IOfflineActivation,&_GUID const IID_IOfflineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v13 + 48LL))(v13, &IID_IOfflineActivation, a4);
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
0x18001c5e0  mov     [rsp+arg_18], r9
0x18001c5e5  push    rbx
0x18001c5e6  push    rbp
0x18001c5e7  push    rsi
0x18001c5e8  push    rdi
0x18001c5e9  push    r12
0x18001c5eb  push    r13
0x18001c5ed  push    r14
0x18001c5ef  push    r15
0x18001c5f1  sub     rsp, 38h
0x18001c5f5  xor     esi, esi
0x18001c5f7  xor     edi, edi
0x18001c5f9  xor     r14d, r14d
0x18001c5fc  mov     [rsp+78h+var_58], esi
0x18001c600  xor     r15d, r15d
0x18001c603  mov     r12d, r8d
0x18001c606  mov     r13, rcx
0x18001c609  test    r9, r9
0x18001c60c  jnz     short loc_18001C618
0x18001c60e  mov     ebx, 80004003h
0x18001c613  jmp     loc_18001C701
0x18001c618  lea     rbp, [rcx+8]
0x18001c61c  cmp     [rbp+4], esi
0x18001c61f  jz      loc_18001C6FC
0x18001c625  test    edx, edx
0x18001c627  jnz     loc_18001C6FC
0x18001c62d  lea     rbx, [rcx+18h]
0x18001c631  mov     rsi, rbx
0x18001c634  test    rbx, rbx
0x18001c637  jz      short loc_18001C646
0x18001c639  mov     rcx, rbx
0x18001c63c  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001c641  mov     edi, 1
0x18001c646  lea     r8, [rsp+78h+var_58]
0x18001c64b  mov     edx, r12d
0x18001c64e  mov     rcx, rbp
0x18001c651  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c656  test    al, al
0x18001c658  jnz     short loc_18001C6C7
0x18001c65a  test    rbx, rbx
0x18001c65d  jz      short loc_18001C67B
0x18001c65f  test    edi, edi
0x18001c661  jz      short loc_18001C66D
0x18001c663  mov     rcx, rbx
0x18001c666  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c66b  xor     edi, edi
0x18001c66d  mov     rcx, rbx
0x18001c670  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001c675  xor     esi, esi
0x18001c677  lea     r15d, [rsi+1]
0x18001c67b  lea     r8, [rsp+78h+var_58]
0x18001c680  mov     edx, r12d
0x18001c683  mov     rcx, rbp
0x18001c686  mov     r14, rbx
0x18001c689  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c68e  test    al, al
0x18001c690  jnz     short loc_18001C699
0x18001c692  xor     ecx, ecx
0x18001c694  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c699  lea     r8, [rsp+78h+var_58]
0x18001c69e  mov     edx, r12d
0x18001c6a1  mov     rcx, rbp
0x18001c6a4  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c6a9  test    al, al
0x18001c6ab  jnz     short loc_18001C6C7
0x18001c6ad  lea     r8, [rsp+78h+var_58]
0x18001c6b2  xor     edx, edx
0x18001c6b4  mov     rcx, rbp
0x18001c6b7  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c6bc  test    al, al
0x18001c6be  jnz     short loc_18001C6C7
0x18001c6c0  mov     ebx, 8002802Bh
0x18001c6c5  jmp     short loc_18001C701
0x18001c6c7  mov     rcx, [r13+10h]
0x18001c6cb  lea     rdx, IID_IOfflineActivation
0x18001c6d2  movsxd  rax, [rsp+78h+var_58]
0x18001c6d7  mov     r8, [rsp+78h+arg_18]
0x18001c6df  add     rax, rax
0x18001c6e2  mov     rcx, [rcx+rax*8]
0x18001c6e6  mov     rax, [rcx]
0x18001c6e9  mov     rax, [rax+30h]
0x18001c6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6f2  mov     ebx, eax
0x18001c6f4  test    eax, eax
0x18001c6f6  jns     short loc_18001C708
0x18001c6f8  mov     ecx, eax
0x18001c6fa  jmp     short loc_18001C703
0x18001c6fc  mov     ebx, 8002000Bh
0x18001c701  mov     ecx, ebx
0x18001c703  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c708  mov     ecx, ebx
0x18001c70a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c70f  test    r14, r14
0x18001c712  jz      short loc_18001C721
0x18001c714  test    r15d, r15d
0x18001c717  jz      short loc_18001C721
0x18001c719  mov     rcx, r14
0x18001c71c  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c721  test    rsi, rsi
0x18001c724  jz      short loc_18001C732
0x18001c726  test    edi, edi
0x18001c728  jz      short loc_18001C732
0x18001c72a  mov     rcx, rsi
0x18001c72d  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c732  mov     eax, ebx
0x18001c734  add     rsp, 38h
0x18001c738  pop     r15
0x18001c73a  pop     r14
0x18001c73c  pop     r13
0x18001c73e  pop     r12
0x18001c740  pop     rdi
0x18001c741  pop     rsi
0x18001c742  pop     rbp
0x18001c743  pop     rbx
0x18001c744  retn
```
