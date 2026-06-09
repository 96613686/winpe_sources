# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x18003c5c4`
- end: `0x18003c6f1`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180042338`

## callees

- `0x180024d34`
- `0x1800321d4`
- `0x1800326dc`
- `0x180036fa4`
- `0x18003c5c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c628`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c61a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c68b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c61a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c68b`

## string_xrefs

- `0x18003c654`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003c69a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003c6d0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(void **a1, __int64 a2)
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
  if ( GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
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
  if ( !GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
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
0x18003c5c4  mov     [rsp+arg_8], rbx
0x18003c5c9  mov     [rsp+arg_10], rsi
0x18003c5ce  push    rdi
0x18003c5cf  sub     rsp, 30h
0x18003c5d3  mov     rbx, rcx
0x18003c5d6  mov     rsi, rdx
0x18003c5d9  mov     rcx, [rcx]; Block
0x18003c5dc  mov     qword ptr [rbx], 0
0x18003c5e3  test    rcx, rcx
0x18003c5e6  jz      short loc_18003C5ED
0x18003c5e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c5ed  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003c5f4  mov     [rsp+38h+TokenInformationLength], 0
0x18003c5fc  test    rsi, rsi
0x18003c5ff  cmovz   rsi, rax
0x18003c603  xor     r9d, r9d; TokenInformationLength
0x18003c606  lea     rax, [rsp+38h+TokenInformationLength]
0x18003c60b  xor     r8d, r8d; TokenInformation
0x18003c60e  mov     rcx, rsi; TokenHandle
0x18003c611  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003c616  lea     edx, [r9+19h]; TokenInformationClass
0x18003c61a  call    cs:__imp_GetTokenInformation
0x18003c620  test    eax, eax
0x18003c622  jnz     loc_18003C6CB
0x18003c628  call    cs:__imp_GetLastError
0x18003c62e  cmp     eax, 7Ah ; 'z'
0x18003c631  jnz     loc_18003C6CB
0x18003c637  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003c63b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c642  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c647  mov     rdi, rax
0x18003c64a  test    rax, rax
0x18003c64d  jnz     short loc_18003C671
0x18003c64f  mov     rcx, [rsp+38h]; this
0x18003c654  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c65b  mov     ebx, 8007000Eh
0x18003c660  mov     edx, 119h; void *
0x18003c665  mov     r9d, ebx; char *
0x18003c668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c66d  mov     eax, ebx
0x18003c66f  jmp     short loc_18003C6E1
0x18003c671  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003c676  lea     rax, [rsp+38h+TokenInformationLength]
0x18003c67b  mov     r8, rdi; TokenInformation
0x18003c67e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003c683  mov     edx, 19h; TokenInformationClass
0x18003c688  mov     rcx, rsi; TokenHandle
0x18003c68b  call    cs:__imp_GetTokenInformation
0x18003c691  test    eax, eax
0x18003c693  jnz     short loc_18003C6B7
0x18003c695  mov     rcx, [rsp+38h]; this
0x18003c69a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c6a1  mov     edx, 11Ah; void *
0x18003c6a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c6ab  mov     rcx, rdi; Block
0x18003c6ae  mov     ebx, eax
0x18003c6b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c6b5  jmp     short loc_18003C66D
0x18003c6b7  mov     rcx, [rbx]; Block
0x18003c6ba  mov     [rbx], rdi
0x18003c6bd  test    rcx, rcx
0x18003c6c0  jz      short loc_18003C6C7
0x18003c6c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c6c7  xor     eax, eax
0x18003c6c9  jmp     short loc_18003C6E1
0x18003c6cb  mov     rcx, [rsp+38h]; this
0x18003c6d0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c6d7  mov     edx, 117h; void *
0x18003c6dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c6e1  mov     rbx, [rsp+38h+arg_8]
0x18003c6e6  mov     rsi, [rsp+38h+arg_10]
0x18003c6eb  add     rsp, 30h
0x18003c6ef  pop     rdi
0x18003c6f0  retn
```
