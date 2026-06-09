# CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001f760`
- end: `0x18001f8c6`
- name: `?GetTypeInfo@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
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
- `0x18001f760`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v13 + 48LL))(
          v13,
          &IID_IOfflineActivationPhoneList,
          a4);
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
0x18001f760  mov     [rsp+arg_18], r9
0x18001f765  push    rbx
0x18001f766  push    rbp
0x18001f767  push    rsi
0x18001f768  push    rdi
0x18001f769  push    r12
0x18001f76b  push    r13
0x18001f76d  push    r14
0x18001f76f  push    r15
0x18001f771  sub     rsp, 38h
0x18001f775  xor     esi, esi
0x18001f777  xor     edi, edi
0x18001f779  xor     r14d, r14d
0x18001f77c  mov     [rsp+78h+var_58], esi
0x18001f780  xor     r15d, r15d
0x18001f783  mov     r12d, r8d
0x18001f786  mov     r13, rcx
0x18001f789  test    r9, r9
0x18001f78c  jnz     short loc_18001F798
0x18001f78e  mov     ebx, 80004003h
0x18001f793  jmp     loc_18001F881
0x18001f798  lea     rbp, [rcx+8]
0x18001f79c  cmp     [rbp+4], esi
0x18001f79f  jz      loc_18001F87C
0x18001f7a5  test    edx, edx
0x18001f7a7  jnz     loc_18001F87C
0x18001f7ad  lea     rbx, [rcx+18h]
0x18001f7b1  mov     rsi, rbx
0x18001f7b4  test    rbx, rbx
0x18001f7b7  jz      short loc_18001F7C6
0x18001f7b9  mov     rcx, rbx
0x18001f7bc  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001f7c1  mov     edi, 1
0x18001f7c6  lea     r8, [rsp+78h+var_58]
0x18001f7cb  mov     edx, r12d
0x18001f7ce  mov     rcx, rbp
0x18001f7d1  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f7d6  test    al, al
0x18001f7d8  jnz     short loc_18001F847
0x18001f7da  test    rbx, rbx
0x18001f7dd  jz      short loc_18001F7FB
0x18001f7df  test    edi, edi
0x18001f7e1  jz      short loc_18001F7ED
0x18001f7e3  mov     rcx, rbx
0x18001f7e6  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001f7eb  xor     edi, edi
0x18001f7ed  mov     rcx, rbx
0x18001f7f0  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001f7f5  xor     esi, esi
0x18001f7f7  lea     r15d, [rsi+1]
0x18001f7fb  lea     r8, [rsp+78h+var_58]
0x18001f800  mov     edx, r12d
0x18001f803  mov     rcx, rbp
0x18001f806  mov     r14, rbx
0x18001f809  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f80e  test    al, al
0x18001f810  jnz     short loc_18001F819
0x18001f812  xor     ecx, ecx
0x18001f814  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f819  lea     r8, [rsp+78h+var_58]
0x18001f81e  mov     edx, r12d
0x18001f821  mov     rcx, rbp
0x18001f824  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f829  test    al, al
0x18001f82b  jnz     short loc_18001F847
0x18001f82d  lea     r8, [rsp+78h+var_58]
0x18001f832  xor     edx, edx
0x18001f834  mov     rcx, rbp
0x18001f837  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f83c  test    al, al
0x18001f83e  jnz     short loc_18001F847
0x18001f840  mov     ebx, 8002802Bh
0x18001f845  jmp     short loc_18001F881
0x18001f847  mov     rcx, [r13+10h]
0x18001f84b  lea     rdx, IID_IOfflineActivationPhoneList
0x18001f852  movsxd  rax, [rsp+78h+var_58]
0x18001f857  mov     r8, [rsp+78h+arg_18]
0x18001f85f  add     rax, rax
0x18001f862  mov     rcx, [rcx+rax*8]
0x18001f866  mov     rax, [rcx]
0x18001f869  mov     rax, [rax+30h]
0x18001f86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f872  mov     ebx, eax
0x18001f874  test    eax, eax
0x18001f876  jns     short loc_18001F888
0x18001f878  mov     ecx, eax
0x18001f87a  jmp     short loc_18001F883
0x18001f87c  mov     ebx, 8002000Bh
0x18001f881  mov     ecx, ebx
0x18001f883  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f888  mov     ecx, ebx
0x18001f88a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f88f  test    r14, r14
0x18001f892  jz      short loc_18001F8A1
0x18001f894  test    r15d, r15d
0x18001f897  jz      short loc_18001F8A1
0x18001f899  mov     rcx, r14
0x18001f89c  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001f8a1  test    rsi, rsi
0x18001f8a4  jz      short loc_18001F8B2
0x18001f8a6  test    edi, edi
0x18001f8a8  jz      short loc_18001F8B2
0x18001f8aa  mov     rcx, rsi
0x18001f8ad  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001f8b2  mov     eax, ebx
0x18001f8b4  add     rsp, 38h
0x18001f8b8  pop     r15
0x18001f8ba  pop     r14
0x18001f8bc  pop     r13
0x18001f8be  pop     r12
0x18001f8c0  pop     rdi
0x18001f8c1  pop     rsi
0x18001f8c2  pop     rbp
0x18001f8c3  pop     rbx
0x18001f8c4  retn
```
