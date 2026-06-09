# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1400b9ce8`
- end: `0x1400b9e2e`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400b9c90`

## callees

- `0x1400a6578`
- `0x1400a65a0`
- `0x1400b9ce8`
- `0x1401332f0`
- `0x140133358`
- `0x140133d60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400b9d38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400b9db9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400b9d38`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400b9db9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b9d4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b9d4c`

## string_xrefs

- `0x1400b9d7e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400b9dce`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1400b9e04`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1)
{
  void *v2; // rcx
  const char *v3; // r9
  void *v4; // rdi
  unsigned int LastError; // ebx
  const char *v7; // r9
  void *v8; // rcx
  int ReturnLength; // [rsp+20h] [rbp-28h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    operator delete(v2);
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || GetLastError() != 122 )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v3);
  }
  v4 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenUser,
          v4,
          TokenInformationLength,
          &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
    operator delete(v4);
    return LastError;
  }
  v8 = *a1;
  *a1 = v4;
  if ( v8 )
    operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x1400b9ce8  mov     [rsp+arg_8], rbx
0x1400b9ced  push    rdi
0x1400b9cee  sub     rsp, 40h
0x1400b9cf2  mov     rax, cs:__security_cookie
0x1400b9cf9  xor     rax, rsp
0x1400b9cfc  mov     [rsp+48h+var_10], rax
0x1400b9d01  mov     rbx, rcx
0x1400b9d04  mov     rcx, [rcx]; Block
0x1400b9d07  mov     qword ptr [rbx], 0
0x1400b9d0e  test    rcx, rcx
0x1400b9d11  jz      short loc_1400B9D18
0x1400b9d13  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b9d18  xor     r9d, r9d; TokenInformationLength
0x1400b9d1b  mov     [rsp+48h+TokenInformationLength], 0
0x1400b9d23  lea     rax, [rsp+48h+TokenInformationLength]
0x1400b9d28  xor     r8d, r8d; TokenInformation
0x1400b9d2b  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1400b9d30  lea     edx, [r9+1]; TokenInformationClass
0x1400b9d34  lea     rcx, [r9-6]; TokenHandle
0x1400b9d38  call    cs:__imp_GetTokenInformation
0x1400b9d3f  nop     dword ptr [rax+rax+00h]
0x1400b9d44  test    eax, eax
0x1400b9d46  jnz     loc_1400B9DFF
0x1400b9d4c  call    cs:__imp_GetLastError
0x1400b9d53  nop     dword ptr [rax+rax+00h]
0x1400b9d58  cmp     eax, 7Ah ; 'z'
0x1400b9d5b  jnz     loc_1400B9DFF
0x1400b9d61  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x1400b9d65  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400b9d6c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400b9d71  mov     rdi, rax
0x1400b9d74  test    rax, rax
0x1400b9d77  jnz     short loc_1400B9D9B
0x1400b9d79  mov     rcx, [rsp+48h]; this
0x1400b9d7e  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400b9d85  mov     ebx, 8007000Eh
0x1400b9d8a  mov     edx, 119h; void *
0x1400b9d8f  mov     r9d, ebx; char *
0x1400b9d92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400b9d97  mov     eax, ebx
0x1400b9d99  jmp     short loc_1400B9E15
0x1400b9d9b  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1400b9da0  lea     rax, [rsp+48h+TokenInformationLength]
0x1400b9da5  mov     r8, rdi; TokenInformation
0x1400b9da8  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x1400b9dad  mov     edx, 1; TokenInformationClass
0x1400b9db2  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1400b9db9  call    cs:__imp_GetTokenInformation
0x1400b9dc0  nop     dword ptr [rax+rax+00h]
0x1400b9dc5  test    eax, eax
0x1400b9dc7  jnz     short loc_1400B9DEB
0x1400b9dc9  mov     rcx, [rsp+48h]; this
0x1400b9dce  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400b9dd5  mov     edx, 11Ah; void *
0x1400b9dda  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400b9ddf  mov     rcx, rdi; Block
0x1400b9de2  mov     ebx, eax
0x1400b9de4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b9de9  jmp     short loc_1400B9D97
0x1400b9deb  mov     rcx, [rbx]; Block
0x1400b9dee  mov     [rbx], rdi
0x1400b9df1  test    rcx, rcx
0x1400b9df4  jz      short loc_1400B9DFB
0x1400b9df6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b9dfb  xor     eax, eax
0x1400b9dfd  jmp     short loc_1400B9E15
0x1400b9dff  mov     rcx, [rsp+48h]; this
0x1400b9e04  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400b9e0b  mov     edx, 117h; void *
0x1400b9e10  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400b9e15  mov     rcx, [rsp+48h+var_10]
0x1400b9e1a  xor     rcx, rsp; StackCookie
0x1400b9e1d  call    __security_check_cookie
0x1400b9e22  mov     rbx, [rsp+48h+arg_8]
0x1400b9e27  add     rsp, 40h
0x1400b9e2b  pop     rdi
0x1400b9e2c  retn
```
