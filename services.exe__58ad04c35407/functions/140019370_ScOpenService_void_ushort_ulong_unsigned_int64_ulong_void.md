# ScOpenService(void *,ushort *,ulong,unsigned __int64 *,ulong,void * *)

- ea: `0x140019370`
- end: `0x1400199aa`
- name: `?ScOpenService@@YAKPEAXPEAGKPEA_KKPEAPEAX@Z`
- size: `1594`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, wchar_t *String2@<rdx>, unsigned int@<r8d>, unsigned __int64 *@<r9>, unsigned int, void **)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400190a0`
- `0x140019200`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x140007130`
- `0x140011ba0`
- `0x1400135b0`
- `0x140013f60`
- `0x140013f90`
- `0x140017160`
- `0x140017230`
- `0x1400188fc`
- `0x140019370`
- `0x14001c100`
- `0x140020dbc`
- `0x1400216dc`
- `0x140021ef4`
- `0x1400291a8`
- `0x14004b1c0`
- `0x1400575b0`
- `0x140081770`
- `0x1400817f4`
- `0x1400818a8`
- `0x140094020`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140019402`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140019402`
- `RPCRT4!I_RpcSessionStrictContextHandle` at `0x140019443`
- `RPCRT4!I_RpcSessionStrictContextHandle` at `0x140019443`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1400194bc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1400194bc`
- `ntdll!RtlEqualSid` at `0x140019685`
- `ntdll!RtlEqualSid` at `0x140019685`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x140019667`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x140019667`
- `ntdll!RtlReleaseResource` at `0x1400194aa`
- `ntdll!RtlReleaseResource` at `0x1400195b7`
- `ntdll!RtlReleaseResource` at `0x1400197fb`
- `ntdll!RtlReleaseResource` at `0x1400198b3`
- `ntdll!RtlReleaseResource` at `0x140019940`
- `ntdll!RtlReleaseResource` at `0x1400194aa`
- `ntdll!RtlReleaseResource` at `0x1400195b7`
- `ntdll!RtlReleaseResource` at `0x1400197fb`
- `ntdll!RtlReleaseResource` at `0x1400198b3`
- `ntdll!RtlReleaseResource` at `0x140019940`
- `ntdll!RtlAcquireResourceShared` at `0x140019480`
- `ntdll!RtlAcquireResourceShared` at `0x140019480`
- `ntdll!RtlInitUnicodeString` at `0x140019639`
- `ntdll!RtlInitUnicodeString` at `0x140019639`
- `ntdll!RtlFreeHeap` at `0x1400196f7`
- `ntdll!RtlFreeHeap` at `0x1400197e4`
- `ntdll!RtlFreeHeap` at `0x14001989c`
- `ntdll!RtlFreeHeap` at `0x1400196f7`
- `ntdll!RtlFreeHeap` at `0x1400197e4`
- `ntdll!RtlFreeHeap` at `0x14001989c`
- `ntdll!RtlCreateServiceSid` at `0x14001964c`
- `ntdll!RtlCreateServiceSid` at `0x14001964c`

## string_xrefs

- `0x14001962c`: `TrustedInstaller`
- `0x140019706`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall ScOpenService(
        const wchar_t **a1,
        wchar_t *String2,
        unsigned int a3,
        unsigned __int64 *a4,
        char a5,
        void **a6)
{
  int v6; // r12d
  unsigned int IsClientLocal; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  BOOL v14; // r14d
  RPC_STATUS v15; // eax
  struct CServiceRecord *v16; // rdi
  int v17; // edx
  int v18; // r8d
  unsigned __int64 UserContext; // r14
  RTL_SRWLOCK *v20; // rcx
  BOOL v21; // ebx
  int v22; // r9d
  _DWORD *v23; // r14
  __int64 v24; // rdx
  int v25; // r8d
  signed __int64 v26; // rbx
  signed __int64 v27; // rbx
  __int64 v28; // rax
  int v29; // edx
  int v30; // r8d
  unsigned __int8 OwnerDefaulted[8]; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v33; // [rsp+48h] [rbp-B8h] BYREF
  struct CServiceRecord *v34; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int Pid; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v36; // [rsp+5Ch] [rbp-A4h]
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp-A0h] BYREF
  struct CServiceRecord *v38; // [rsp+68h] [rbp-98h] BYREF
  ULONG ServiceSidLength; // [rsp+70h] [rbp-90h] BYREF
  PSID Owner; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t **v42; // [rsp+88h] [rbp-78h]
  void **v43; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  _BYTE ServiceSid[80]; // [rsp+B0h] [rbp-50h] BYREF

  v6 = 0;
  v36 = a3;
  v42 = a1;
  v43 = a6;
  P = 0;
  v34 = 0;
  Pid = 0;
  Owner = 0;
  OwnerDefaulted[0] = 0;
  ServiceSidLength = 68;
  DestinationString = 0;
  if ( ScShutdownInProgress )
  {
    IsClientLocal = 1115;
    goto LABEL_70;
  }
  ClientLocalFlag = 0;
  LODWORD(v38) = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal )
    goto LABEL_67;
  v14 = ClientLocalFlag == 0;
  v33 = v14;
  if ( !ClientLocalFlag )
  {
    IsClientLocal = ScCheckProtocol(v12, v11, v13, &v38);
    if ( !IsClientLocal )
    {
      if ( !(_DWORD)v38 )
        I_RpcSessionStrictContextHandle();
      goto LABEL_8;
    }
LABEL_67:
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 21, WPP_1e8a53e398193c11e9533327b920648d_Traceguids, IsClientLocal);
    goto LABEL_70;
  }
LABEL_8:
  if ( !(unsigned int)ScIsValidScManagerHandle(a1) )
  {
    IsClientLocal = 6;
    goto LABEL_70;
  }
  if ( !(unsigned int)ScIsValidServiceName(String2) )
  {
    IsClientLocal = 123;
    goto LABEL_70;
  }
  RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v34);
  IsClientLocal = ScGetNamedServiceRecord(String2, &v34);
  if ( IsClientLocal )
  {
LABEL_13:
    RtlReleaseResource(&ScServiceRecordLock);
    goto LABEL_70;
  }
  v15 = I_RpcBindingInqLocalClientPID(0, &Pid);
  v16 = v34;
  if ( !v15 )
  {
    v6 = 1;
    if ( (*((_DWORD *)v34 + 13) & 0x100000) != 0 )
    {
      if ( a4 )
      {
        v38 = v34;
        if ( v34 )
          _InterlockedAdd((volatile signed __int32 *)v34 + 3, 1u);
        IsClientLocal = 1060;
        UserContext = ScGetUserContext();
        if ( !UserContext
          || (Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v34),
              (IsClientLocal = CServiceDatabase::FindServiceByUserContextAndTemplate(v20, UserContext, v16, &v34)) != 0) )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_Si(WPP_GLOBAL_Control->StubInfo, v17, v18, (_DWORD)String2, UserContext);
          }
          Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v38);
          goto LABEL_13;
        }
        Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v38);
        v16 = v34;
        v14 = v33;
      }
    }
  }
  CScmLock::LockAutoShared((char *)v16 + 312, &v33);
  if ( (a5 & 1) != 0 && (*((_DWORD *)v16 + 13) & 1) != 0 && (*((_BYTE *)v16 + 80) & 0x30) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        23,
        (unsigned int)WPP_1e8a53e398193c11e9533327b920648d_Traceguids,
        *((_QWORD *)v16 + 7),
        36);
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v33);
    RtlReleaseResource(&ScServiceRecordLock);
    IsClientLocal = 1060;
    goto LABEL_70;
  }
  IsClientLocal = ScCreateServiceHandle(v16, v6 != 0 ? Pid : 0, (struct _SC_HANDLE_STRUCT **)&P);
  if ( IsClientLocal )
  {
LABEL_34:
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v33);
    goto LABEL_13;
  }
  v21 = 0;
  RtlInitUnicodeString(&DestinationString, L"TrustedInstaller");
  if ( !RtlCreateServiceSid(&DestinationString, ServiceSid, &ServiceSidLength)
    && !RtlGetOwnerSecurityDescriptor(*((PSECURITY_DESCRIPTOR *)v16 + 18), &Owner, OwnerDefaulted)
    && Owner
    && !OwnerDefaulted[0] )
  {
    v21 = RtlEqualSid(ServiceSid, Owner) != 0;
  }
  v22 = v14;
  v23 = P;
  IsClientLocal = ScAccessValidate((struct _SC_HANDLE_STRUCT *)P, v36, v21, v22);
  if ( IsClientLocal )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x40000) != 0 )
    {
      WPP_SF_dS(
        WPP_GLOBAL_Control->StubInfo,
        24,
        (unsigned int)WPP_1e8a53e398193c11e9533327b920648d_Traceguids,
        IsClientLocal,
        (__int64)String2);
    }
LABEL_44:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    goto LABEL_34;
  }
  if ( wcsicmp(v42[2], L"ServicesActive") )
  {
    if ( (v36 & 0x2000000) != 0 )
    {
      v23[2] &= 0xFFFFFE0F;
    }
    else if ( (v23[2] & 0x1F0) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 0x10) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 25, WPP_1e8a53e398193c11e9533327b920648d_Traceguids, String2);
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v33);
      RtlReleaseResource(&ScServiceRecordLock);
      IsClientLocal = 5;
      goto LABEL_70;
    }
  }
  if ( !a4 )
    goto LABEL_64;
  if ( !(*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v16 + 160LL))(v16) )
  {
    IsClientLocal = 1062;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        26,
        (unsigned int)WPP_1e8a53e398193c11e9533327b920648d_Traceguids,
        (_DWORD)String2,
        38);
    goto LABEL_44;
  }
  v26 = *a4;
  v24 = *(_QWORD *)((*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v16 + 160LL))(v16) + 96);
  if ( v26 == _InterlockedCompareExchange64((volatile signed __int64 *)(v24 + 120), 0, v26) )
  {
LABEL_64:
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x40000) != 0 )
    {
      WPP_SF_SqLLd(
        WPP_GLOBAL_Control->StubInfo,
        v24,
        v25,
        *((_QWORD *)v16 + 7),
        (char)v23,
        v6 != 0 ? Pid : 0,
        v36,
        *((_DWORD *)v16 + 3));
    }
    v34 = 0;
    ScSetAndIncrementServiceHandlesCount((struct _SC_HANDLE_STRUCT *)v23, v16);
    *v43 = v23;
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v33);
    RtlReleaseResource(&ScServiceRecordLock);
    IsClientLocal = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v27 = *a4;
      v28 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)v16 + 160LL))(v16);
      WPP_SF_Siid(
        WPP_GLOBAL_Control->StubInfo,
        v29,
        v30,
        (_DWORD)String2,
        *(_QWORD *)(*(_QWORD *)(v28 + 96) + 120LL),
        v27);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)&v33);
    RtlReleaseResource(&ScServiceRecordLock);
    IsClientLocal = 776;
  }
LABEL_70:
  Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(&v34);
  return IsClientLocal;
}

```

