# CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18001c750`
- end: `0x18001c8b6`
- name: `?GetTypeInfo@?$CDispatchImplT@UIOnlineActivation@@$1?IID_IOnlineActivation@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
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
- `0x18001c750`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<IOnlineActivation,&_GUID const IID_IOnlineActivation,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v13 + 48LL))(v13, &IID_IOnlineActivation, a4);
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
0x18001c750  mov     [rsp+arg_18], r9
0x18001c755  push    rbx
0x18001c756  push    rbp
0x18001c757  push    rsi
0x18001c758  push    rdi
0x18001c759  push    r12
0x18001c75b  push    r13
0x18001c75d  push    r14
0x18001c75f  push    r15
0x18001c761  sub     rsp, 38h
0x18001c765  xor     esi, esi
0x18001c767  xor     edi, edi
0x18001c769  xor     r14d, r14d
0x18001c76c  mov     [rsp+78h+var_58], esi
0x18001c770  xor     r15d, r15d
0x18001c773  mov     r12d, r8d
0x18001c776  mov     r13, rcx
0x18001c779  test    r9, r9
0x18001c77c  jnz     short loc_18001C788
0x18001c77e  mov     ebx, 80004003h
0x18001c783  jmp     loc_18001C871
0x18001c788  lea     rbp, [rcx+8]
0x18001c78c  cmp     [rbp+4], esi
0x18001c78f  jz      loc_18001C86C
0x18001c795  test    edx, edx
0x18001c797  jnz     loc_18001C86C
0x18001c79d  lea     rbx, [rcx+18h]
0x18001c7a1  mov     rsi, rbx
0x18001c7a4  test    rbx, rbx
0x18001c7a7  jz      short loc_18001C7B6
0x18001c7a9  mov     rcx, rbx
0x18001c7ac  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x18001c7b1  mov     edi, 1
0x18001c7b6  lea     r8, [rsp+78h+var_58]
0x18001c7bb  mov     edx, r12d
0x18001c7be  mov     rcx, rbp
0x18001c7c1  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c7c6  test    al, al
0x18001c7c8  jnz     short loc_18001C837
0x18001c7ca  test    rbx, rbx
0x18001c7cd  jz      short loc_18001C7EB
0x18001c7cf  test    edi, edi
0x18001c7d1  jz      short loc_18001C7DD
0x18001c7d3  mov     rcx, rbx
0x18001c7d6  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c7db  xor     edi, edi
0x18001c7dd  mov     rcx, rbx
0x18001c7e0  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x18001c7e5  xor     esi, esi
0x18001c7e7  lea     r15d, [rsi+1]
0x18001c7eb  lea     r8, [rsp+78h+var_58]
0x18001c7f0  mov     edx, r12d
0x18001c7f3  mov     rcx, rbp
0x18001c7f6  mov     r14, rbx
0x18001c7f9  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c7fe  test    al, al
0x18001c800  jnz     short loc_18001C809
0x18001c802  xor     ecx, ecx
0x18001c804  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c809  lea     r8, [rsp+78h+var_58]
0x18001c80e  mov     edx, r12d
0x18001c811  mov     rcx, rbp
0x18001c814  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c819  test    al, al
0x18001c81b  jnz     short loc_18001C837
0x18001c81d  lea     r8, [rsp+78h+var_58]
0x18001c822  xor     edx, edx
0x18001c824  mov     rcx, rbp
0x18001c827  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18001c82c  test    al, al
0x18001c82e  jnz     short loc_18001C837
0x18001c830  mov     ebx, 8002802Bh
0x18001c835  jmp     short loc_18001C871
0x18001c837  mov     rcx, [r13+10h]
0x18001c83b  lea     rdx, IID_IOnlineActivation
0x18001c842  movsxd  rax, [rsp+78h+var_58]
0x18001c847  mov     r8, [rsp+78h+arg_18]
0x18001c84f  add     rax, rax
0x18001c852  mov     rcx, [rcx+rax*8]
0x18001c856  mov     rax, [rcx]
0x18001c859  mov     rax, [rax+30h]
0x18001c85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c862  mov     ebx, eax
0x18001c864  test    eax, eax
0x18001c866  jns     short loc_18001C878
0x18001c868  mov     ecx, eax
0x18001c86a  jmp     short loc_18001C873
0x18001c86c  mov     ebx, 8002000Bh
0x18001c871  mov     ecx, ebx
0x18001c873  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001c878  mov     ecx, ebx
0x18001c87a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001c87f  test    r14, r14
0x18001c882  jz      short loc_18001C891
0x18001c884  test    r15d, r15d
0x18001c887  jz      short loc_18001C891
0x18001c889  mov     rcx, r14
0x18001c88c  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c891  test    rsi, rsi
0x18001c894  jz      short loc_18001C8A2
0x18001c896  test    edi, edi
0x18001c898  jz      short loc_18001C8A2
0x18001c89a  mov     rcx, rsi
0x18001c89d  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18001c8a2  mov     eax, ebx
0x18001c8a4  add     rsp, 38h
0x18001c8a8  pop     r15
0x18001c8aa  pop     r14
0x18001c8ac  pop     r13
0x18001c8ae  pop     r12
0x18001c8b0  pop     rdi
0x18001c8b1  pop     rsi
0x18001c8b2  pop     rbp
0x18001c8b3  pop     rbx
0x18001c8b4  retn
```
