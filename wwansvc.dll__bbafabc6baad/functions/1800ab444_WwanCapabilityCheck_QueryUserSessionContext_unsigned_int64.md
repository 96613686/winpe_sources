# WwanCapabilityCheck::QueryUserSessionContext(unsigned __int64 &)

- ea: `0x1800ab444`
- end: `0x1800ab754`
- name: `?QueryUserSessionContext@WwanCapabilityCheck@@SAKAEA_K@Z`
- size: `784`
- prototype: `unsigned int __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ad000`

## callees

- `0x180009990`
- `0x180019d70`
- `0x1800ab2b0`
- `0x1800ab444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab5cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab4c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab5cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab67c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab4e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab566`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab5e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab65e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab4e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab566`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab5e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab65e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab4b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab541`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab5c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab63d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab4b9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab541`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab5c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ab63d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab4f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab576`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab5f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab66e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab4f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab576`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab5f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab66e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab4a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab52e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab5b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab62a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab4a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab52e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab5b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ab62a`
- `RPCRT4!RpcImpersonateClient` at `0x1800ab482`
- `RPCRT4!RpcImpersonateClient` at `0x1800ab482`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800ab727`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800ab727`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab6d7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab6e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab703`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab712`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab6d7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab6e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab703`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800ab712`

## pseudocode

```c
__int64 __fastcall WwanCapabilityCheck::QueryUserSessionContext(unsigned __int64 *a1)
{
  char v1; // di
  unsigned int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  bool v8; // sf
  HANDLE v9; // rax
  signed int v10; // eax
  unsigned int v11; // ecx
  HANDLE v12; // rax
  signed int v13; // eax
  HANDLE v14; // rax
  signed int v15; // eax
  HANDLE v16; // rax
  HANDLE v17; // rax
  signed int v18; // eax
  HANDLE v19; // rax
  signed int v20; // eax
  __int64 *v22; // [rsp+20h] [rbp-60h] BYREF
  void *v23; // [rsp+28h] [rbp-58h] BYREF
  char v24; // [rsp+30h] [rbp-50h]
  __int64 *v25; // [rsp+38h] [rbp-48h] BYREF
  void *v26; // [rsp+40h] [rbp-40h] BYREF
  char v27; // [rsp+48h] [rbp-38h]
  __int64 *v28; // [rsp+50h] [rbp-30h] BYREF
  void *v29; // [rsp+58h] [rbp-28h] BYREF
  char v30; // [rsp+60h] [rbp-20h]
  __int64 *v31; // [rsp+68h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-10h] BYREF
  char v33; // [rsp+78h] [rbp-8h]
  __int64 v34; // [rsp+B0h] [rbp+30h] BYREF
  unsigned __int64 v35; // [rsp+B8h] [rbp+38h] BYREF

  v1 = 0;
  v34 = 0;
  *a1 = 0;
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
  {
    v3 = 50;
    goto LABEL_49;
  }
  v3 = RpcImpersonateClient(0);
  if ( v3 )
    goto LABEL_49;
  TokenHandle = 0;
  v31 = &v34;
  v33 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
    goto LABEL_44;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023888 )
    goto LABEL_11;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
  {
LABEL_44:
    v3 = 0;
    goto LABEL_38;
  }
  v7 = GetLastError();
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    LastError = (unsigned __int16)v7 | 0x80070000;
LABEL_11:
    v8 = LastError < 0;
  }
  if ( !v8 )
    goto LABEL_44;
  v29 = 0;
  v28 = &v34;
  v30 = 1;
  v9 = GetCurrentThread();
  if ( OpenThreadToken(v9, 0xCu, 0, &v29) )
    goto LABEL_29;
  v10 = GetLastError();
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 == -2147023888 )
  {
    v12 = GetCurrentProcess();
    if ( !OpenProcessToken(v12, 0xCu, &v29) )
    {
      v13 = GetLastError();
      v11 = -2147024896;
      if ( v13 <= 0 )
        v11 = v13;
      goto LABEL_20;
    }
LABEL_29:
    v23 = 0;
    v22 = &v34;
    v24 = 1;
    v17 = GetCurrentThread();
    if ( OpenThreadToken(v17, 0xCu, 0, &v23) )
      goto LABEL_34;
    v18 = GetLastError();
    v3 = v18;
    if ( v18 > 0 )
      v3 = (unsigned __int16)v18 | 0x80070000;
    if ( v3 != -2147023888 )
      goto LABEL_37;
    v19 = GetCurrentProcess();
    if ( OpenProcessToken(v19, 0xCu, &v23) )
    {
LABEL_34:
      v3 = 0;
    }
    else
    {
      v20 = GetLastError();
      v3 = v20;
      if ( v20 > 0 )
        v3 = (unsigned __int16)v20 | 0x80070000;
    }
LABEL_37:
    v1 = 5;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v22);
    goto LABEL_38;
  }
LABEL_20:
  if ( (v11 & 0x1FFF0000) != 0x70000 )
    goto LABEL_29;
  v26 = 0;
  v25 = &v34;
  v27 = 1;
  v14 = GetCurrentThread();
  if ( OpenThreadToken(v14, 0xCu, 0, &v26) )
    goto LABEL_26;
  v15 = GetLastError();
  if ( v15 > 0 )
    v15 = (unsigned __int16)v15 | 0x80070000;
  if ( v15 != -2147023888 )
    goto LABEL_28;
  v16 = GetCurrentProcess();
  if ( OpenProcessToken(v16, 0xCu, &v26) )
LABEL_26:
    LOWORD(v15) = 0;
  else
    LOWORD(v15) = GetLastError();
LABEL_28:
  v3 = (unsigned __int16)v15;
  v1 = 3;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v25);
LABEL_38:
  if ( (v1 & 1) != 0 )
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v28);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v31);
  if ( !v3 )
  {
    v35 = 0;
    if ( (int)UMgrQueryUserContext(v34, &v35) >= 0
      || ((UMgrQueryUserContext(v34, &v35) & 0x1FFF0000) != 0x70000
        ? (v3 = UMgrQueryUserContext(v34, &v35))
        : (v3 = (unsigned __int16)UMgrQueryUserContext(v34, &v35)),
          !v3) )
    {
      *a1 = v35;
    }
  }
  RpcRevertToSelfEx(0);
LABEL_49:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
  return v3;
}

```

