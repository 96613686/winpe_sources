# CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001f5f0`
- end: `0x18001f756`
- name: `?GetTypeInfo@?$CDispatchImplT@UIOfflineActivationPhoneData@@$1?IID_IOfflineActivationPhoneData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
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
- `0x18001f5f0`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<IOfflineActivationPhoneData,&_GUID const IID_IOfflineActivationPhoneData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
          &IID_IOfflineActivationPhoneData,
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
0x18001f5f0  mov     [rsp+arg_18], r9
0x18001f5f5  push    rbx
0x18001f5f6  push    rbp
0x18001f5f7  push    rsi
0x18001f5f8  push    rdi
0x18001f5f9  push    r12
0x18001f5fb  push    r13
0x18001f5fd  push    r14
0x18001f5ff  push    r15
0x18001f601  sub     rsp, 38h
0x18001f605  xor     esi, esi
0x18001f607  xor     edi, edi
0x18001f609  xor     r14d, r14d
0x18001f60c  mov     [rsp+78h+var_58], esi
0x18001f610  xor     r15d, r15d
0x18001f613  mov     r12d, r8d
0x18001f616  mov     r13, rcx
0x18001f619  test    r9, r9
0x18001f61c  jnz     short loc_18001F628
0x18001f61e  mov     ebx, 80004003h
0x18001f623  jmp     loc_18001F711
0x18001f628  lea     rbp, [rcx+8]
0x18001f62c  cmp     [rbp+4], esi
0x18001f62f  jz      loc_18001F70C
0x18001f635  test    edx, edx
0x18001f637  jnz     loc_18001F70C
0x18001f63d  lea     rbx, [rcx+18h]
0x18001f641  mov     rsi, rbx
0x18001f644  test    rbx, rbx
0x18001f647  jz      short loc_18001F656
0x18001f649  mov     rcx, rbx
0x18001f64c  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001f651  mov     edi, 1
0x18001f656  lea     r8, [rsp+78h+var_58]
0x18001f65b  mov     edx, r12d
0x18001f65e  mov     rcx, rbp
0x18001f661  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f666  test    al, al
0x18001f668  jnz     short loc_18001F6D7
0x18001f66a  test    rbx, rbx
0x18001f66d  jz      short loc_18001F68B
0x18001f66f  test    edi, edi
0x18001f671  jz      short loc_18001F67D
0x18001f673  mov     rcx, rbx
0x18001f676  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001f67b  xor     edi, edi
0x18001f67d  mov     rcx, rbx
0x18001f680  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001f685  xor     esi, esi
0x18001f687  lea     r15d, [rsi+1]
0x18001f68b  lea     r8, [rsp+78h+var_58]
0x18001f690  mov     edx, r12d
0x18001f693  mov     rcx, rbp
0x18001f696  mov     r14, rbx
0x18001f699  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f69e  test    al, al
0x18001f6a0  jnz     short loc_18001F6A9
0x18001f6a2  xor     ecx, ecx
0x18001f6a4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f6a9  lea     r8, [rsp+78h+var_58]
0x18001f6ae  mov     edx, r12d
0x18001f6b1  mov     rcx, rbp
0x18001f6b4  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f6b9  test    al, al
0x18001f6bb  jnz     short loc_18001F6D7
0x18001f6bd  lea     r8, [rsp+78h+var_58]
0x18001f6c2  xor     edx, edx
0x18001f6c4  mov     rcx, rbp
0x18001f6c7  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001f6cc  test    al, al
0x18001f6ce  jnz     short loc_18001F6D7
0x18001f6d0  mov     ebx, 8002802Bh
0x18001f6d5  jmp     short loc_18001F711
0x18001f6d7  mov     rcx, [r13+10h]
0x18001f6db  lea     rdx, IID_IOfflineActivationPhoneData
0x18001f6e2  movsxd  rax, [rsp+78h+var_58]
0x18001f6e7  mov     r8, [rsp+78h+arg_18]
0x18001f6ef  add     rax, rax
0x18001f6f2  mov     rcx, [rcx+rax*8]
0x18001f6f6  mov     rax, [rcx]
0x18001f6f9  mov     rax, [rax+30h]
0x18001f6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f702  mov     ebx, eax
0x18001f704  test    eax, eax
0x18001f706  jns     short loc_18001F718
0x18001f708  mov     ecx, eax
0x18001f70a  jmp     short loc_18001F713
0x18001f70c  mov     ebx, 8002000Bh
0x18001f711  mov     ecx, ebx
0x18001f713  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001f718  mov     ecx, ebx
0x18001f71a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001f71f  test    r14, r14
0x18001f722  jz      short loc_18001F731
0x18001f724  test    r15d, r15d
0x18001f727  jz      short loc_18001F731
0x18001f729  mov     rcx, r14
0x18001f72c  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001f731  test    rsi, rsi
0x18001f734  jz      short loc_18001F742
0x18001f736  test    edi, edi
0x18001f738  jz      short loc_18001F742
0x18001f73a  mov     rcx, rsi
0x18001f73d  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001f742  mov     eax, ebx
0x18001f744  add     rsp, 38h
0x18001f748  pop     r15
0x18001f74a  pop     r14
0x18001f74c  pop     r13
0x18001f74e  pop     r12
0x18001f750  pop     rdi
0x18001f751  pop     rsi
0x18001f752  pop     rbp
0x18001f753  pop     rbx
0x18001f754  retn
```
