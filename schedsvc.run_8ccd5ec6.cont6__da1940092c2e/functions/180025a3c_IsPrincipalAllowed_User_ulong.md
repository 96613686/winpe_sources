# IsPrincipalAllowed(User,ulong)

- ea: `0x180025a3c`
- end: `0x180025ddb`
- name: `?IsPrincipalAllowed@@YAJVUser@@K@Z`
- size: `927`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180047ee0`
- `0x18004e9d0`

## callees

- `0x180006a74`
- `0x180007b44`
- `0x18000fe50`
- `0x180011e40`
- `0x1800246a8`
- `0x1800258cc`
- `0x180025a3c`
- `0x180025de4`
- `0x180025e70`
- `0x18002f814`
- `0x180042200`
- `0x1800449bc`
- `0x18004595c`
- `0x18005a2bc`
- `0x18006acbc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025ccb`
- `msvcrt!_wcsicmp` at `0x180025ccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ce0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025c31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025ce0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b68`
- `RPCRT4!RpcImpersonateClient` at `0x180025a67`
- `RPCRT4!RpcImpersonateClient` at `0x180025a67`
- `RPCRT4!RpcRevertToSelf` at `0x180025ade`
- `RPCRT4!RpcRevertToSelf` at `0x180025b0b`
- `RPCRT4!RpcRevertToSelf` at `0x180025d6d`
- `RPCRT4!RpcRevertToSelf` at `0x180025db6`
- `RPCRT4!RpcRevertToSelf` at `0x180025ade`
- `RPCRT4!RpcRevertToSelf` at `0x180025b0b`
- `RPCRT4!RpcRevertToSelf` at `0x180025d6d`
- `RPCRT4!RpcRevertToSelf` at `0x180025db6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025c57`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025c57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180025d56`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180025da4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180025d56`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180025da4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180025d44`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180025d44`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180025d24`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180025d24`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsPrincipalAllowed(User *a1, int a2)
{
  RPC_STATUS v4; // eax
  EventManager *v5; // rcx
  RPC_STATUS v6; // ebx
  tsched *v7; // rcx
  int v8; // ebx
  char v9; // r15
  __int64 v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  const WCHAR ***Account; // rax
  const WCHAR *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r8
  void *v16; // rcx
  int v17; // eax
  __int64 v18; // r8
  const wchar_t ***v19; // rcx
  const wchar_t ***v20; // r9
  const wchar_t *v21; // rdx
  const wchar_t *v22; // rcx
  bool v23; // r14
  SC_HANDLE v24; // rax
  SC_HANDLE v25; // rsi
  SC_HANDLE v26; // rbx
  void *v28; // [rsp+20h] [rbp-50h]
  const struct _GUID *v29; // [rsp+28h] [rbp-48h]
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v31; // [rsp+38h] [rbp-38h]
  const unsigned __int16 *v32; // [rsp+40h] [rbp-30h]
  __int64 v33; // [rsp+48h] [rbp-28h]
  __int64 v34; // [rsp+50h] [rbp-20h]
  RPC_STATUS v35; // [rsp+58h] [rbp-18h]
  __int64 v36; // [rsp+5Ch] [rbp-14h]
  int v37; // [rsp+B8h] [rbp+48h] BYREF
  __int64 v38; // [rsp+C0h] [rbp+50h] BYREF
  char v39; // [rsp+C8h] [rbp+58h] BYREF

  v38 = 0;
  v37 = 1;
  v4 = RpcImpersonateClient(0);
  v6 = v4;
  if ( v4 )
  {
    EventManager::EvtReport(v5, &IMPERSONATION_FAILURE, L"IsPrincipalAllowed", v4, v28, v29);
    v31 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v32 = &qword_1800A8718;
    v33 = 0;
    v34 = 0;
    v35 = v6;
    v36 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v8 = User::FromImpersonationToken((struct User *)&v38, 0);
  if ( v8 >= 0 )
  {
    if ( (unsigned int)tsched::IsUserAdmin(v7) || (v9 = 0, User::IsLocalSystem((User *)&v38)) )
      v9 = 1;
    RpcRevertToSelf();
    if ( v9 && (a2 & 0x100000) != 0 )
      goto LABEL_55;
    v10 = *(_QWORD *)a1;
    if ( !*(_QWORD *)a1
      || *(_BYTE *)v10
      || !*(_QWORD *)(v10 + 32) && (int)User::UpdateEntry(a1) < 0
      || !*(_QWORD *)(*(_QWORD *)a1 + 32LL) )
    {
      goto LABEL_52;
    }
    v11 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    if ( !*(_QWORD *)a1 )
    {
      if ( v38 )
      {
LABEL_17:
        LeaveCriticalSection(v11);
LABEL_18:
        if ( !v9 || (a2 & 0x10000) == 0 && (a2 & 0x8000) == 0 && a2 >= 0 && !User::IsService(a1) )
        {
          if ( !User::IsServiceSid(a1) )
          {
LABEL_52:
            wmi::AutoRef<User::UserEntry>::Release(&v38);
            wmi::AutoRef<User::UserEntry>::Release(a1);
            return 2147942405LL;
          }
          Account = (const WCHAR ***)User::GetAccount(a1, &v39);
          if ( *Account )
            v13 = **Account;
          else
            v13 = 0;
          _bstr_t::~_bstr_t((_bstr_t *)&v39);
          RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v37, L"IsPrincipalAllowed", 1);
          v24 = OpenSCManagerW(0, 0, 1u);
          v25 = v24;
          if ( !v24 || (v26 = OpenServiceW(v24, v13, 0xF01FFu), CloseServiceHandle(v25), !v26) )
          {
            if ( v37 )
              RpcRevertToSelf();
            goto LABEL_52;
          }
          CloseServiceHandle(v26);
          if ( v37 )
            RpcRevertToSelf();
        }
LABEL_55:
        v8 = 0;
        goto LABEL_56;
      }
LABEL_30:
      LeaveCriticalSection(v11);
      goto LABEL_55;
    }
    if ( !v38 )
      goto LABEL_17;
    if ( User::IsAlias(a1) || User::IsAlias((User *)&v38) )
    {
      if ( !User::IsAlias(a1) || !User::IsAlias((User *)&v38) )
        goto LABEL_17;
    }
    else
    {
      if ( v15 == v14 )
        goto LABEL_30;
      v16 = *(void **)(v14 + 32);
      if ( v16 && *(_QWORD *)(v15 + 32) )
      {
        v17 = EqualSid(v16, *(PSID *)(v15 + 32));
        goto LABEL_45;
      }
    }
    if ( (unsigned __int8)_bstr_t::operator!(v14 + 8) || (unsigned __int8)_bstr_t::operator!(v18 + 8) )
      goto LABEL_17;
    if ( *v19 )
      v21 = **v19;
    else
      v21 = 0;
    if ( *v20 )
      v22 = **v20;
    else
      v22 = 0;
    v17 = _wcsicmp(v22, v21);
LABEL_45:
    v23 = v17 != 0;
    LeaveCriticalSection(v11);
    if ( v23 )
      goto LABEL_55;
    goto LABEL_18;
  }
  RpcRevertToSelf();
LABEL_56:
  wmi::AutoRef<User::UserEntry>::Release(&v38);
  wmi::AutoRef<User::UserEntry>::Release(a1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180025a3c  mov     [rsp-38h+arg_0], rcx
0x180025a41  push    rbp
0x180025a42  push    rbx
0x180025a43  push    rsi
0x180025a44  push    rdi
0x180025a45  push    r12
0x180025a47  push    r14
0x180025a49  push    r15
0x180025a4b  mov     rbp, rsp
0x180025a4e  sub     rsp, 70h
0x180025a52  mov     esi, edx
0x180025a54  mov     rdi, rcx
0x180025a57  xor     r12d, r12d
0x180025a5a  mov     [rbp+arg_10], r12
0x180025a5e  mov     [rbp+arg_8], 1
0x180025a65  xor     ecx, ecx; BindingHandle
0x180025a67  call    cs:__imp_RpcImpersonateClient
0x180025a6e  nop     dword ptr [rax+rax+00h]
0x180025a73  mov     ebx, eax
0x180025a75  test    eax, eax
0x180025a77  jz      short loc_180025ACD
0x180025a79  mov     r9d, eax; unsigned int
0x180025a7c  lea     r8, aIsprincipalall; "IsPrincipalAllowed"
0x180025a83  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x180025a8a  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x180025a8f  mov     [rbp+var_38], r12b
0x180025a93  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180025a9a  mov     [rbp+pExceptionObject], rax
0x180025a9e  lea     rax, qword_1800A8718
0x180025aa5  mov     [rbp+var_30], rax
0x180025aa9  mov     [rbp+var_28], r12
0x180025aad  mov     [rbp+var_20], r12
0x180025ab1  mov     [rbp+var_18], ebx
0x180025ab4  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180025abc  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180025ac3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180025ac7  call    _CxxThrowException_0
0x180025acd  xor     edx, edx; void *
0x180025acf  lea     rcx, [rbp+arg_10]; struct User *
0x180025ad3  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x180025ad8  mov     ebx, eax
0x180025ada  test    eax, eax
0x180025adc  jns     short loc_180025AEF
0x180025ade  call    cs:__imp_RpcRevertToSelf
0x180025ae5  nop     dword ptr [rax+rax+00h]
0x180025aea  jmp     loc_180025DC5
0x180025aef  call    ?IsUserAdmin@tsched@@YAHXZ; tsched::IsUserAdmin(void)
0x180025af4  test    eax, eax
0x180025af6  jnz     short loc_180025B08
0x180025af8  lea     rcx, [rbp+arg_10]; this
0x180025afc  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x180025b01  test    al, al
0x180025b03  mov     r15b, r12b
0x180025b06  jz      short loc_180025B0B
0x180025b08  mov     r15b, 1
0x180025b0b  call    cs:__imp_RpcRevertToSelf
0x180025b12  nop     dword ptr [rax+rax+00h]
0x180025b17  test    r15b, r15b
0x180025b1a  jz      short loc_180025B26
0x180025b1c  bt      esi, 14h
0x180025b20  jb      loc_180025DC2
0x180025b26  mov     rax, [rdi]
0x180025b29  test    rax, rax
0x180025b2c  jz      loc_180025D7A
0x180025b32  cmp     [rax], r12b
0x180025b35  jnz     loc_180025D7A
0x180025b3b  cmp     [rax+20h], r12
0x180025b3f  jnz     short loc_180025B51
0x180025b41  mov     rcx, rdi; this
0x180025b44  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180025b49  test    eax, eax
0x180025b4b  js      loc_180025D7A
0x180025b51  mov     rax, [rdi]
0x180025b54  cmp     [rax+20h], r12
0x180025b58  jz      loc_180025D7A
0x180025b5e  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180025b65  mov     rcx, rbx; lpCriticalSection
0x180025b68  call    cs:__imp_EnterCriticalSection
0x180025b6f  nop     dword ptr [rax+rax+00h]
0x180025b74  mov     rdx, [rdi]
0x180025b77  test    rdx, rdx
0x180025b7a  jnz     loc_180025C03
0x180025b80  cmp     [rbp+arg_10], r12
0x180025b84  jz      loc_180025C2E
0x180025b8a  mov     rcx, rbx; lpCriticalSection
0x180025b8d  call    cs:__imp_LeaveCriticalSection
0x180025b94  nop     dword ptr [rax+rax+00h]
0x180025b99  test    r15b, r15b
0x180025b9c  jz      short loc_180025BD3
0x180025b9e  mov     eax, esi
0x180025ba0  and     eax, 8000h
0x180025ba5  bt      esi, 10h
0x180025ba9  jb      loc_180025DC2
0x180025baf  test    eax, eax
0x180025bb1  jnz     loc_180025DC2
0x180025bb7  shr     esi, 1Fh
0x180025bba  test    sil, sil
0x180025bbd  jnz     loc_180025DC2
0x180025bc3  mov     rcx, rdi; this
0x180025bc6  call    ?IsService@User@@QEBA_NXZ; User::IsService(void)
0x180025bcb  test    al, al
0x180025bcd  jnz     loc_180025DC2
0x180025bd3  mov     rcx, rdi; this
0x180025bd6  call    ?IsServiceSid@User@@QEBA_NXZ; User::IsServiceSid(void)
0x180025bdb  test    al, al
0x180025bdd  jz      loc_180025D7A
0x180025be3  lea     rdx, [rbp+arg_18]
0x180025be7  mov     rcx, rdi
0x180025bea  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x180025bef  mov     rbx, [rax]
0x180025bf2  test    rbx, rbx
0x180025bf5  jz      loc_180025CFA
0x180025bfb  mov     rbx, [rbx]
0x180025bfe  jmp     loc_180025CFD
0x180025c03  mov     r8, [rbp+arg_10]
0x180025c07  test    r8, r8
0x180025c0a  jz      loc_180025B8A
0x180025c10  mov     rcx, rdi; this
0x180025c13  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180025c18  test    al, al
0x180025c1a  jnz     short loc_180025C65
0x180025c1c  lea     rcx, [rbp+arg_10]; this
0x180025c20  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180025c25  test    al, al
0x180025c27  jnz     short loc_180025C65
0x180025c29  cmp     r8, rdx
0x180025c2c  jnz     short loc_180025C42
0x180025c2e  mov     rcx, rbx; lpCriticalSection
0x180025c31  call    cs:__imp_LeaveCriticalSection
0x180025c38  nop     dword ptr [rax+rax+00h]
0x180025c3d  jmp     loc_180025DC2
0x180025c42  mov     rcx, [rdx+20h]; pSid1
0x180025c46  test    rcx, rcx
0x180025c49  jz      short loc_180025C86
0x180025c4b  mov     rax, [r8+20h]
0x180025c4f  test    rax, rax
0x180025c52  jz      short loc_180025C86
0x180025c54  mov     rdx, rax; pSid2
0x180025c57  call    cs:__imp_EqualSid
0x180025c5e  nop     dword ptr [rax+rax+00h]
0x180025c63  jmp     short loc_180025CD7
0x180025c65  mov     rcx, rdi; this
0x180025c68  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180025c6d  test    al, al
0x180025c6f  jz      loc_180025B8A
0x180025c75  lea     rcx, [rbp+arg_10]; this
0x180025c79  call    ?IsAlias@User@@QEBA_NXZ; User::IsAlias(void)
0x180025c7e  test    al, al
0x180025c80  jz      loc_180025B8A
0x180025c86  lea     r9, [rdx+8]
0x180025c8a  mov     rcx, r9
0x180025c8d  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180025c92  test    al, al
0x180025c94  jnz     loc_180025B8A
0x180025c9a  lea     rcx, [r8+8]
0x180025c9e  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x180025ca3  test    al, al
0x180025ca5  jnz     loc_180025B8A
0x180025cab  mov     rax, [rcx]
0x180025cae  test    rax, rax
0x180025cb1  jz      short loc_180025CB8
0x180025cb3  mov     rdx, [rax]
0x180025cb6  jmp     short loc_180025CBB
0x180025cb8  mov     rdx, r12; String2
0x180025cbb  mov     rax, [r9]
0x180025cbe  test    rax, rax
0x180025cc1  jz      short loc_180025CC8
0x180025cc3  mov     rcx, [rax]
0x180025cc6  jmp     short loc_180025CCB
0x180025cc8  mov     rcx, r12; String1
0x180025ccb  call    cs:__imp__wcsicmp
0x180025cd2  nop     dword ptr [rax+rax+00h]
0x180025cd7  test    eax, eax
0x180025cd9  setnz   r14b
0x180025cdd  mov     rcx, rbx; lpCriticalSection
0x180025ce0  call    cs:__imp_LeaveCriticalSection
0x180025ce7  nop     dword ptr [rax+rax+00h]
0x180025cec  test    r14b, r14b
0x180025cef  jnz     loc_180025DC2
0x180025cf5  jmp     loc_180025B99
0x180025cfa  mov     rbx, r12
0x180025cfd  lea     rcx, [rbp+arg_18]; this
0x180025d01  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180025d06  mov     r8d, 1; int
0x180025d0c  lea     rdx, aIsprincipalall; "IsPrincipalAllowed"
0x180025d13  lea     rcx, [rbp+arg_8]; this
0x180025d17  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180025d1c  xor     edx, edx; lpDatabaseName
0x180025d1e  xor     ecx, ecx; lpMachineName
0x180025d20  lea     r8d, [rdx+1]; dwDesiredAccess
0x180025d24  call    cs:__imp_OpenSCManagerW
0x180025d2b  nop     dword ptr [rax+rax+00h]
0x180025d30  mov     rsi, rax
0x180025d33  test    rax, rax
0x180025d36  jz      short loc_180025D67
0x180025d38  mov     r8d, 0F01FFh; dwDesiredAccess
0x180025d3e  mov     rdx, rbx; lpServiceName
0x180025d41  mov     rcx, rax; hSCManager
0x180025d44  call    cs:__imp_OpenServiceW
0x180025d4b  nop     dword ptr [rax+rax+00h]
0x180025d50  mov     rbx, rax
0x180025d53  mov     rcx, rsi; hSCObject
0x180025d56  call    cs:__imp_CloseServiceHandle
0x180025d5d  nop     dword ptr [rax+rax+00h]
0x180025d62  test    rbx, rbx
0x180025d65  jnz     short loc_180025DA1
0x180025d67  cmp     [rbp+arg_8], r12d
0x180025d6b  jz      short loc_180025D7A
0x180025d6d  call    cs:__imp_RpcRevertToSelf
0x180025d74  nop     dword ptr [rax+rax+00h]
0x180025d79  nop
0x180025d7a  lea     rcx, [rbp+arg_10]
0x180025d7e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180025d83  nop
0x180025d84  mov     rcx, rdi
0x180025d87  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180025d8c  mov     eax, 80070005h
0x180025d91  add     rsp, 70h
0x180025d95  pop     r15
0x180025d97  pop     r14
0x180025d99  pop     r12
0x180025d9b  pop     rdi
0x180025d9c  pop     rsi
0x180025d9d  pop     rbx
0x180025d9e  pop     rbp
0x180025d9f  retn
0x180025da1  mov     rcx, rbx; hSCObject
0x180025da4  call    cs:__imp_CloseServiceHandle
0x180025dab  nop     dword ptr [rax+rax+00h]
0x180025db0  cmp     [rbp+arg_8], r12d
0x180025db4  jz      short loc_180025DC2
0x180025db6  call    cs:__imp_RpcRevertToSelf
0x180025dbd  nop     dword ptr [rax+rax+00h]
0x180025dc2  mov     ebx, r12d
0x180025dc5  lea     rcx, [rbp+arg_10]
0x180025dc9  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180025dce  nop
0x180025dcf  mov     rcx, rdi
0x180025dd2  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180025dd7  mov     eax, ebx
0x180025dd9  jmp     short loc_180025D91
```
