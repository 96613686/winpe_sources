# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x1800b8da8`
- end: `0x1800b8ed8`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `304`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003a3c0`

## callees

- `0x1800088e8`
- `0x180061e1c`
- `0x18006c18c`
- `0x1800b8da8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800b8dcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800b8e95`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800b8ea8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800b8dcc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800b8e95`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800b8ea8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b8dff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b8e70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b8dff`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800b8e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8e0d`

## string_xrefs

- `0x1800b8e39`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800b8e7f`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800b8eb7`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x1800b8da8  mov     [rsp+arg_8], rbx
0x1800b8dad  mov     [rsp+arg_10], rsi
0x1800b8db2  push    rdi
0x1800b8db3  sub     rsp, 30h
0x1800b8db7  mov     rbx, rcx
0x1800b8dba  mov     rsi, rdx
0x1800b8dbd  mov     rcx, [rcx]
0x1800b8dc0  mov     qword ptr [rbx], 0
0x1800b8dc7  test    rcx, rcx
0x1800b8dca  jz      short loc_1800B8DD2
0x1800b8dcc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800b8dd2  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800b8dd9  mov     [rsp+38h+TokenInformationLength], 0
0x1800b8de1  test    rsi, rsi
0x1800b8de4  cmovz   rsi, rax
0x1800b8de8  xor     r9d, r9d; TokenInformationLength
0x1800b8deb  lea     rax, [rsp+38h+TokenInformationLength]
0x1800b8df0  xor     r8d, r8d; TokenInformation
0x1800b8df3  mov     rcx, rsi; TokenHandle
0x1800b8df6  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800b8dfb  lea     edx, [r9+1]; TokenInformationClass
0x1800b8dff  call    cs:__imp_GetTokenInformation
0x1800b8e05  test    eax, eax
0x1800b8e07  jnz     loc_1800B8EB2
0x1800b8e0d  call    cs:__imp_GetLastError
0x1800b8e13  cmp     eax, 7Ah ; 'z'
0x1800b8e16  jnz     loc_1800B8EB2
0x1800b8e1c  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1800b8e20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b8e27  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8e2c  mov     rdi, rax
0x1800b8e2f  test    rax, rax
0x1800b8e32  jnz     short loc_1800B8E56
0x1800b8e34  mov     rcx, [rsp+38h]; this
0x1800b8e39  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800b8e40  mov     ebx, 8007000Eh
0x1800b8e45  mov     edx, 119h; void *
0x1800b8e4a  mov     r9d, ebx; char *
0x1800b8e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8e52  mov     eax, ebx
0x1800b8e54  jmp     short loc_1800B8EC8
0x1800b8e56  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800b8e5b  lea     rax, [rsp+38h+TokenInformationLength]
0x1800b8e60  mov     r8, rdi; TokenInformation
0x1800b8e63  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800b8e68  mov     edx, 1; TokenInformationClass
0x1800b8e6d  mov     rcx, rsi; TokenHandle
0x1800b8e70  call    cs:__imp_GetTokenInformation
0x1800b8e76  test    eax, eax
0x1800b8e78  jnz     short loc_1800B8E9D
0x1800b8e7a  mov     rcx, [rsp+38h]; this
0x1800b8e7f  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800b8e86  mov     edx, 11Ah; void *
0x1800b8e8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b8e90  mov     rcx, rdi
0x1800b8e93  mov     ebx, eax
0x1800b8e95  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800b8e9b  jmp     short loc_1800B8E52
0x1800b8e9d  mov     rcx, [rbx]
0x1800b8ea0  mov     [rbx], rdi
0x1800b8ea3  test    rcx, rcx
0x1800b8ea6  jz      short loc_1800B8EAE
0x1800b8ea8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800b8eae  xor     eax, eax
0x1800b8eb0  jmp     short loc_1800B8EC8
0x1800b8eb2  mov     rcx, [rsp+38h]; this
0x1800b8eb7  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800b8ebe  mov     edx, 117h; void *
0x1800b8ec3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b8ec8  mov     rbx, [rsp+38h+arg_8]
0x1800b8ecd  mov     rsi, [rsp+38h+arg_10]
0x1800b8ed2  add     rsp, 30h
0x1800b8ed6  pop     rdi
0x1800b8ed7  retn
```