## disassembly

```asm
0x140019370  push    rbp
0x140019372  push    rbx
0x140019373  push    rsi
0x140019374  push    rdi
0x140019375  push    r12
0x140019377  push    r13
0x140019379  push    r14
0x14001937b  push    r15
0x14001937d  lea     rbp, [rsp-18h]
0x140019382  sub     rsp, 118h
0x140019389  mov     rax, cs:__security_cookie
0x140019390  xor     rax, rsp
0x140019393  mov     [rbp+50h+var_50], rax
0x140019397  mov     rax, [rbp+50h+arg_28]
0x14001939e  xor     r12d, r12d
0x1400193a1  cmp     cs:?ScShutdownInProgress@@3KA, r12d; ulong ScShutdownInProgress
0x1400193a8  xorps   xmm0, xmm0
0x1400193ab  mov     r13, r9
0x1400193ae  mov     [rsp+150h+var_F4], r8d
0x1400193b3  mov     r15, rdx
0x1400193b6  mov     [rbp+50h+var_C8], rcx
0x1400193ba  mov     rdi, rcx
0x1400193bd  mov     [rbp+50h+var_C0], rax
0x1400193c1  mov     [rbp+50h+P], r12
0x1400193c5  mov     [rsp+150h+var_100], r12
0x1400193ca  mov     [rsp+150h+Pid], r12d
0x1400193cf  mov     [rsp+150h+Owner], r12
0x1400193d4  mov     [rsp+150h+OwnerDefaulted], r12b
0x1400193d9  mov     [rsp+150h+ServiceSidLength], 44h ; 'D'
0x1400193e1  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x1400193e5  jz      short loc_1400193F1
0x1400193e7  mov     ebx, 45Bh
0x1400193ec  jmp     loc_14001997E
0x1400193f1  lea     rdx, [rsp+150h+ClientLocalFlag]; ClientLocalFlag
0x1400193f6  mov     [rsp+150h+ClientLocalFlag], r12d
0x1400193fb  xor     ecx, ecx; BindingHandle
0x1400193fd  mov     dword ptr [rsp+150h+var_E8], r12d
0x140019402  call    cs:__imp_I_RpcBindingIsClientLocal
0x140019408  mov     ebx, eax
0x14001940a  test    eax, eax
0x14001940c  jnz     loc_14001994A
0x140019412  mov     eax, [rsp+150h+ClientLocalFlag]
0x140019416  mov     r14d, r12d
0x140019419  test    eax, eax
0x14001941b  setz    r14b
0x14001941f  mov     [rsp+150h+var_108], r14d
0x140019424  test    eax, eax
0x140019426  jnz     short loc_140019449
0x140019428  lea     r9, [rsp+150h+var_E8]
0x14001942d  call    ScCheckProtocol
0x140019432  mov     ebx, eax
0x140019434  test    eax, eax
0x140019436  jnz     loc_14001994A
0x14001943c  cmp     dword ptr [rsp+150h+var_E8], r12d
0x140019441  jnz     short loc_140019449
0x140019443  call    cs:__imp_I_RpcSessionStrictContextHandle
0x140019449  mov     rcx, rdi; void *
0x14001944c  call    ?ScIsValidScManagerHandle@@YAHPEAX@Z; ScIsValidScManagerHandle(void *)
0x140019451  test    eax, eax
0x140019453  jnz     short loc_14001945D
0x140019455  lea     ebx, [rax+6]
0x140019458  jmp     loc_14001997E
0x14001945d  mov     rcx, r15; unsigned __int16 *
0x140019460  call    ?ScIsValidServiceName@@YAHPEBG@Z; ScIsValidServiceName(ushort const *)
0x140019465  test    eax, eax
0x140019467  jnz     short loc_140019471
0x140019469  lea     ebx, [rax+7Bh]
0x14001946c  jmp     loc_14001997E
0x140019471  mov     esi, 1
0x140019476  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14001947d  mov     dl, sil; Wait
0x140019480  call    cs:__imp_RtlAcquireResourceShared
0x140019486  lea     rcx, [rsp+150h+var_100]
0x14001948b  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x140019490  lea     rdx, [rsp+150h+var_100]; struct CServiceRecord **
0x140019495  mov     rcx, r15; String2
0x140019498  call    ?ScGetNamedServiceRecord@@YAKPEBGPEAPEAVCServiceRecord@@@Z; ScGetNamedServiceRecord(ushort const *,CServiceRecord * *)
0x14001949d  mov     ebx, eax
0x14001949f  test    eax, eax
0x1400194a1  jz      short loc_1400194B5
0x1400194a3  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400194aa  call    cs:__imp_RtlReleaseResource
0x1400194b0  jmp     loc_14001997E
0x1400194b5  lea     rdx, [rsp+150h+Pid]; Pid
0x1400194ba  xor     ecx, ecx; Binding
0x1400194bc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1400194c2  mov     rdi, [rsp+150h+var_100]
0x1400194c7  test    eax, eax
0x1400194c9  jnz     short loc_140019538
0x1400194cb  mov     eax, [rdi+34h]
0x1400194ce  mov     r12d, esi
0x1400194d1  bt      eax, 14h
0x1400194d5  jnb     short loc_140019538
0x1400194d7  test    r13, r13
0x1400194da  jz      short loc_140019538
0x1400194dc  mov     [rsp+150h+var_E8], rdi
0x1400194e1  test    rdi, rdi
0x1400194e4  jz      short loc_1400194EA
0x1400194e6  lock add [rdi+0Ch], esi
0x1400194ea  mov     ebx, 424h
0x1400194ef  call    ?ScGetUserContext@@YA_KXZ; ScGetUserContext(void)
0x1400194f4  mov     r14, rax
0x1400194f7  test    rax, rax
0x1400194fa  jz      loc_1400195C7
0x140019500  lea     rcx, [rsp+150h+var_100]
0x140019505  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x14001950a  lea     r9, [rsp+150h+var_100]; struct CServiceRecord **
0x14001950f  mov     r8, rdi; struct CServiceRecord *
0x140019512  mov     rdx, r14; unsigned __int64
0x140019515  call    ?FindServiceByUserContextAndTemplate@CServiceDatabase@@QEAAK_KPEAVCServiceRecord@@PEAPEAV2@@Z; CServiceDatabase::FindServiceByUserContextAndTemplate(unsigned __int64,CServiceRecord *,CServiceRecord * *)
0x14001951a  mov     ebx, eax
0x14001951c  test    eax, eax
0x14001951e  jnz     loc_1400195C7
0x140019524  lea     rcx, [rsp+150h+var_E8]
0x140019529  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x14001952e  mov     rdi, [rsp+150h+var_100]
0x140019533  mov     r14d, [rsp+150h+var_108]
0x140019538  lea     rcx, [rdi+138h]
0x14001953f  lea     rdx, [rsp+150h+var_108]
0x140019544  call    ?LockAutoShared@CScmLock@@QEAA?AVCScmSyncLockShared@@XZ; CScmLock::LockAutoShared(void)
0x140019549  test    [rbp+50h+arg_20], sil
0x140019550  jz      loc_140019600
0x140019556  mov     eax, [rdi+34h]
0x140019559  test    sil, al
0x14001955c  jz      loc_140019600
0x140019562  test    byte ptr [rdi+50h], 30h
0x140019566  jz      loc_140019600
0x14001956c  mov     rcx, cs:WPP_GLOBAL_Control
0x140019573  lea     rax, WPP_GLOBAL_Control
0x14001957a  cmp     rcx, rax
0x14001957d  jz      short loc_1400195A6
0x14001957f  test    [rcx+1Ch], sil
0x140019583  jz      short loc_1400195A6
0x140019585  mov     r9, [rdi+38h]
0x140019589  lea     r8, WPP_1e8a53e398193c11e9533327b920648d_Traceguids
0x140019590  mov     rcx, [rcx+10h]
0x140019594  mov     edx, 17h
0x140019599  mov     dword ptr [rsp+150h+var_130], 424h
0x1400195a1  call    WPP_SF_Sd
0x1400195a6  lea     rcx, [rsp+150h+var_108]; this
0x1400195ab  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1400195b0  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400195b7  call    cs:__imp_RtlReleaseResource
0x1400195bd  mov     ebx, 424h
0x1400195c2  jmp     loc_14001997E
0x1400195c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195ce  lea     rax, WPP_GLOBAL_Control
0x1400195d5  cmp     rcx, rax
0x1400195d8  jz      short loc_1400195F1
0x1400195da  test    [rcx+1Ch], sil
0x1400195de  jz      short loc_1400195F1
0x1400195e0  mov     rcx, [rcx+10h]
0x1400195e4  mov     r9, r15
0x1400195e7  mov     [rsp+150h+var_130], r14
0x1400195ec  call    WPP_SF_Si
0x1400195f1  lea     rcx, [rsp+150h+var_E8]
0x1400195f6  call    ?InternalRelease@?$ComPtr@VCServiceRecord@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CServiceRecord>::InternalRelease(void)
0x1400195fb  jmp     loc_1400194A3
0x140019600  mov     eax, r12d
0x140019603  lea     r8, [rbp+50h+P]; struct _SC_HANDLE_STRUCT **
0x140019607  neg     eax
0x140019609  mov     rcx, rdi; struct CServiceRecord *
0x14001960c  sbb     edx, edx
0x14001960e  and     edx, [rsp+150h+Pid]; unsigned int
0x140019612  call    ?ScCreateServiceHandle@@YAKPEAVCServiceRecord@@KPEAPEAU_SC_HANDLE_STRUCT@@@Z; ScCreateServiceHandle(CServiceRecord *,ulong,_SC_HANDLE_STRUCT * *)
0x140019617  mov     ebx, eax
0x140019619  test    eax, eax
0x14001961b  jz      short loc_14001962C
0x14001961d  lea     rcx, [rsp+150h+var_108]; this
0x140019622  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x140019627  jmp     loc_1400194A3
0x14001962c  lea     rdx, aTrustedinstall; "TrustedInstaller"
0x140019633  xor     ebx, ebx
0x140019635  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140019639  call    cs:__imp_RtlInitUnicodeString
0x14001963f  lea     r8, [rsp+150h+ServiceSidLength]; ServiceSidLength
0x140019644  lea     rdx, [rbp+50h+ServiceSid]; ServiceSid
0x140019648  lea     rcx, [rbp+50h+DestinationString]; ServiceName
0x14001964c  call    cs:__imp_RtlCreateServiceSid
0x140019652  test    eax, eax
0x140019654  jnz     short loc_140019690
0x140019656  mov     rcx, [rdi+90h]; SecurityDescriptor
0x14001965d  lea     r8, [rsp+150h+OwnerDefaulted]; OwnerDefaulted
0x140019662  lea     rdx, [rsp+150h+Owner]; Owner
0x140019667  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14001966d  test    eax, eax
0x14001966f  jnz     short loc_140019690
0x140019671  mov     rdx, [rsp+150h+Owner]; Sid2
0x140019676  test    rdx, rdx
0x140019679  jz      short loc_140019690
0x14001967b  cmp     [rsp+150h+OwnerDefaulted], bl
0x14001967f  jnz     short loc_140019690
0x140019681  lea     rcx, [rbp+50h+ServiceSid]; Sid1
0x140019685  call    cs:__imp_RtlEqualSid
0x14001968b  test    al, al
0x14001968d  cmovnz  ebx, esi
0x140019690  mov     edx, [rsp+150h+var_F4]; unsigned int
0x140019694  mov     r9d, r14d; int
0x140019697  mov     r14, [rbp+50h+P]
0x14001969b  mov     r8d, ebx; int
0x14001969e  mov     rcx, r14; struct _SC_HANDLE_STRUCT *
0x1400196a1  call    ?ScAccessValidate@@YAKPEAU_SC_HANDLE_STRUCT@@KHH@Z; ScAccessValidate(_SC_HANDLE_STRUCT *,ulong,int,int)
0x1400196a6  mov     ebx, eax
0x1400196a8  test    eax, eax
0x1400196aa  jz      short loc_140019702
0x1400196ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196b3  lea     rax, WPP_GLOBAL_Control
0x1400196ba  cmp     rcx, rax
0x1400196bd  jz      short loc_1400196E5
0x1400196bf  test    dword ptr [rcx+1Ch], 40000h
0x1400196c6  jz      short loc_1400196E5
0x1400196c8  mov     rcx, [rcx+10h]
0x1400196cc  lea     r8, WPP_1e8a53e398193c11e9533327b920648d_Traceguids
0x1400196d3  mov     edx, 18h
0x1400196d8  mov     [rsp+150h+var_130], r15
0x1400196dd  mov     r9d, ebx
0x1400196e0  call    WPP_SF_dS
0x1400196e5  mov     rcx, gs:60h
0x1400196ee  mov     r8, r14; P
0x1400196f1  xor     edx, edx; Flags
0x1400196f3  mov     rcx, [rcx+30h]; HeapHandle
0x1400196f7  call    cs:__imp_RtlFreeHeap
0x1400196fd  jmp     loc_14001961D
0x140019702  mov     rcx, [rbp+50h+var_C8]
0x140019706  lea     rdx, aServicesactive; "ServicesActive"
0x14001970d  mov     rcx, [rcx+10h]; String1
0x140019711  call    _wcsicmp
0x140019716  test    eax, eax
0x140019718  jz      short loc_14001972C
0x14001971a  test    [rsp+150h+var_F4], 2000000h
0x140019722  jz      short loc_140019797
0x140019724  and     dword ptr [r14+8], 0FFFFFE0Fh
0x14001972c  test    r13, r13
0x14001972f  jz      loc_1400198C3
0x140019735  mov     rax, [rdi]
0x140019738  mov     rcx, rdi
0x14001973b  mov     rax, [rax+0A0h]
0x140019742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019747  test    rax, rax
0x14001974a  jnz     loc_14001980B
0x140019750  mov     rcx, cs:WPP_GLOBAL_Control
0x140019757  lea     rax, WPP_GLOBAL_Control
0x14001975e  mov     ebx, 426h
0x140019763  cmp     rcx, rax
0x140019766  jz      loc_1400196E5
0x14001976c  test    [rcx+1Ch], sil
0x140019770  jz      loc_1400196E5
0x140019776  mov     rcx, [rcx+10h]
0x14001977a  lea     r8, WPP_1e8a53e398193c11e9533327b920648d_Traceguids
0x140019781  mov     edx, 1Ah
0x140019786  mov     dword ptr [rsp+150h+var_130], ebx
0x14001978a  mov     r9, r15
0x14001978d  call    WPP_SF_Sd
0x140019792  jmp     loc_1400196E5
0x140019797  test    dword ptr [r14+8], 1F0h
0x14001979f  jz      short loc_14001972C
0x1400197a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400197a8  lea     rax, WPP_GLOBAL_Control
0x1400197af  cmp     rcx, rax
0x1400197b2  jz      short loc_1400197D2
0x1400197b4  test    byte ptr [rcx+1Ch], 10h
0x1400197b8  jz      short loc_1400197D2
0x1400197ba  mov     rcx, [rcx+10h]
0x1400197be  lea     r8, WPP_1e8a53e398193c11e9533327b920648d_Traceguids
0x1400197c5  mov     edx, 19h
0x1400197ca  mov     r9, r15
0x1400197cd  call    WPP_SF_S
0x1400197d2  mov     rcx, gs:60h
0x1400197db  mov     r8, r14; P
0x1400197de  xor     edx, edx; Flags
0x1400197e0  mov     rcx, [rcx+30h]; HeapHandle
0x1400197e4  call    cs:__imp_RtlFreeHeap
0x1400197ea  lea     rcx, [rsp+150h+var_108]; this
0x1400197ef  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1400197f4  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400197fb  call    cs:__imp_RtlReleaseResource
0x140019801  mov     ebx, 5
0x140019806  jmp     loc_14001997E
0x14001980b  mov     rcx, [rdi]
0x14001980e  mov     rbx, [r13+0]
0x140019812  mov     rax, [rcx+0A0h]
0x140019819  mov     rcx, rdi
0x14001981c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019821  xor     ecx, ecx
0x140019823  mov     rdx, [rax+60h]
0x140019827  mov     rax, rbx
0x14001982a  lock cmpxchg [rdx+78h], rcx
0x140019830  jz      loc_1400198C3
0x140019836  mov     rcx, cs:WPP_GLOBAL_Control
0x14001983d  lea     rax, WPP_GLOBAL_Control
0x140019844  cmp     rcx, rax
0x140019847  jz      short loc_14001988A
0x140019849  test    [rcx+1Ch], sil
0x14001984d  jz      short loc_14001988A
0x14001984f  mov     rax, [rdi]
0x140019852  mov     rcx, rdi
0x140019855  mov     rbx, [r13+0]
0x140019859  mov     rax, [rax+0A0h]
0x140019860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019865  mov     [rsp+150h+var_128], rbx
  ... truncated ...
```