## disassembly

```asm
0x1800ab444  mov     [rsp-28h+arg_10], rbx
0x1800ab449  mov     [rsp-28h+arg_18], rsi
0x1800ab44e  push    rbp
0x1800ab44f  push    rdi
0x1800ab450  push    r12
0x1800ab452  push    r13
0x1800ab454  push    r15
0x1800ab456  mov     rbp, rsp
0x1800ab459  sub     rsp, 80h
0x1800ab460  xor     edi, edi
0x1800ab462  mov     rsi, rcx
0x1800ab465  mov     dword ptr [rbp+arg_0], edi
0x1800ab468  mov     [rbp+arg_0], rdi
0x1800ab46c  mov     [rcx], rdi
0x1800ab46f  call    IsUMgrQueryUserContextPresent
0x1800ab474  test    al, al
0x1800ab476  jnz     short loc_1800AB480
0x1800ab478  lea     ebx, [rdi+32h]
0x1800ab47b  jmp     loc_1800AB72D
0x1800ab480  xor     ecx, ecx; BindingHandle
0x1800ab482  call    cs:__imp_RpcImpersonateClient
0x1800ab488  mov     ebx, eax
0x1800ab48a  test    eax, eax
0x1800ab48c  jnz     loc_1800AB72D
0x1800ab492  lea     rax, [rbp+arg_0]
0x1800ab496  mov     [rbp+TokenHandle], rdi
0x1800ab49a  mov     [rbp+var_18], rax
0x1800ab49e  mov     [rbp+var_8], 1
0x1800ab4a2  call    cs:__imp_GetCurrentThread
0x1800ab4a8  lea     r13d, [rbx+0Ch]
0x1800ab4ac  xor     r8d, r8d; OpenAsSelf
0x1800ab4af  mov     rcx, rax; ThreadHandle
0x1800ab4b2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ab4b6  mov     edx, r13d; DesiredAccess
0x1800ab4b9  call    cs:__imp_OpenThreadToken
0x1800ab4bf  test    eax, eax
0x1800ab4c1  jnz     loc_1800AB70E
0x1800ab4c7  call    cs:__imp_GetLastError
0x1800ab4cd  mov     r15d, 80070000h
0x1800ab4d3  test    eax, eax
0x1800ab4d5  jle     short loc_1800AB4DD
0x1800ab4d7  movzx   eax, ax
0x1800ab4da  or      eax, r15d
0x1800ab4dd  mov     r12d, 800703F0h
0x1800ab4e3  cmp     eax, r12d
0x1800ab4e6  jnz     short loc_1800AB516
0x1800ab4e8  call    cs:__imp_GetCurrentProcess
0x1800ab4ee  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800ab4f2  mov     edx, r13d; DesiredAccess
0x1800ab4f5  mov     rcx, rax; ProcessHandle
0x1800ab4f8  call    cs:__imp_OpenProcessToken
0x1800ab4fe  test    eax, eax
0x1800ab500  jnz     loc_1800AB70E
0x1800ab506  call    cs:__imp_GetLastError
0x1800ab50c  test    eax, eax
0x1800ab50e  jle     short loc_1800AB518
0x1800ab510  movzx   eax, ax
0x1800ab513  or      eax, r15d
0x1800ab516  test    eax, eax
0x1800ab518  jns     loc_1800AB70E
0x1800ab51e  lea     rax, [rbp+arg_0]
0x1800ab522  mov     [rbp+var_28], rdi
0x1800ab526  mov     [rbp+var_30], rax
0x1800ab52a  mov     [rbp+var_20], 1
0x1800ab52e  call    cs:__imp_GetCurrentThread
0x1800ab534  lea     r9, [rbp+var_28]; TokenHandle
0x1800ab538  xor     r8d, r8d; OpenAsSelf
0x1800ab53b  mov     rcx, rax; ThreadHandle
0x1800ab53e  mov     edx, r13d; DesiredAccess
0x1800ab541  call    cs:__imp_OpenThreadToken
0x1800ab547  test    eax, eax
0x1800ab549  jnz     loc_1800AB61A
0x1800ab54f  call    cs:__imp_GetLastError
0x1800ab555  mov     ecx, eax
0x1800ab557  test    eax, eax
0x1800ab559  jle     short loc_1800AB561
0x1800ab55b  movzx   ecx, ax
0x1800ab55e  or      ecx, r15d
0x1800ab561  cmp     ecx, r12d
0x1800ab564  jnz     short loc_1800AB592
0x1800ab566  call    cs:__imp_GetCurrentProcess
0x1800ab56c  lea     r8, [rbp+var_28]; TokenHandle
0x1800ab570  mov     edx, r13d; DesiredAccess
0x1800ab573  mov     rcx, rax; ProcessHandle
0x1800ab576  call    cs:__imp_OpenProcessToken
0x1800ab57c  test    eax, eax
0x1800ab57e  jnz     loc_1800AB61A
0x1800ab584  call    cs:__imp_GetLastError
0x1800ab58a  test    eax, eax
0x1800ab58c  mov     ecx, r15d
0x1800ab58f  cmovle  ecx, eax
0x1800ab592  and     ecx, 1FFF0000h
0x1800ab598  cmp     ecx, 70000h
0x1800ab59e  jnz     short loc_1800AB61A
0x1800ab5a0  lea     rax, [rbp+arg_0]
0x1800ab5a4  mov     [rbp+var_40], rdi
0x1800ab5a8  mov     [rbp+var_48], rax
0x1800ab5ac  mov     [rbp+var_38], 1
0x1800ab5b0  call    cs:__imp_GetCurrentThread
0x1800ab5b6  lea     r9, [rbp+var_40]; TokenHandle
0x1800ab5ba  xor     r8d, r8d; OpenAsSelf
0x1800ab5bd  mov     rcx, rax; ThreadHandle
0x1800ab5c0  mov     edx, r13d; DesiredAccess
0x1800ab5c3  call    cs:__imp_OpenThreadToken
0x1800ab5c9  test    eax, eax
0x1800ab5cb  jnz     short loc_1800AB5FC
0x1800ab5cd  call    cs:__imp_GetLastError
0x1800ab5d3  test    eax, eax
0x1800ab5d5  jle     short loc_1800AB5DD
0x1800ab5d7  movzx   eax, ax
0x1800ab5da  or      eax, r15d
0x1800ab5dd  cmp     eax, r12d
0x1800ab5e0  jnz     short loc_1800AB60D
0x1800ab5e2  call    cs:__imp_GetCurrentProcess
0x1800ab5e8  lea     r8, [rbp+var_40]; TokenHandle
0x1800ab5ec  mov     edx, r13d; DesiredAccess
0x1800ab5ef  mov     rcx, rax; ProcessHandle
0x1800ab5f2  call    cs:__imp_OpenProcessToken
0x1800ab5f8  test    eax, eax
0x1800ab5fa  jz      short loc_1800AB600
0x1800ab5fc  xor     eax, eax
0x1800ab5fe  jmp     short loc_1800AB60D
0x1800ab600  call    cs:__imp_GetLastError
0x1800ab606  test    eax, eax
0x1800ab608  jle     short loc_1800AB60D
0x1800ab60a  movzx   eax, ax
0x1800ab60d  movzx   ebx, ax
0x1800ab610  mov     edi, 3
0x1800ab615  jmp     loc_1800AB6A2
0x1800ab61a  lea     rax, [rbp+arg_0]
0x1800ab61e  mov     [rbp+var_58], rdi
0x1800ab622  mov     [rbp+var_60], rax
0x1800ab626  mov     [rbp+var_50], 1
0x1800ab62a  call    cs:__imp_GetCurrentThread
0x1800ab630  lea     r9, [rbp+var_58]; TokenHandle
0x1800ab634  xor     r8d, r8d; OpenAsSelf
0x1800ab637  mov     rcx, rax; ThreadHandle
0x1800ab63a  mov     edx, r13d; DesiredAccess
0x1800ab63d  call    cs:__imp_OpenThreadToken
0x1800ab643  test    eax, eax
0x1800ab645  jnz     short loc_1800AB678
0x1800ab647  call    cs:__imp_GetLastError
0x1800ab64d  mov     ebx, eax
0x1800ab64f  test    eax, eax
0x1800ab651  jle     short loc_1800AB659
0x1800ab653  movzx   ebx, ax
0x1800ab656  or      ebx, r15d
0x1800ab659  cmp     ebx, r12d
0x1800ab65c  jnz     short loc_1800AB68E
0x1800ab65e  call    cs:__imp_GetCurrentProcess
0x1800ab664  lea     r8, [rbp+var_58]; TokenHandle
0x1800ab668  mov     edx, r13d; DesiredAccess
0x1800ab66b  mov     rcx, rax; ProcessHandle
0x1800ab66e  call    cs:__imp_OpenProcessToken
0x1800ab674  test    eax, eax
0x1800ab676  jz      short loc_1800AB67C
0x1800ab678  xor     ebx, ebx
0x1800ab67a  jmp     short loc_1800AB68E
0x1800ab67c  call    cs:__imp_GetLastError
0x1800ab682  mov     ebx, eax
0x1800ab684  test    eax, eax
0x1800ab686  jle     short loc_1800AB68E
0x1800ab688  movzx   ebx, ax
0x1800ab68b  or      ebx, r15d
0x1800ab68e  lea     rcx, [rbp+var_60]
0x1800ab692  mov     edi, 5
0x1800ab697  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ab69c  test    dil, 2
0x1800ab6a0  jz      short loc_1800AB6AB
0x1800ab6a2  lea     rcx, [rbp+var_48]
0x1800ab6a6  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ab6ab  test    dil, 1
0x1800ab6af  jz      short loc_1800AB6BA
0x1800ab6b1  lea     rcx, [rbp+var_30]
0x1800ab6b5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ab6ba  lea     rcx, [rbp+var_18]
0x1800ab6be  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800ab6c3  test    ebx, ebx
0x1800ab6c5  jnz     short loc_1800AB725
0x1800ab6c7  mov     rcx, [rbp+arg_0]
0x1800ab6cb  lea     rdx, [rbp+arg_8]
0x1800ab6cf  mov     [rbp+arg_8], 0
0x1800ab6d7  call    cs:__imp_UMgrQueryUserContext
0x1800ab6dd  test    eax, eax
0x1800ab6df  jns     short loc_1800AB71E
0x1800ab6e1  mov     rcx, [rbp+arg_0]
0x1800ab6e5  lea     rdx, [rbp+arg_8]
0x1800ab6e9  call    cs:__imp_UMgrQueryUserContext
0x1800ab6ef  mov     rcx, [rbp+arg_0]
0x1800ab6f3  lea     rdx, [rbp+arg_8]
0x1800ab6f7  and     eax, 1FFF0000h
0x1800ab6fc  cmp     eax, 70000h
0x1800ab701  jnz     short loc_1800AB712
0x1800ab703  call    cs:__imp_UMgrQueryUserContext
0x1800ab709  movzx   ebx, ax
0x1800ab70c  jmp     short loc_1800AB71A
0x1800ab70e  xor     ebx, ebx
0x1800ab710  jmp     short loc_1800AB69C
0x1800ab712  call    cs:__imp_UMgrQueryUserContext
0x1800ab718  mov     ebx, eax
0x1800ab71a  test    ebx, ebx
0x1800ab71c  jnz     short loc_1800AB725
0x1800ab71e  mov     rax, [rbp+arg_8]
0x1800ab722  mov     [rsi], rax
0x1800ab725  xor     ecx, ecx; BindingHandle
0x1800ab727  call    cs:__imp_RpcRevertToSelfEx
0x1800ab72d  lea     rcx, [rbp+arg_0]
0x1800ab731  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ab736  lea     r11, [rsp+80h+var_s0]
0x1800ab73e  mov     eax, ebx
0x1800ab740  mov     rbx, [r11+40h]
0x1800ab744  mov     rsi, [r11+48h]
0x1800ab748  mov     rsp, r11
0x1800ab74b  pop     r15
0x1800ab74d  pop     r13
0x1800ab74f  pop     r12
0x1800ab751  pop     rdi
0x1800ab752  pop     rbp
0x1800ab753  retn
```
