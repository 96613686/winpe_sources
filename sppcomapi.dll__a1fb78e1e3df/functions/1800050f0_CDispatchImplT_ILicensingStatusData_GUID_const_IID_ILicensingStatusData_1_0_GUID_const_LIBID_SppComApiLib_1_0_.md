# CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800050f0`
- end: `0x180005256`
- name: `?GetTypeInfo@?$CDispatchImplT@UILicensingStatusData@@$1?IID_ILicensingStatusData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJIKPEAPEAUITypeInfo@@@Z`
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
- `0x1800050f0`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfo(
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
          &IID_ILicensingStatusData,
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
0x1800050f0  mov     [rsp+arg_18], r9
0x1800050f5  push    rbx
0x1800050f6  push    rbp
0x1800050f7  push    rsi
0x1800050f8  push    rdi
0x1800050f9  push    r12
0x1800050fb  push    r13
0x1800050fd  push    r14
0x1800050ff  push    r15
0x180005101  sub     rsp, 38h
0x180005105  xor     esi, esi
0x180005107  xor     edi, edi
0x180005109  xor     r14d, r14d
0x18000510c  mov     [rsp+78h+var_58], esi
0x180005110  xor     r15d, r15d
0x180005113  mov     r12d, r8d
0x180005116  mov     r13, rcx
0x180005119  test    r9, r9
0x18000511c  jnz     short loc_180005128
0x18000511e  mov     ebx, 80004003h
0x180005123  jmp     loc_180005211
0x180005128  lea     rbp, [rcx+8]
0x18000512c  cmp     [rbp+4], esi
0x18000512f  jz      loc_18000520C
0x180005135  test    edx, edx
0x180005137  jnz     loc_18000520C
0x18000513d  lea     rbx, [rcx+18h]
0x180005141  mov     rsi, rbx
0x180005144  test    rbx, rbx
0x180005147  jz      short loc_180005156
0x180005149  mov     rcx, rbx
0x18000514c  call    ?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireShared(void)
0x180005151  mov     edi, 1
0x180005156  lea     r8, [rsp+78h+var_58]
0x18000515b  mov     edx, r12d
0x18000515e  mov     rcx, rbp
0x180005161  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x180005166  test    al, al
0x180005168  jnz     short loc_1800051D7
0x18000516a  test    rbx, rbx
0x18000516d  jz      short loc_18000518B
0x18000516f  test    edi, edi
0x180005171  jz      short loc_18000517D
0x180005173  mov     rcx, rbx
0x180005176  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x18000517b  xor     edi, edi
0x18000517d  mov     rcx, rbx
0x180005180  call    ?AcquireExclusive@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::AcquireExclusive(void)
0x180005185  xor     esi, esi
0x180005187  lea     r15d, [rsi+1]
0x18000518b  lea     r8, [rsp+78h+var_58]
0x180005190  mov     edx, r12d
0x180005193  mov     rcx, rbp
0x180005196  mov     r14, rbx
0x180005199  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x18000519e  test    al, al
0x1800051a0  jnz     short loc_1800051A9
0x1800051a2  xor     ecx, ecx
0x1800051a4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800051a9  lea     r8, [rsp+78h+var_58]
0x1800051ae  mov     edx, r12d
0x1800051b1  mov     rcx, rbp
0x1800051b4  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x1800051b9  test    al, al
0x1800051bb  jnz     short loc_1800051D7
0x1800051bd  lea     r8, [rsp+78h+var_58]
0x1800051c2  xor     edx, edx
0x1800051c4  mov     rcx, rbp
0x1800051c7  call    ?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z; CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)
0x1800051cc  test    al, al
0x1800051ce  jnz     short loc_1800051D7
0x1800051d0  mov     ebx, 8002802Bh
0x1800051d5  jmp     short loc_180005211
0x1800051d7  mov     rcx, [r13+10h]
0x1800051db  lea     rdx, IID_ILicensingStatusData
0x1800051e2  movsxd  rax, [rsp+78h+var_58]
0x1800051e7  mov     r8, [rsp+78h+arg_18]
0x1800051ef  add     rax, rax
0x1800051f2  mov     rcx, [rcx+rax*8]
0x1800051f6  mov     rax, [rcx]
0x1800051f9  mov     rax, [rax+30h]
0x1800051fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005202  mov     ebx, eax
0x180005204  test    eax, eax
0x180005206  jns     short loc_180005218
0x180005208  mov     ecx, eax
0x18000520a  jmp     short loc_180005213
0x18000520c  mov     ebx, 8002000Bh
0x180005211  mov     ecx, ebx
0x180005213  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005218  mov     ecx, ebx
0x18000521a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000521f  test    r14, r14
0x180005222  jz      short loc_180005231
0x180005224  test    r15d, r15d
0x180005227  jz      short loc_180005231
0x180005229  mov     rcx, r14
0x18000522c  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x180005231  test    rsi, rsi
0x180005234  jz      short loc_180005242
0x180005236  test    edi, edi
0x180005238  jz      short loc_180005242
0x18000523a  mov     rcx, rsi
0x18000523d  call    ?ReleaseLockEx@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ; CRWLock2T<CEmptyType>::ReleaseLockEx(void)
0x180005242  mov     eax, ebx
0x180005244  add     rsp, 38h
0x180005248  pop     r15
0x18000524a  pop     r14
0x18000524c  pop     r13
0x18000524e  pop     r12
0x180005250  pop     rdi
0x180005251  pop     rsi
0x180005252  pop     rbp
0x180005253  pop     rbx
0x180005254  retn
```
