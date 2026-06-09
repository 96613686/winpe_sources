# CClassData::DuplicateAndAdjustInteractiveUserTokenILIfNecessary(CToken *,void *,void * *)

- ea: `0x18005c14c`
- end: `0x18005c3b4`
- name: `?DuplicateAndAdjustInteractiveUserTokenILIfNecessary@CClassData@@CAJPEAVCToken@@PEAXPEAPEAX@Z`
- size: `616`
- prototype: `__int64 __fastcall(struct CToken *this, HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004cd64`

## callees

- `0x18001ec28`
- `0x180025910`
- `0x18002ba28`
- `0x18002ed28`
- `0x18005c14c`
- `0x18005c3bc`
- `0x18008cd90`

## import_xrefs

- `ntdll!NtDuplicateToken` at `0x18005c265`
- `ntdll!NtDuplicateToken` at `0x18005c265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c35f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005c35f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c34c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c34c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c344`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c344`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c357`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18005c291`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18005c291`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005c225`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005c225`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005c1fc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005c20e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005c1fc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18005c20e`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005c27b`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x18005c27b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c273`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c384`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c273`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005c384`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005c182`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18005c182`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c1e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c2b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c2ef`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c1e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c2b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18005c2ef`

## string_xrefs

- `0x18005c2c1`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005c314`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005c32e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005c36e`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18005c393`: `onecore\com\combase\rpcss\olescm\launch.cxx`

## pseudocode

```c
__int64 __fastcall CClassData::DuplicateAndAdjustInteractiveUserTokenILIfNecessary(
        struct CToken *this,
        HANDLE TokenHandle,
        void **a3)
{
  int TokenIntegrityLevel; // eax
  enum _TOKEN_INFORMATION_CLASS v7; // edx
  unsigned int v8; // ebx
  PDWORD SidSubAuthority; // rax
  void *v10; // r15
  const char *v11; // r9
  void *v12; // rdi
  NTSTATUS v13; // eax
  DWORD SidLengthRequired; // eax
  const char *v15; // r9
  DWORD LastError; // ebx
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-30h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-30h]
  struct _TOKEN_MANDATORY_LABEL *v20; // [rsp+38h] [rbp-18h] BYREF
  char v21; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct _TOKEN_MANDATORY_LABEL *hMem; // [rsp+80h] [rbp+30h]
  void *TokenInformation; // [rsp+90h] [rbp+40h] BYREF

  *a3 = 0;
  if ( EqualSid((char *)this + 156, gSidAnonymous) )
    return 0;
  TokenInformation = 0;
  TokenIntegrityLevel = CToken::GetTokenIntegrityLevel(this, (struct _TOKEN_MANDATORY_LABEL **)&TokenInformation);
  v8 = TokenIntegrityLevel;
  if ( TokenIntegrityLevel >= 0 )
  {
    hMem = 0;
    v20 = 0;
    v21 = 1;
    v8 = GetTokenIntegrityLevel(TokenHandle, v7, &v20);
    if ( v21 )
      hMem = v20;
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88D,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
        (const char *)v8,
        TokenType);
    }
    else
    {
      SidSubAuthority = GetSidSubAuthority(hMem->Label.Sid, 0);
      v10 = TokenInformation;
      if ( *GetSidSubAuthority(*(PSID *)TokenInformation, 0) >= *SidSubAuthority )
        goto LABEL_13;
      TokenInformation = 0;
      if ( ImpersonateLoggedOnUser(TokenHandle) )
      {
        v12 = TokenInformation;
        if ( (char *)TokenInformation - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          LastError = GetLastError();
          CloseHandle(v12);
          SetLastError(LastError);
        }
        TokenInformation = 0;
        v13 = NtDuplicateToken(TokenHandle, 0, 0, 0, TokenPrimary, &TokenInformation);
        if ( v13 >= 0 )
        {
          RevertToSelf();
          SidLengthRequired = GetSidLengthRequired(1u);
          if ( SetTokenInformation(TokenInformation, TokenIntegrityLevel, v10, SidLengthRequired + 16) )
          {
            *a3 = TokenInformation;
LABEL_13:
            if ( hMem )
              LocalFree(hMem);
            return 0;
          }
          v8 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x8AF,
                 (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
                 v15);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenInformation);
          goto LABEL_19;
        }
        v8 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x8A9,
               (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
               (const char *)(unsigned int)v13,
               TokenTypea);
        RevertToSelf();
      }
      else
      {
        v8 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x8A0,
               (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
               v11);
      }
      if ( (char *)TokenInformation - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenInformation);
    }
