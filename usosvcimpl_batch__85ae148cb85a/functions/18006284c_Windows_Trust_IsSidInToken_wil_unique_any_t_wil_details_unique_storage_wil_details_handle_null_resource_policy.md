# Windows::Trust::IsSidInToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &)

- ea: `0x18006284c`
- end: `0x1800629d3`
- name: `?IsSidInToken@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z`
- size: `391`
- prototype: `bool __fastcall(HANDLE *, PSID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800629dc`
- `0x180062a4c`

## callees

- `0x180010f24`
- `0x18006284c`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062936`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180062913`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180062951`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180062913`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180062951`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800628ef`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800628ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800628ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800628ae`

## string_xrefs

- `0x180062982`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x180062994`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x1800629a9`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x1800629be`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
bool __fastcall Windows::Trust::IsSidInToken(HANDLE *a1, PSID *a2)
{
  HANDLE v4; // rcx
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  bool v8; // bl
  const char *v10; // r9
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+34h] [rbp-1Ch] BYREF
  WINBOOL v13; // [rsp+38h] [rbp-18h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-14h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v4 = *a1;
  if ( !v4 || v4 == (HANDLE)-1LL )
    goto LABEL_10;
  ReturnLength = 0;
  TokenInformation = 1;
  if ( !GetTokenInformation(v4, TokenType, &TokenInformation, 4u, &ReturnLength) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x107,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
      v5);
  if ( TokenInformation == 2 )
  {
LABEL_10:
    v13 = 0;
    if ( !CheckTokenMembership(*a1, *a2, &v13) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x116,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
        v10);
    return v13 != 0;
  }
  else
  {
    TokenHandle = 0;
    if ( !DuplicateTokenEx(*a1, 8u, 0, SecurityIdentification, TokenImpersonation, &TokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x10C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
        v6);
    IsMember = 0;
    if ( !CheckTokenMembership(TokenHandle, *a2, &IsMember) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x10F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
        v7);
    v8 = IsMember != 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v8;
  }
}

```

## disassembly

```asm
0x18006284c  mov     [rsp-18h+arg_10], rbx
0x180062851  push    rbp
0x180062852  push    rsi
0x180062853  push    rdi
0x180062854  mov     rbp, rsp
0x180062857  sub     rsp, 50h
0x18006285b  mov     rax, cs:__security_cookie
0x180062862  xor     rax, rsp
0x180062865  mov     [rbp+var_8], rax
0x180062869  mov     rdi, rdx
0x18006286c  mov     rbx, rcx
0x18006286f  mov     rcx, [rcx]; TokenHandle
0x180062872  test    rcx, rcx
0x180062875  jz      loc_180062940
0x18006287b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006287f  jz      loc_180062940
0x180062885  mov     [rbp+var_14], 0
0x18006288c  mov     [rbp+TokenInformation], 1
0x180062893  mov     rsi, [rbp+18h]
0x180062897  lea     rax, [rbp+var_14]
0x18006289b  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800628a0  mov     r9d, 4; TokenInformationLength
0x1800628a6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800628aa  lea     edx, [r9+4]; TokenInformationClass
0x1800628ae  call    cs:__imp_GetTokenInformation
0x1800628b4  test    eax, eax
0x1800628b6  jz      loc_180062994
0x1800628bc  cmp     [rbp+TokenInformation], 2
0x1800628c0  jz      short loc_180062940
0x1800628c2  mov     [rbp+TokenHandle], 0
0x1800628ca  mov     rsi, [rbp+18h]
0x1800628ce  lea     rax, [rbp+TokenHandle]
0x1800628d2  mov     [rsp+50h+phNewToken], rax; phNewToken
0x1800628d7  mov     dword ptr [rsp+50h+ReturnLength], 2; TokenType
0x1800628df  mov     r9d, 1; ImpersonationLevel
0x1800628e5  xor     r8d, r8d; lpTokenAttributes
0x1800628e8  lea     edx, [r9+7]; dwDesiredAccess
0x1800628ec  mov     rcx, [rbx]; hExistingToken
0x1800628ef  call    cs:__imp_DuplicateTokenEx
0x1800628f5  test    eax, eax
0x1800628f7  jz      loc_1800629A9
0x1800628fd  mov     [rbp+IsMember], 0
0x180062904  mov     rbx, [rbp+18h]
0x180062908  lea     r8, [rbp+IsMember]; IsMember
0x18006290c  mov     rdx, [rdi]; SidToCheck
0x18006290f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180062913  call    cs:__imp_CheckTokenMembership
0x180062919  test    eax, eax
0x18006291b  jz      loc_1800629BE
0x180062921  cmp     [rbp+IsMember], 0
0x180062925  setnz   bl
0x180062928  mov     rcx, [rbp+TokenHandle]; hObject
0x18006292c  lea     rdx, [rcx-1]
0x180062930  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180062934  ja      short loc_18006293C
0x180062936  call    cs:__imp_CloseHandle
0x18006293c  mov     al, bl
0x18006293e  jmp     short loc_180062962
0x180062940  mov     [rbp+var_18], 0
0x180062947  lea     r8, [rbp+var_18]; IsMember
0x18006294b  mov     rdx, [rdi]; SidToCheck
0x18006294e  mov     rcx, [rbx]; TokenHandle
0x180062951  call    cs:__imp_CheckTokenMembership
0x180062957  test    eax, eax
0x180062959  jz      short loc_18006297E
0x18006295b  cmp     [rbp+var_18], 0
0x18006295f  setnz   al
0x180062962  mov     rcx, [rbp+var_8]
0x180062966  xor     rcx, rsp; StackCookie
0x180062969  call    __security_check_cookie
0x18006296e  mov     rbx, [rsp+50h+arg_10]
0x180062976  add     rsp, 50h
0x18006297a  pop     rdi
0x18006297b  pop     rsi
0x18006297c  pop     rbp
0x18006297d  retn
0x18006297e  mov     rcx, [rbp+18h]; this
0x180062982  lea     r8, aCW1SSrcOrchest_43; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180062989  mov     edx, 116h; void *
0x18006298e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180062994  lea     r8, aCW1SSrcOrchest_43; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006299b  mov     edx, 107h; void *
0x1800629a0  mov     rcx, rsi; this
0x1800629a3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800629a9  lea     r8, aCW1SSrcOrchest_43; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800629b0  mov     edx, 10Ch; void *
0x1800629b5  mov     rcx, rsi; this
0x1800629b8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800629be  lea     r8, aCW1SSrcOrchest_43; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800629c5  mov     edx, 10Fh; void *
0x1800629ca  mov     rcx, rbx; this
0x1800629cd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
