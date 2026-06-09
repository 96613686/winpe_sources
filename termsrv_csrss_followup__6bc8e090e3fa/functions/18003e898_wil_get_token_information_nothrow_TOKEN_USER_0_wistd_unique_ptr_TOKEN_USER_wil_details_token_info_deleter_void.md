# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18003e898`
- end: `0x18003e9d8`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800445b8`

## callees

- `0x18002609c`
- `0x180033f44`
- `0x18003444c`
- `0x180038ee4`
- `0x18003e898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e902`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e902`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e8ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e96b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e8ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e96b`

## string_xrefs

- `0x18003e934`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003e980`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003e9b6`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rdi
  unsigned int LastError; // ebx
  const char *v9; // r9
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  TokenInformationLength = 0;
  if ( !a2 )
    a2 = -6;
  if ( GetTokenInformation((HANDLE)a2, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
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
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v9);
    operator delete(v6);
    return LastError;
  }
  v10 = *a1;
  *a1 = v6;
  if ( v10 )
    operator delete(v10);
  return 0;
}

```

## disassembly

```asm
0x18003e898  mov     [rsp+arg_8], rbx
0x18003e89d  mov     [rsp+arg_10], rsi
0x18003e8a2  push    rdi
0x18003e8a3  sub     rsp, 30h
0x18003e8a7  mov     rbx, rcx
0x18003e8aa  mov     rsi, rdx
0x18003e8ad  mov     rcx, [rcx]; Block
0x18003e8b0  mov     qword ptr [rbx], 0
0x18003e8b7  test    rcx, rcx
0x18003e8ba  jz      short loc_18003E8C1
0x18003e8bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e8c1  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003e8c8  mov     [rsp+38h+TokenInformationLength], 0
0x18003e8d0  test    rsi, rsi
0x18003e8d3  cmovz   rsi, rax
0x18003e8d7  xor     r9d, r9d; TokenInformationLength
0x18003e8da  lea     rax, [rsp+38h+TokenInformationLength]
0x18003e8df  xor     r8d, r8d; TokenInformation
0x18003e8e2  mov     rcx, rsi; TokenHandle
0x18003e8e5  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003e8ea  lea     edx, [r9+1]; TokenInformationClass
0x18003e8ee  call    cs:__imp_GetTokenInformation
0x18003e8f5  nop     dword ptr [rax+rax+00h]
0x18003e8fa  test    eax, eax
0x18003e8fc  jnz     loc_18003E9B1
0x18003e902  call    cs:__imp_GetLastError
0x18003e909  nop     dword ptr [rax+rax+00h]
0x18003e90e  cmp     eax, 7Ah ; 'z'
0x18003e911  jnz     loc_18003E9B1
0x18003e917  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003e91b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e922  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e927  mov     rdi, rax
0x18003e92a  test    rax, rax
0x18003e92d  jnz     short loc_18003E951
0x18003e92f  mov     rcx, [rsp+38h]; this
0x18003e934  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e93b  mov     ebx, 8007000Eh
0x18003e940  mov     edx, 119h; void *
0x18003e945  mov     r9d, ebx; char *
0x18003e948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e94d  mov     eax, ebx
0x18003e94f  jmp     short loc_18003E9C7
0x18003e951  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003e956  lea     rax, [rsp+38h+TokenInformationLength]
0x18003e95b  mov     r8, rdi; TokenInformation
0x18003e95e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003e963  mov     edx, 1; TokenInformationClass
0x18003e968  mov     rcx, rsi; TokenHandle
0x18003e96b  call    cs:__imp_GetTokenInformation
0x18003e972  nop     dword ptr [rax+rax+00h]
0x18003e977  test    eax, eax
0x18003e979  jnz     short loc_18003E99D
0x18003e97b  mov     rcx, [rsp+38h]; this
0x18003e980  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e987  mov     edx, 11Ah; void *
0x18003e98c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e991  mov     rcx, rdi; Block
0x18003e994  mov     ebx, eax
0x18003e996  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e99b  jmp     short loc_18003E94D
0x18003e99d  mov     rcx, [rbx]; Block
0x18003e9a0  mov     [rbx], rdi
0x18003e9a3  test    rcx, rcx
0x18003e9a6  jz      short loc_18003E9AD
0x18003e9a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e9ad  xor     eax, eax
0x18003e9af  jmp     short loc_18003E9C7
0x18003e9b1  mov     rcx, [rsp+38h]; this
0x18003e9b6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e9bd  mov     edx, 117h; void *
0x18003e9c2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e9c7  mov     rbx, [rsp+38h+arg_8]
0x18003e9cc  mov     rsi, [rsp+38h+arg_10]
0x18003e9d1  add     rsp, 30h
0x18003e9d5  pop     rdi
0x18003e9d6  retn
```
