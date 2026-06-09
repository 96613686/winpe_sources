# CClassData::DuplicateAndAdjustInteractiveUserTokenILIfNecessary(CToken *,void *,void * *)

- ea: `0x18000c454`
- end: `0x18000c6f3`
- name: `?DuplicateAndAdjustInteractiveUserTokenILIfNecessary@CClassData@@CAJPEAVCToken@@PEAXPEAPEAX@Z`
- size: `671`
- prototype: `__int64 __fastcall(struct CToken *this, HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e578`

## callees

- `0x18000b100`
- `0x18000c454`
- `0x18000c6fc`
- `0x18000c728`
- `0x18000ce5c`
- `0x1800210f8`
- `0x180024590`
- `0x18002fcb0`
- `0x180093f20`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x18000c57b`
- `ntdll!NtDuplicateToken` at `0x18000c57b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c6b2`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000c5b9`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000c5b9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000c540`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000c540`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c507`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c51f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c507`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000c51f`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000c59d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18000c59d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c58f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c687`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c58f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c687`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c487`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c487`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000c5e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000c62f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000c5e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000c62f`

## string_xrefs

- `0x18000c5f9`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c657`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c671`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c69c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000c6c7`: `onecore\com\combase\rpcss\olescm\launch.cxx`

## pseudocode

```c
__int64 __fastcall CClassData::DuplicateAndAdjustInteractiveUserTokenILIfNecessary(
        struct CToken *this,
        HANDLE TokenHandle,
        void **a3)
{
  int TokenIntegrityLevel; // eax
  enum _TOKEN_INFORMATION_CLASS v7; // edx
  unsigned int LastError; // ebx
  PDWORD SidSubAuthority; // rax
  void *v10; // r14
  const char *v11; // r9
  NTSTATUS v12; // eax
  DWORD SidLengthRequired; // eax
  const char *v14; // r9
  HLOCAL v15; // rcx
  HLOCAL v17; // rcx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-30h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-30h]
  struct _TOKEN_MANDATORY_LABEL *v20; // [rsp+38h] [rbp-18h] BYREF
  char v21; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HLOCAL hMem; // [rsp+70h] [rbp+20h] BYREF
  void *TokenInformation; // [rsp+80h] [rbp+30h] BYREF

  *a3 = 0;
  if ( EqualSid((char *)this + 156, gSidAnonymous) )
    return 0;
  TokenInformation = 0;
  TokenIntegrityLevel = CToken::GetTokenIntegrityLevel(this, (struct _TOKEN_MANDATORY_LABEL **)&TokenInformation);
  LastError = TokenIntegrityLevel;
  if ( TokenIntegrityLevel < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88A,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)(unsigned int)TokenIntegrityLevel,
      TokenType);
    return LastError;
  }
  hMem = 0;
  v20 = 0;
  v21 = 1;
  LastError = GetTokenIntegrityLevel(TokenHandle, v7, &v20);
  if ( v21 )
    wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &hMem,
      v20);
  if ( (LastError & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88D,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
      (const char *)LastError,
      TokenType);
LABEL_17:
    v17 = hMem;
    hMem = 0;
    if ( v17 )
      LocalFree(v17);
    return LastError;
  }
  SidSubAuthority = GetSidSubAuthority(*(PSID *)hMem, 0);
  v10 = TokenInformation;
  if ( *GetSidSubAuthority(*(PSID *)TokenInformation, 0) >= *SidSubAuthority )
    goto LABEL_11;
  TokenInformation = 0;
  if ( !ImpersonateLoggedOnUser(TokenHandle) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x8A0,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                  v11);
    goto LABEL_15;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenInformation,
    0);
  v12 = NtDuplicateToken(TokenHandle, 0, 0, 0, TokenPrimary, &TokenInformation);
  if ( v12 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x8A9,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                  (const char *)(unsigned int)v12,
                  TokenTypea);
    RevertToSelf();
LABEL_15:
    if ( (char *)TokenInformation - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenInformation);
    goto LABEL_17;
  }
  RevertToSelf();
  SidLengthRequired = GetSidLengthRequired(1u);
  if ( SetTokenInformation(TokenInformation, TokenIntegrityLevel, v10, SidLengthRequired + 16) )
  {
    *a3 = TokenInformation;
LABEL_11:
    v15 = hMem;
    hMem = 0;
    if ( v15 )
      LocalFree(v15);
    return 0;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x8AF,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                v14);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenInformation);
  wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
    &hMem,
    0);
  return LastError;
}

