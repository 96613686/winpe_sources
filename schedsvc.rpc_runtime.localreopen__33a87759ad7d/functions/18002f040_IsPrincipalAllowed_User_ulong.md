# IsPrincipalAllowed(User,ulong)

- ea: `0x18002f040`
- end: `0x18002f356`
- name: `?IsPrincipalAllowed@@YAJVUser@@K@Z`
- size: `790`
- prototype: `__int64 __fastcall(User *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180045df0`
- `0x18004c6d0`

## callees

- `0x18000b4e0`
- `0x18000dc30`
- `0x18001239c`
- `0x18001351c`
- `0x18002ab20`
- `0x18002eeec`
- `0x18002f040`
- `0x18002f35c`
- `0x18002f3e0`
- `0x180039b6c`
- `0x180040590`
- `0x180042f40`
- `0x18005790c`
- `0x1800679e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002f277`
- `msvcrt!_wcsicmp` at `0x18002f277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f175`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f286`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f175`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f286`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f15a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f15a`
- `RPCRT4!RpcImpersonateClient` at `0x18002f06b`
- `RPCRT4!RpcImpersonateClient` at `0x18002f06b`
- `RPCRT4!RpcRevertToSelf` at `0x18002f0dc`
- `RPCRT4!RpcRevertToSelf` at `0x18002f103`
- `RPCRT4!RpcRevertToSelf` at `0x18002f2fb`
- `RPCRT4!RpcRevertToSelf` at `0x18002f337`
- `RPCRT4!RpcRevertToSelf` at `0x18002f0dc`
- `RPCRT4!RpcRevertToSelf` at `0x18002f103`
- `RPCRT4!RpcRevertToSelf` at `0x18002f2fb`
- `RPCRT4!RpcRevertToSelf` at `0x18002f337`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002f221`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002f221`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002f2ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002f32b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002f2ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002f32b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002f2de`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002f2de`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002f2c4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002f2c4`

## pseudocode

```c
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
  __int64 v12; // rax
  const WCHAR ***Account; // rax
  const WCHAR *v14; // rbx
  void *v15; // rcx
  void *v16; // rdx
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
    v32 = &qword_1800A4718;
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
      goto LABEL_54;
    v10 = *(_QWORD *)a1;
    if ( !*(_QWORD *)a1
      || *(_BYTE *)v10
      || !*(_QWORD *)(v10 + 32) && (int)User::UpdateEntry(a1) < 0
      || !*(_QWORD *)(*(_QWORD *)a1 + 32LL) )
    {
      goto LABEL_51;
    }
    v11 = User::s_cs;
    EnterCriticalSection(User::s_cs);
    v12 = *(_QWORD *)a1;
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
LABEL_51:
            wmi::AutoRef<User::UserEntry>::Release(&v38);
            wmi::AutoRef<User::UserEntry>::Release(a1);
            return 2147942405LL;
          }
          Account = (const WCHAR ***)User::GetAccount(a1, &v39);
          if ( *Account )
            v14 = **Account;
          else
            v14 = 0;
          _bstr_t::~_bstr_t((_bstr_t *)&v39);
          RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v37, L"IsPrincipalAllowed", 1);
          v24 = OpenSCManagerW(0, 0, 1u);
          v25 = v24;
          if ( !v24 || (v26 = OpenServiceW(v24, v14, 0xF01FFu), CloseServiceHandle(v25), !v26) )
          {
            if ( v37 )
              RpcRevertToSelf();
            goto LABEL_51;
          }
          CloseServiceHandle(v26);
          if ( v37 )
            RpcRevertToSelf();
        }
LABEL_54:
        v8 = 0;
        goto LABEL_55;
      }