LABEL_19:
    if ( hMem )
      LocalFree(hMem);
    return v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x88A,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\launch.cxx",
    (const char *)(unsigned int)TokenIntegrityLevel,
    TokenType);
  return v8;
}

```

## disassembly

```asm
0x18005c14c  mov     [rsp-28h+arg_8], rbx
0x18005c151  mov     [rsp-28h+arg_18], rsi
0x18005c156  push    rbp
0x18005c157  push    rdi
0x18005c158  push    r12
0x18005c15a  push    r14
0x18005c15c  push    r15
0x18005c15e  mov     rbp, rsp
0x18005c161  sub     rsp, 50h
0x18005c165  mov     rsi, rdx
0x18005c168  mov     rbx, rcx
0x18005c16b  xor     r12d, r12d
0x18005c16e  add     rcx, 9Ch; pSid1
0x18005c175  mov     [r8], r12
0x18005c178  mov     r14, r8
0x18005c17b  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18005c182  call    cs:__imp_EqualSid
0x18005c188  test    eax, eax
0x18005c18a  jnz     loc_18005C2B9
0x18005c190  lea     rdx, [rbp+TokenInformation]; struct _TOKEN_MANDATORY_LABEL **
0x18005c194  mov     [rbp+TokenInformation], r12
0x18005c198  mov     rcx, rbx; this
0x18005c19b  call    ?GetTokenIntegrityLevel@CToken@@UEAAJPEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; CToken::GetTokenIntegrityLevel(_TOKEN_MANDATORY_LABEL * *)
0x18005c1a0  mov     ebx, eax
0x18005c1a2  test    eax, eax
0x18005c1a4  js      loc_18005C32A
0x18005c1aa  lea     rax, [rbp+hMem]
0x18005c1ae  mov     [rbp+hMem], r12
0x18005c1b2  lea     r8, [rbp+var_18]; struct _TOKEN_MANDATORY_LABEL **
0x18005c1b6  mov     [rbp+var_20], rax
0x18005c1ba  mov     rcx, rsi; TokenHandle
0x18005c1bd  mov     [rbp+var_18], r12
0x18005c1c1  mov     [rbp+var_10], 1
0x18005c1c5  call    ?GetTokenIntegrityLevel@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAU_TOKEN_MANDATORY_LABEL@@@Z; GetTokenIntegrityLevel(void *,_TOKEN_INFORMATION_CLASS,_TOKEN_MANDATORY_LABEL * *)
0x18005c1ca  mov     ebx, eax
0x18005c1cc  cmp     [rbp+var_10], r12b
0x18005c1d0  jz      short loc_18005C1EB
0x18005c1d2  mov     r8, [rbp+var_20]
0x18005c1d6  mov     rdx, [rbp+var_18]
0x18005c1da  mov     rcx, [r8]; hMem
0x18005c1dd  mov     [r8], rdx
0x18005c1e0  test    rcx, rcx
0x18005c1e3  jz      short loc_18005C1EB
0x18005c1e5  call    cs:__imp_LocalFree
0x18005c1eb  test    ebx, ebx
0x18005c1ed  js      loc_18005C310
0x18005c1f3  mov     rcx, [rbp+hMem]
0x18005c1f7  xor     edx, edx; nSubAuthority
0x18005c1f9  mov     rcx, [rcx]; pSid
0x18005c1fc  call    cs:__imp_GetSidSubAuthority
0x18005c202  mov     r15, [rbp+TokenInformation]
0x18005c206  xor     edx, edx; nSubAuthority
0x18005c208  mov     rbx, rax
0x18005c20b  mov     rcx, [r15]; pSid
0x18005c20e  call    cs:__imp_GetSidSubAuthority
0x18005c214  mov     ecx, [rbx]
0x18005c216  cmp     [rax], ecx
0x18005c218  jnb     loc_18005C2A6
0x18005c21e  mov     rcx, rsi; hToken
0x18005c221  mov     [rbp+TokenInformation], r12
0x18005c225  call    cs:__imp_ImpersonateLoggedOnUser
0x18005c22b  test    eax, eax
0x18005c22d  jz      loc_18005C2BD
0x18005c233  mov     rdi, [rbp+TokenInformation]
0x18005c237  lea     rax, [rdi-1]
0x18005c23b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005c23f  jbe     loc_18005C34C
0x18005c245  lea     rax, [rbp+TokenInformation]
0x18005c249  mov     [rbp+TokenInformation], r12
0x18005c24d  mov     [rsp+50h+NewTokenHandle], rax; NewTokenHandle
0x18005c252  xor     r9d, r9d; EffectiveOnly
0x18005c255  xor     r8d, r8d; ObjectAttributes
0x18005c258  mov     [rsp+50h+TokenType], 1; int
0x18005c260  xor     edx, edx; DesiredAccess
0x18005c262  mov     rcx, rsi; ExistingTokenHandle
0x18005c265  call    cs:__imp_NtDuplicateToken
0x18005c26b  test    eax, eax
0x18005c26d  js      loc_18005C36A
0x18005c273  call    cs:__imp_RevertToSelf
0x18005c279  mov     cl, 1; nSubAuthorityCount
0x18005c27b  call    cs:__imp_GetSidLengthRequired
0x18005c281  mov     rcx, [rbp+TokenInformation]; TokenHandle
0x18005c285  mov     r8, r15; TokenInformation
0x18005c288  mov     edx, 19h; TokenInformationClass
0x18005c28d  lea     r9d, [rax+10h]; TokenInformationLength
0x18005c291  call    cs:__imp_SetTokenInformation
0x18005c297  test    eax, eax
0x18005c299  jz      loc_18005C38F
0x18005c29f  mov     rax, [rbp+TokenInformation]
0x18005c2a3  mov     [r14], rax
0x18005c2a6  mov     rcx, [rbp+hMem]; hMem
0x18005c2aa  mov     [rbp+hMem], r12
0x18005c2ae  test    rcx, rcx
0x18005c2b1  jz      short loc_18005C2B9
0x18005c2b3  call    cs:__imp_LocalFree
0x18005c2b9  xor     eax, eax
0x18005c2bb  jmp     short loc_18005C2F7
0x18005c2bd  mov     rcx, [rbp+28h]; this
0x18005c2c1  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005c2c8  mov     edx, 8A0h; void *
0x18005c2cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c2d2  mov     ebx, eax
0x18005c2d4  mov     rcx, [rbp+TokenInformation]; hObject
0x18005c2d8  lea     rdx, [rcx-1]
0x18005c2dc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005c2e0  jbe     short loc_18005C344
0x18005c2e2  mov     rcx, [rbp+hMem]; hMem
0x18005c2e6  mov     [rbp+hMem], r12
0x18005c2ea  test    rcx, rcx
0x18005c2ed  jz      short loc_18005C2F5
0x18005c2ef  call    cs:__imp_LocalFree
0x18005c2f5  mov     eax, ebx
0x18005c2f7  lea     r11, [rsp+50h+var_s0]
0x18005c2fc  mov     rbx, [r11+38h]
0x18005c300  mov     rsi, [r11+48h]
0x18005c304  mov     rsp, r11
0x18005c307  pop     r15
0x18005c309  pop     r14
0x18005c30b  pop     r12
0x18005c30d  pop     rdi
0x18005c30e  pop     rbp
0x18005c30f  retn
0x18005c310  mov     rcx, [rbp+28h]; this
0x18005c314  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005c31b  mov     r9d, ebx; char *
0x18005c31e  mov     edx, 88Dh; void *
0x18005c323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c328  jmp     short loc_18005C2E2
0x18005c32a  mov     rcx, [rbp+28h]; this
0x18005c32e  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005c335  mov     r9d, ebx; char *
0x18005c338  mov     edx, 88Ah; void *
0x18005c33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c342  jmp     short loc_18005C2F5
0x18005c344  call    cs:__imp_CloseHandle
0x18005c34a  jmp     short loc_18005C2E2
0x18005c34c  call    cs:__imp_GetLastError
0x18005c352  mov     rcx, rdi; hObject
0x18005c355  mov     ebx, eax
0x18005c357  call    cs:__imp_CloseHandle
0x18005c35d  mov     ecx, ebx; dwErrCode
0x18005c35f  call    cs:__imp_SetLastError
0x18005c365  jmp     loc_18005C245
0x18005c36a  mov     rcx, [rbp+28h]; this
0x18005c36e  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005c375  mov     r9d, eax; char *
0x18005c378  mov     edx, 8A9h; void *
0x18005c37d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18005c382  mov     ebx, eax
0x18005c384  call    cs:__imp_RevertToSelf
0x18005c38a  jmp     loc_18005C2D4
0x18005c38f  mov     rcx, [rbp+28h]; this
0x18005c393  lea     r8, aOnecoreComComb_68; "onecore\\com\\combase\\rpcss\\olescm\\l"...
0x18005c39a  mov     edx, 8AFh; void *
0x18005c39f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c3a4  lea     rcx, [rbp+TokenInformation]
0x18005c3a8  mov     ebx, eax
0x18005c3aa  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005c3af  jmp     loc_18005C2E2
```