```

## disassembly

```asm
0x18000c454  mov     [rsp-18h+arg_8], rbx
0x18000c459  mov     [rsp-18h+arg_18], rsi
0x18000c45e  push    rbp
0x18000c45f  push    rdi
0x18000c460  push    r14
0x18000c462  mov     rbp, rsp
0x18000c465  sub     rsp, 50h
0x18000c469  mov     rdi, rdx
0x18000c46c  mov     qword ptr [r8], 0
0x18000c473  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18000c47a  mov     rbx, rcx
0x18000c47d  add     rcx, 9Ch; pSid1
0x18000c484  mov     rsi, r8
0x18000c487  call    cs:__imp_EqualSid
0x18000c48e  nop     dword ptr [rax+rax+00h]
0x18000c493  test    eax, eax
0x18000c495  jnz     loc_18000C5F1
0x18000c49b  lea     rdx, [rbp+TokenInformation]; struct _TOKEN_MANDATORY_LABEL **
0x18000c49f  mov     [rbp+TokenInformation], 0
0x18000c4a7  mov     rcx, rbx; this
0x18000c4aa  call    ?GetTokenIntegrityLevel@CToken@@UEAAJPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; CToken::GetTokenIntegrityLevel(_TOKEN_MANDATORY_LABEL * *)
0x18000c4af  mov     ebx, eax
0x18000c4b1  test    eax, eax
0x18000c4b3  js      loc_18000C698
0x18000c4b9  lea     rax, [rbp+hMem]
0x18000c4bd  mov     [rbp+hMem], 0
0x18000c4c5  lea     r8, [rbp+var_18]; struct _TOKEN_MANDATORY_LABEL **
0x18000c4c9  mov     [rbp+var_20], rax
0x18000c4cd  mov     rcx, rdi; TokenHandle
0x18000c4d0  mov     [rbp+var_18], 0
0x18000c4d8  mov     [rbp+var_10], 1
0x18000c4dc  call    ?GetTokenIntegrityLevel@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; GetTokenIntegrityLevel(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)
0x18000c4e1  cmp     [rbp+var_10], 0
0x18000c4e5  mov     ebx, eax
0x18000c4e7  jz      short loc_18000C4F6
0x18000c4e9  mov     rdx, [rbp+var_18]
0x18000c4ed  mov     rcx, [rbp+var_20]
0x18000c4f1  call    ?reset@?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_PROC_THREAD_ATTRIBUTE_LIST *)
0x18000c4f6  test    ebx, ebx
0x18000c4f8  js      loc_18000C653
0x18000c4fe  mov     rcx, [rbp+hMem]
0x18000c502  xor     edx, edx; nSubAuthority
0x18000c504  mov     rcx, [rcx]; pSid
0x18000c507  call    cs:__imp_GetSidSubAuthority
0x18000c50e  nop     dword ptr [rax+rax+00h]
0x18000c513  mov     r14, [rbp+TokenInformation]
0x18000c517  xor     edx, edx; nSubAuthority
0x18000c519  mov     rbx, rax
0x18000c51c  mov     rcx, [r14]; pSid
0x18000c51f  call    cs:__imp_GetSidSubAuthority
0x18000c526  nop     dword ptr [rax+rax+00h]
0x18000c52b  mov     ecx, [rbx]
0x18000c52d  cmp     [rax], ecx
0x18000c52f  jnb     loc_18000C5D4
0x18000c535  mov     rcx, rdi; hToken
0x18000c538  mov     [rbp+TokenInformation], 0
0x18000c540  call    cs:__imp_ImpersonateLoggedOnUser
0x18000c547  nop     dword ptr [rax+rax+00h]
0x18000c54c  test    eax, eax
0x18000c54e  jz      loc_18000C5F5
0x18000c554  xor     edx, edx
0x18000c556  lea     rcx, [rbp+TokenInformation]
0x18000c55a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000c55f  lea     rax, [rbp+TokenInformation]
0x18000c563  xor     r9d, r9d; EffectiveOnly
0x18000c566  mov     [rsp+50h+NewTokenHandle], rax; NewTokenHandle
0x18000c56b  xor     r8d, r8d; ObjectAttributes
0x18000c56e  xor     edx, edx; DesiredAccess
0x18000c570  mov     [rsp+50h+TokenType], 1; int
0x18000c578  mov     rcx, rdi; ExistingTokenHandle
0x18000c57b  call    cs:__imp_NtDuplicateToken
0x18000c582  nop     dword ptr [rax+rax+00h]
0x18000c587  test    eax, eax
0x18000c589  js      loc_18000C66D
0x18000c58f  call    cs:__imp_RevertToSelf
0x18000c596  nop     dword ptr [rax+rax+00h]
0x18000c59b  mov     cl, 1; nSubAuthorityCount
0x18000c59d  call    cs:__imp_GetSidLengthRequired
0x18000c5a4  nop     dword ptr [rax+rax+00h]
0x18000c5a9  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x18000c5ad  mov     r8, r14; TokenInformation
0x18000c5b0  mov     edx, 19h; TokenInformationClass
0x18000c5b5  lea     r9d, [rax+10h]; TokenInformationLength
0x18000c5b9  call    cs:__imp_SetTokenInformation
0x18000c5c0  nop     dword ptr [rax+rax+00h]
0x18000c5c5  test    eax, eax
0x18000c5c7  jz      loc_18000C6C3
0x18000c5cd  mov     rax, [rbp+TokenInformation]
0x18000c5d1  mov     [rsi], rax
0x18000c5d4  mov     rcx, [rbp+hMem]; hMem
0x18000c5d8  mov     [rbp+hMem], 0
0x18000c5e0  test    rcx, rcx
0x18000c5e3  jz      short loc_18000C5F1
0x18000c5e5  call    cs:__imp_LocalFree
0x18000c5ec  nop     dword ptr [rax+rax+00h]
0x18000c5f1  xor     eax, eax
0x18000c5f3  jmp     short loc_18000C63D
0x18000c5f5  mov     rcx, [rbp+18h]; this
0x18000c5f9  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000c600  mov     edx, 8A0h; void *
0x18000c605  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c60a  mov     ebx, eax
0x18000c60c  mov     rcx, [rbp+TokenInformation]; hObject
0x18000c610  lea     rdx, [rcx-1]
0x18000c614  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000c618  jbe     loc_18000C6B2
0x18000c61e  mov     rcx, [rbp+hMem]; hMem
0x18000c622  mov     [rbp+hMem], 0
0x18000c62a  test    rcx, rcx
0x18000c62d  jz      short loc_18000C63B
0x18000c62f  call    cs:__imp_LocalFree
0x18000c636  nop     dword ptr [rax+rax+00h]
0x18000c63b  mov     eax, ebx
0x18000c63d  lea     r11, [rsp+50h+var_s0]
0x18000c642  mov     rbx, [r11+28h]
0x18000c646  mov     rsi, [r11+38h]
0x18000c64a  mov     rsp, r11
0x18000c64d  pop     r14
0x18000c64f  pop     rdi
0x18000c650  pop     rbp
0x18000c651  retn
0x18000c653  mov     rcx, [rbp+18h]; this
0x18000c657  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000c65e  mov     r9d, ebx; char *
0x18000c661  mov     edx, 88Dh; void *
0x18000c666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c66b  jmp     short loc_18000C61E
0x18000c66d  mov     rcx, [rbp+18h]; this
0x18000c671  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000c678  mov     r9d, eax; char *
0x18000c67b  mov     edx, 8A9h; void *
0x18000c680  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000c685  mov     ebx, eax
0x18000c687  call    cs:__imp_RevertToSelf
0x18000c68e  nop     dword ptr [rax+rax+00h]
0x18000c693  jmp     loc_18000C60C
0x18000c698  mov     rcx, [rbp+18h]; this
0x18000c69c  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000c6a3  mov     r9d, ebx; char *
0x18000c6a6  mov     edx, 88Ah; void *
0x18000c6ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6b0  jmp     short loc_18000C63B
0x18000c6b2  call    cs:__imp_CloseHandle
0x18000c6b9  nop     dword ptr [rax+rax+00h]
0x18000c6be  jmp     loc_18000C61E
0x18000c6c3  mov     rcx, [rbp+18h]; this
0x18000c6c7  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18000c6ce  mov     edx, 8AFh; void *
0x18000c6d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c6d8  lea     rcx, [rbp+TokenInformation]
0x18000c6dc  mov     ebx, eax
0x18000c6de  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000c6e3  xor     edx, edx
0x18000c6e5  lea     rcx, [rbp+hMem]
0x18000c6e9  call    ?reset@?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_PROC_THREAD_ATTRIBUTE_LIST@@@Z; wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_PROC_THREAD_ATTRIBUTE_LIST *)
0x18000c6ee  jmp     loc_18000C63B
```
