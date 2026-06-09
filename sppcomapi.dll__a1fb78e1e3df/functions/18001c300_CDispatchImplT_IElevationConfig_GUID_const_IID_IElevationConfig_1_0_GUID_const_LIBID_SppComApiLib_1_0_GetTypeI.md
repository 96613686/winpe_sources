# CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001c300`
- end: `0x18001c466`
- name: `?GetTypeInfo@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800033cc`
- `0x180003520`
- `0x1800038a8`
- `0x180004288`
- `0x180004340`
- `0x180004b00`
- `0x18001c300`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v13 + 48LL))(v13, &IID_IElevationConfig, a4);
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
0x18001c300  mov     [rsp+arg_18], r9
0x18001c305  push    rbx
0x18001c306  push    rbp
0x18001c307  push    rsi
0x18001c308  push    rdi
0x18001c309  push    r12
0x18001c30b  push    r13
0x18001c30d  push    r14
0x18001c30f  push    r15
0x18001c311  sub     rsp, 38h
0x18001c315  xor     esi, esi
0x18001c317  xor     edi, edi
0x18001c319  xor     r14d, r14d
0x18001c31c  mov     [rsp+78h+var_58], esi
0x18001c320  xor     r15d, r15d
0x18001c323  mov     r12d, r8d
0x18001c326  mov     r13, rcx
0x18001c329  test    r9, r9
0x18001c32c  jnz     short loc_18001C338
0x18001c32e  mov     ebx, 80004003h
0x18001c333  jmp     loc_18001C421
0x18001c338  lea     rbp, [rcx+8]
0x18001c33c  cmp     [rbp+4], esi
0x18001c33f  jz      loc_18001C41C
0x18001c345  test    edx, edx
0x18001c347  jnz     loc_18001C41C
0x18001c34d  lea     rbx, [rcx+18h]
0x18001c351  mov     rsi, rbx
0x18001c354  test    rbx, rbx
0x18001c357  jz      short loc_18001C366
0x18001c359  mov     rcx, rbx
0x18001c35c  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001c361  mov     edi, 1
0x18001c366  lea     r8, [rsp+78h+var_58]
0x18001c36b  mov     edx, r12d
0x18001c36e  mov     rcx, rbp
0x18001c371  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c376  test    al, al
0x18001c378  jnz     short loc_18001C3E7
0x18001c37a  test    rbx, rbx
0x18001c37d  jz      short loc_18001C39B
0x18001c37f  test    edi, edi
0x18001c381  jz      short loc_18001C38D
0x18001c383  mov     rcx, rbx
0x18001c386  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c38b  xor     edi, edi
0x18001c38d  mov     rcx, rbx
0x18001c390  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001c395  xor     esi, esi
0x18001c397  lea     r15d, [rsi+1]
0x18001c39b  lea     r8, [rsp+78h+var_58]
0x18001c3a0  mov     edx, r12d
0x18001c3a3  mov     rcx, rbp
0x18001c3a6  mov     r14, rbx
0x18001c3a9  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c3ae  test    al, al
0x18001c3b0  jnz     short loc_18001C3B9
0x18001c3b2  xor     ecx, ecx
0x18001c3b4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c3b9  lea     r8, [rsp+78h+var_58]
0x18001c3be  mov     edx, r12d
0x18001c3c1  mov     rcx, rbp
0x18001c3c4  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c3c9  test    al, al
0x18001c3cb  jnz     short loc_18001C3E7
0x18001c3cd  lea     r8, [rsp+78h+var_58]
0x18001c3d2  xor     edx, edx
0x18001c3d4  mov     rcx, rbp
0x18001c3d7  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c3dc  test    al, al
0x18001c3de  jnz     short loc_18001C3E7
0x18001c3e0  mov     ebx, 8002802Bh
0x18001c3e5  jmp     short loc_18001C421
0x18001c3e7  mov     rcx, [r13+10h]
0x18001c3eb  lea     rdx, IID_IElevationConfig
0x18001c3f2  movsxd  rax, [rsp+78h+var_58]
0x18001c3f7  mov     r8, [rsp+78h+arg_18]
0x18001c3ff  add     rax, rax
0x18001c402  mov     rcx, [rcx+rax*8]
0x18001c406  mov     rax, [rcx]
0x18001c409  mov     rax, [rax+30h]
0x18001c40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c412  mov     ebx, eax
0x18001c414  test    eax, eax
0x18001c416  jns     short loc_18001C428
0x18001c418  mov     ecx, eax
0x18001c41a  jmp     short loc_18001C423
0x18001c41c  mov     ebx, 8002000Bh
0x18001c421  mov     ecx, ebx
0x18001c423  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c428  mov     ecx, ebx
0x18001c42a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c42f  test    r14, r14
0x18001c432  jz      short loc_18001C441
0x18001c434  test    r15d, r15d
0x18001c437  jz      short loc_18001C441
0x18001c439  mov     rcx, r14
0x18001c43c  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c441  test    rsi, rsi
0x18001c444  jz      short loc_18001C452
0x18001c446  test    edi, edi
0x18001c448  jz      short loc_18001C452
0x18001c44a  mov     rcx, rsi
0x18001c44d  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c452  mov     eax, ebx
0x18001c454  add     rsp, 38h
0x18001c458  pop     r15
0x18001c45a  pop     r14
0x18001c45c  pop     r13
0x18001c45e  pop     r12
0x18001c460  pop     rdi
0x18001c461  pop     rsi
0x18001c462  pop     rbp
0x18001c463  pop     rbx
0x18001c464  retn
```