LABEL_30:
      LeaveCriticalSection(v11);
      goto LABEL_54;
    }
    if ( !v38 )
      goto LABEL_17;
    if ( *(_BYTE *)v12 )
    {
      if ( !*(_BYTE *)v38 )
        goto LABEL_17;
    }
    else
    {
      if ( *(_BYTE *)v38 )
        goto LABEL_17;
      if ( v38 == v12 )
        goto LABEL_30;
      v15 = *(void **)(v12 + 32);
      if ( v15 )
      {
        v16 = *(void **)(v38 + 32);
        if ( v16 )
        {
          v17 = EqualSid(v15, v16);
          goto LABEL_44;
        }
      }
    }
    if ( (unsigned __int8)_bstr_t::operator!(v12 + 8) || (unsigned __int8)_bstr_t::operator!(v18 + 8) )
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
LABEL_44:
    v23 = v17 != 0;
    LeaveCriticalSection(v11);
    if ( v23 )
      goto LABEL_54;
    goto LABEL_18;
  }
  RpcRevertToSelf();
LABEL_55:
  wmi::AutoRef<User::UserEntry>::Release(&v38);
  wmi::AutoRef<User::UserEntry>::Release(a1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002f040  mov     [rsp-38h+arg_0], rcx
0x18002f045  push    rbp
0x18002f046  push    rbx
0x18002f047  push    rsi
0x18002f048  push    rdi
0x18002f049  push    r12
0x18002f04b  push    r14
0x18002f04d  push    r15
0x18002f04f  mov     rbp, rsp
0x18002f052  sub     rsp, 70h
0x18002f056  mov     esi, edx
0x18002f058  mov     rdi, rcx
0x18002f05b  xor     r12d, r12d
0x18002f05e  mov     [rbp+arg_10], r12
0x18002f062  mov     [rbp+arg_8], 1
0x18002f069  xor     ecx, ecx; BindingHandle
0x18002f06b  call    cs:__imp_RpcImpersonateClient
0x18002f071  mov     ebx, eax
0x18002f073  test    eax, eax
0x18002f075  jz      short loc_18002F0CB
0x18002f077  mov     r9d, eax; unsigned int
0x18002f07a  lea     r8, aIsprincipalall; "IsPrincipalAllowed"
0x18002f081  lea     rdx, IMPERSONATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x18002f088  call    ?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGKPEAXPEBU_GUID@@@Z; EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ulong,void *,_GUID const *)
0x18002f08d  mov     [rbp+var_38], r12b
0x18002f091  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18002f098  mov     [rbp+pExceptionObject], rax
0x18002f09c  lea     rax, qword_1800A4718
0x18002f0a3  mov     [rbp+var_30], rax
0x18002f0a7  mov     [rbp+var_28], r12
0x18002f0ab  mov     [rbp+var_20], r12
0x18002f0af  mov     [rbp+var_18], ebx
0x18002f0b2  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18002f0ba  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18002f0c1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002f0c5  call    _CxxThrowException_0
0x18002f0cb  xor     edx, edx; void *
0x18002f0cd  lea     rcx, [rbp+arg_10]; struct User *
0x18002f0d1  call    ?FromImpersonationToken@User@@SAJAEAV1@PEAX@Z; User::FromImpersonationToken(User &,void *)
0x18002f0d6  mov     ebx, eax
0x18002f0d8  test    eax, eax
0x18002f0da  jns     short loc_18002F0E7
0x18002f0dc  call    cs:__imp_RpcRevertToSelf
0x18002f0e2  jmp     loc_18002F340
0x18002f0e7  call    ?IsUserAdmin@tsched@@YAHXZ; tsched::IsUserAdmin(void)
0x18002f0ec  test    eax, eax
0x18002f0ee  jnz     short loc_18002F100
0x18002f0f0  lea     rcx, [rbp+arg_10]; this
0x18002f0f4  call    ?IsLocalSystem@User@@QEBA_NXZ; User::IsLocalSystem(void)
0x18002f0f9  test    al, al
0x18002f0fb  mov     r15b, r12b
0x18002f0fe  jz      short loc_18002F103
0x18002f100  mov     r15b, 1
0x18002f103  call    cs:__imp_RpcRevertToSelf
0x18002f109  test    r15b, r15b
0x18002f10c  jz      short loc_18002F118
0x18002f10e  bt      esi, 14h
0x18002f112  jb      loc_18002F33D
0x18002f118  mov     rax, [rdi]
0x18002f11b  test    rax, rax
0x18002f11e  jz      loc_18002F302
0x18002f124  cmp     [rax], r12b
0x18002f127  jnz     loc_18002F302
0x18002f12d  cmp     [rax+20h], r12
0x18002f131  jnz     short loc_18002F143
0x18002f133  mov     rcx, rdi; this
0x18002f136  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18002f13b  test    eax, eax
0x18002f13d  js      loc_18002F302
0x18002f143  mov     rax, [rdi]
0x18002f146  cmp     [rax+20h], r12
0x18002f14a  jz      loc_18002F302
0x18002f150  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18002f157  mov     rcx, rbx; lpCriticalSection
0x18002f15a  call    cs:__imp_EnterCriticalSection
0x18002f160  mov     rax, [rdi]
0x18002f163  test    rax, rax
0x18002f166  jnz     short loc_18002F1E5
0x18002f168  cmp     [rbp+arg_10], r12
0x18002f16c  jz      loc_18002F201
0x18002f172  mov     rcx, rbx; lpCriticalSection
0x18002f175  call    cs:__imp_LeaveCriticalSection
0x18002f17b  test    r15b, r15b
0x18002f17e  jz      short loc_18002F1B5
0x18002f180  mov     eax, esi
0x18002f182  and     eax, 8000h
0x18002f187  bt      esi, 10h
0x18002f18b  jb      loc_18002F33D
0x18002f191  test    eax, eax
0x18002f193  jnz     loc_18002F33D
0x18002f199  shr     esi, 1Fh
0x18002f19c  test    sil, sil
0x18002f19f  jnz     loc_18002F33D
0x18002f1a5  mov     rcx, rdi; this
0x18002f1a8  call    ?IsService@User@@QEBA_NXZ; User::IsService(void)
0x18002f1ad  test    al, al
0x18002f1af  jnz     loc_18002F33D
0x18002f1b5  mov     rcx, rdi; this
0x18002f1b8  call    ?IsServiceSid@User@@QEBA_NXZ; User::IsServiceSid(void)
0x18002f1bd  test    al, al
0x18002f1bf  jz      loc_18002F302
0x18002f1c5  lea     rdx, [rbp+arg_18]
0x18002f1c9  mov     rcx, rdi
0x18002f1cc  call    ?GetAccount@User@@QEBA?BV_bstr_t@@XZ; User::GetAccount(void)
0x18002f1d1  mov     rbx, [rax]
0x18002f1d4  test    rbx, rbx
0x18002f1d7  jz      loc_18002F29A
0x18002f1dd  mov     rbx, [rbx]
0x18002f1e0  jmp     loc_18002F29D
0x18002f1e5  mov     r8, [rbp+arg_10]
0x18002f1e9  test    r8, r8
0x18002f1ec  jz      short loc_18002F172
0x18002f1ee  cmp     [rax], r12b
0x18002f1f1  jnz     short loc_18002F229
0x18002f1f3  cmp     [r8], r12b
0x18002f1f6  jnz     loc_18002F172
0x18002f1fc  cmp     r8, rax
0x18002f1ff  jnz     short loc_18002F20F
0x18002f201  mov     rcx, rbx; lpCriticalSection
0x18002f204  call    cs:__imp_LeaveCriticalSection
0x18002f20a  jmp     loc_18002F33D
0x18002f20f  mov     rcx, [rax+20h]; pSid1
0x18002f213  test    rcx, rcx
0x18002f216  jz      short loc_18002F232
0x18002f218  mov     rdx, [r8+20h]; pSid2
0x18002f21c  test    rdx, rdx
0x18002f21f  jz      short loc_18002F232
0x18002f221  call    cs:__imp_EqualSid
0x18002f227  jmp     short loc_18002F27D
0x18002f229  cmp     [r8], r12b
0x18002f22c  jz      loc_18002F172
0x18002f232  lea     r9, [rax+8]
0x18002f236  mov     rcx, r9
0x18002f239  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18002f23e  test    al, al
0x18002f240  jnz     loc_18002F172
0x18002f246  lea     rcx, [r8+8]
0x18002f24a  call    ??7_bstr_t@@QEBA_NXZ; _bstr_t::operator!(void)
0x18002f24f  test    al, al
0x18002f251  jnz     loc_18002F172
0x18002f257  mov     rax, [rcx]
0x18002f25a  test    rax, rax
0x18002f25d  jz      short loc_18002F264
0x18002f25f  mov     rdx, [rax]
0x18002f262  jmp     short loc_18002F267
0x18002f264  mov     rdx, r12; String2
0x18002f267  mov     rax, [r9]
0x18002f26a  test    rax, rax
0x18002f26d  jz      short loc_18002F274
0x18002f26f  mov     rcx, [rax]
0x18002f272  jmp     short loc_18002F277
0x18002f274  mov     rcx, r12; String1
0x18002f277  call    cs:__imp__wcsicmp
0x18002f27d  test    eax, eax
0x18002f27f  setnz   r14b
0x18002f283  mov     rcx, rbx; lpCriticalSection
0x18002f286  call    cs:__imp_LeaveCriticalSection
0x18002f28c  test    r14b, r14b
0x18002f28f  jnz     loc_18002F33D
0x18002f295  jmp     loc_18002F17B
0x18002f29a  mov     rbx, r12
0x18002f29d  lea     rcx, [rbp+arg_18]; this
0x18002f2a1  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18002f2a6  mov     r8d, 1; int
0x18002f2ac  lea     rdx, aIsprincipalall; "IsPrincipalAllowed"
0x18002f2b3  lea     rcx, [rbp+arg_8]; this
0x18002f2b7  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x18002f2bc  xor     edx, edx; lpDatabaseName
0x18002f2be  xor     ecx, ecx; lpMachineName
0x18002f2c0  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002f2c4  call    cs:__imp_OpenSCManagerW
0x18002f2ca  mov     rsi, rax
0x18002f2cd  test    rax, rax
0x18002f2d0  jz      short loc_18002F2F5
0x18002f2d2  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002f2d8  mov     rdx, rbx; lpServiceName
0x18002f2db  mov     rcx, rax; hSCManager
0x18002f2de  call    cs:__imp_OpenServiceW
0x18002f2e4  mov     rbx, rax
0x18002f2e7  mov     rcx, rsi; hSCObject
0x18002f2ea  call    cs:__imp_CloseServiceHandle
0x18002f2f0  test    rbx, rbx
0x18002f2f3  jnz     short loc_18002F328
0x18002f2f5  cmp     [rbp+arg_8], r12d
0x18002f2f9  jz      short loc_18002F302
0x18002f2fb  call    cs:__imp_RpcRevertToSelf
0x18002f301  nop
0x18002f302  lea     rcx, [rbp+arg_10]
0x18002f306  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002f30b  nop
0x18002f30c  mov     rcx, rdi
0x18002f30f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002f314  mov     eax, 80070005h
0x18002f319  add     rsp, 70h
0x18002f31d  pop     r15
0x18002f31f  pop     r14
0x18002f321  pop     r12
0x18002f323  pop     rdi
0x18002f324  pop     rsi
0x18002f325  pop     rbx
0x18002f326  pop     rbp
0x18002f327  retn
0x18002f328  mov     rcx, rbx; hSCObject
0x18002f32b  call    cs:__imp_CloseServiceHandle
0x18002f331  cmp     [rbp+arg_8], r12d
0x18002f335  jz      short loc_18002F33D
0x18002f337  call    cs:__imp_RpcRevertToSelf
0x18002f33d  mov     ebx, r12d
0x18002f340  lea     rcx, [rbp+arg_10]
0x18002f344  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002f349  nop
0x18002f34a  mov     rcx, rdi
0x18002f34d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18002f352  mov     eax, ebx
0x18002f354  jmp     short loc_18002F319
```
