# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x180021b2c`
- end: `0x180021c59`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800232b0`

## callees

- `0x180001634`
- `0x180002044`
- `0x180012cb8`
- `0x180012cd8`
- `0x180021b2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180021b90`
- `KERNEL32!GetLastError` at `0x180021b90`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021b82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021bf3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021b82`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021bf3`

## string_xrefs

- `0x180021bbc`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180021c02`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180021c38`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation((HANDLE)a2, TokenIntegrityLevel, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
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
0x180021b2c  mov     [rsp+arg_8], rbx
0x180021b31  mov     [rsp+arg_10], rsi
0x180021b36  push    rdi
0x180021b37  sub     rsp, 30h
0x180021b3b  mov     rbx, rcx
0x180021b3e  mov     rsi, rdx
0x180021b41  mov     rcx, [rcx]; Block
0x180021b44  mov     qword ptr [rbx], 0
0x180021b4b  test    rcx, rcx
0x180021b4e  jz      short loc_180021B55
0x180021b50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021b55  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180021b5c  mov     [rsp+38h+TokenInformationLength], 0
0x180021b64  test    rsi, rsi
0x180021b67  cmovz   rsi, rax
0x180021b6b  xor     r9d, r9d; TokenInformationLength
0x180021b6e  lea     rax, [rsp+38h+TokenInformationLength]
0x180021b73  xor     r8d, r8d; TokenInformation
0x180021b76  mov     rcx, rsi; TokenHandle
0x180021b79  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180021b7e  lea     edx, [r9+19h]; TokenInformationClass
0x180021b82  call    cs:__imp_GetTokenInformation
0x180021b88  test    eax, eax
0x180021b8a  jnz     loc_180021C33
0x180021b90  call    cs:__imp_GetLastError
0x180021b96  cmp     eax, 7Ah ; 'z'
0x180021b99  jnz     loc_180021C33
0x180021b9f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180021ba3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021baa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021baf  mov     rdi, rax
0x180021bb2  test    rax, rax
0x180021bb5  jnz     short loc_180021BD9
0x180021bb7  mov     rcx, [rsp+38h]; this
0x180021bbc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021bc3  mov     ebx, 8007000Eh
0x180021bc8  mov     edx, 119h; void *
0x180021bcd  mov     r9d, ebx; char *
0x180021bd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021bd5  mov     eax, ebx
0x180021bd7  jmp     short loc_180021C49
0x180021bd9  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180021bde  lea     rax, [rsp+38h+TokenInformationLength]
0x180021be3  mov     r8, rdi; TokenInformation
0x180021be6  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180021beb  mov     edx, 19h; TokenInformationClass
0x180021bf0  mov     rcx, rsi; TokenHandle
0x180021bf3  call    cs:__imp_GetTokenInformation
0x180021bf9  test    eax, eax
0x180021bfb  jnz     short loc_180021C1F
0x180021bfd  mov     rcx, [rsp+38h]; this
0x180021c02  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021c09  mov     edx, 11Ah; void *
0x180021c0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021c13  mov     rcx, rdi; Block
0x180021c16  mov     ebx, eax
0x180021c18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021c1d  jmp     short loc_180021BD5
0x180021c1f  mov     rcx, [rbx]; Block
0x180021c22  mov     [rbx], rdi
0x180021c25  test    rcx, rcx
0x180021c28  jz      short loc_180021C2F
0x180021c2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021c2f  xor     eax, eax
0x180021c31  jmp     short loc_180021C49
0x180021c33  mov     rcx, [rsp+38h]; this
0x180021c38  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021c3f  mov     edx, 117h; void *
0x180021c44  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021c49  mov     rbx, [rsp+38h+arg_8]
0x180021c4e  mov     rsi, [rsp+38h+arg_10]
0x180021c53  add     rsp, 30h
0x180021c57  pop     rdi
0x180021c58  retn
```
