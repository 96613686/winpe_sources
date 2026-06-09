# CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001c470`
- end: `0x18001c5d6`
- name: `?GetTypeInfo@?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
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
- `0x18001c470`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
          &IID_ILicensingStateTools,
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
0x18001c470  mov     [rsp+arg_18], r9
0x18001c475  push    rbx
0x18001c476  push    rbp
0x18001c477  push    rsi
0x18001c478  push    rdi
0x18001c479  push    r12
0x18001c47b  push    r13
0x18001c47d  push    r14
0x18001c47f  push    r15
0x18001c481  sub     rsp, 38h
0x18001c485  xor     esi, esi
0x18001c487  xor     edi, edi
0x18001c489  xor     r14d, r14d
0x18001c48c  mov     [rsp+78h+var_58], esi
0x18001c490  xor     r15d, r15d
0x18001c493  mov     r12d, r8d
0x18001c496  mov     r13, rcx
0x18001c499  test    r9, r9
0x18001c49c  jnz     short loc_18001C4A8
0x18001c49e  mov     ebx, 80004003h
0x18001c4a3  jmp     loc_18001C591
0x18001c4a8  lea     rbp, [rcx+8]
0x18001c4ac  cmp     [rbp+4], esi
0x18001c4af  jz      loc_18001C58C
0x18001c4b5  test    edx, edx
0x18001c4b7  jnz     loc_18001C58C
0x18001c4bd  lea     rbx, [rcx+18h]
0x18001c4c1  mov     rsi, rbx
0x18001c4c4  test    rbx, rbx
0x18001c4c7  jz      short loc_18001C4D6
0x18001c4c9  mov     rcx, rbx
0x18001c4cc  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001c4d1  mov     edi, 1
0x18001c4d6  lea     r8, [rsp+78h+var_58]
0x18001c4db  mov     edx, r12d
0x18001c4de  mov     rcx, rbp
0x18001c4e1  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c4e6  test    al, al
0x18001c4e8  jnz     short loc_18001C557
0x18001c4ea  test    rbx, rbx
0x18001c4ed  jz      short loc_18001C50B
0x18001c4ef  test    edi, edi
0x18001c4f1  jz      short loc_18001C4FD
0x18001c4f3  mov     rcx, rbx
0x18001c4f6  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c4fb  xor     edi, edi
0x18001c4fd  mov     rcx, rbx
0x18001c500  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001c505  xor     esi, esi
0x18001c507  lea     r15d, [rsi+1]
0x18001c50b  lea     r8, [rsp+78h+var_58]
0x18001c510  mov     edx, r12d
0x18001c513  mov     rcx, rbp
0x18001c516  mov     r14, rbx
0x18001c519  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c51e  test    al, al
0x18001c520  jnz     short loc_18001C529
0x18001c522  xor     ecx, ecx
0x18001c524  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c529  lea     r8, [rsp+78h+var_58]
0x18001c52e  mov     edx, r12d
0x18001c531  mov     rcx, rbp
0x18001c534  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c539  test    al, al
0x18001c53b  jnz     short loc_18001C557
0x18001c53d  lea     r8, [rsp+78h+var_58]
0x18001c542  xor     edx, edx
0x18001c544  mov     rcx, rbp
0x18001c547  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c54c  test    al, al
0x18001c54e  jnz     short loc_18001C557
0x18001c550  mov     ebx, 8002802Bh
0x18001c555  jmp     short loc_18001C591
0x18001c557  mov     rcx, [r13+10h]
0x18001c55b  lea     rdx, IID_ILicensingStateTools
0x18001c562  movsxd  rax, [rsp+78h+var_58]
0x18001c567  mov     r8, [rsp+78h+arg_18]
0x18001c56f  add     rax, rax
0x18001c572  mov     rcx, [rcx+rax*8]
0x18001c576  mov     rax, [rcx]
0x18001c579  mov     rax, [rax+30h]
0x18001c57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c582  mov     ebx, eax
0x18001c584  test    eax, eax
0x18001c586  jns     short loc_18001C598
0x18001c588  mov     ecx, eax
0x18001c58a  jmp     short loc_18001C593
0x18001c58c  mov     ebx, 8002000Bh
0x18001c591  mov     ecx, ebx
0x18001c593  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c598  mov     ecx, ebx
0x18001c59a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c59f  test    r14, r14
0x18001c5a2  jz      short loc_18001C5B1
0x18001c5a4  test    r15d, r15d
0x18001c5a7  jz      short loc_18001C5B1
0x18001c5a9  mov     rcx, r14
0x18001c5ac  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c5b1  test    rsi, rsi
0x18001c5b4  jz      short loc_18001C5C2
0x18001c5b6  test    edi, edi
0x18001c5b8  jz      short loc_18001C5C2
0x18001c5ba  mov     rcx, rsi
0x18001c5bd  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c5c2  mov     eax, ebx
0x18001c5c4  add     rsp, 38h
0x18001c5c8  pop     r15
0x18001c5ca  pop     r14
0x18001c5cc  pop     r13
0x18001c5ce  pop     r12
0x18001c5d0  pop     rdi
0x18001c5d1  pop     rsi
0x18001c5d2  pop     rbp
0x18001c5d3  pop     rbx
0x18001c5d4  retn
```
