# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18003c6f8`
- end: `0x18003c825`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
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
- `0x18003c6f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c75c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c75c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c74e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c7bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c74e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003c7bf`

## string_xrefs

- `0x18003c788`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003c7ce`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003c804`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18003c6f8  mov     [rsp+arg_8], rbx
0x18003c6fd  mov     [rsp+arg_10], rsi
0x18003c702  push    rdi
0x18003c703  sub     rsp, 30h
0x18003c707  mov     rbx, rcx
0x18003c70a  mov     rsi, rdx
0x18003c70d  mov     rcx, [rcx]; Block
0x18003c710  mov     qword ptr [rbx], 0
0x18003c717  test    rcx, rcx
0x18003c71a  jz      short loc_18003C721
0x18003c71c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c721  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003c728  mov     [rsp+38h+TokenInformationLength], 0
0x18003c730  test    rsi, rsi
0x18003c733  cmovz   rsi, rax
0x18003c737  xor     r9d, r9d; TokenInformationLength
0x18003c73a  lea     rax, [rsp+38h+TokenInformationLength]
0x18003c73f  xor     r8d, r8d; TokenInformation
0x18003c742  mov     rcx, rsi; TokenHandle
0x18003c745  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003c74a  lea     edx, [r9+1]; TokenInformationClass
0x18003c74e  call    cs:__imp_GetTokenInformation
0x18003c754  test    eax, eax
0x18003c756  jnz     loc_18003C7FF
0x18003c75c  call    cs:__imp_GetLastError
0x18003c762  cmp     eax, 7Ah ; 'z'
0x18003c765  jnz     loc_18003C7FF
0x18003c76b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003c76f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c776  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c77b  mov     rdi, rax
0x18003c77e  test    rax, rax
0x18003c781  jnz     short loc_18003C7A5
0x18003c783  mov     rcx, [rsp+38h]; this
0x18003c788  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c78f  mov     ebx, 8007000Eh
0x18003c794  mov     edx, 119h; void *
0x18003c799  mov     r9d, ebx; char *
0x18003c79c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7a1  mov     eax, ebx
0x18003c7a3  jmp     short loc_18003C815
0x18003c7a5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003c7aa  lea     rax, [rsp+38h+TokenInformationLength]
0x18003c7af  mov     r8, rdi; TokenInformation
0x18003c7b2  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003c7b7  mov     edx, 1; TokenInformationClass
0x18003c7bc  mov     rcx, rsi; TokenHandle
0x18003c7bf  call    cs:__imp_GetTokenInformation
0x18003c7c5  test    eax, eax
0x18003c7c7  jnz     short loc_18003C7EB
0x18003c7c9  mov     rcx, [rsp+38h]; this
0x18003c7ce  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c7d5  mov     edx, 11Ah; void *
0x18003c7da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c7df  mov     rcx, rdi; Block
0x18003c7e2  mov     ebx, eax
0x18003c7e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c7e9  jmp     short loc_18003C7A1
0x18003c7eb  mov     rcx, [rbx]; Block
0x18003c7ee  mov     [rbx], rdi
0x18003c7f1  test    rcx, rcx
0x18003c7f4  jz      short loc_18003C7FB
0x18003c7f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003c7fb  xor     eax, eax
0x18003c7fd  jmp     short loc_18003C815
0x18003c7ff  mov     rcx, [rsp+38h]; this
0x18003c804  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003c80b  mov     edx, 117h; void *
0x18003c810  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c815  mov     rbx, [rsp+38h+arg_8]
0x18003c81a  mov     rsi, [rsp+38h+arg_10]
0x18003c81f  add     rsp, 30h
0x18003c823  pop     rdi
0x18003c824  retn
```
