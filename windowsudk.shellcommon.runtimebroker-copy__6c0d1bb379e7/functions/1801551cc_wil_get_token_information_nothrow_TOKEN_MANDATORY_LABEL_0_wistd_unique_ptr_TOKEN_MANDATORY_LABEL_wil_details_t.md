# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x1801551cc`
- end: `0x1801552f9`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180155174`
- `0x1802f3064`

## callees

- `0x1800e2988`
- `0x1800e34bc`
- `0x1801551cc`
- `0x18015d524`
- `0x18027741c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155230`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180155222`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180155293`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180155222`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180155293`

## string_xrefs

- `0x18015525c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1801552a2`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1801552d8`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
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
0x1801551cc  mov     [rsp+arg_8], rbx
0x1801551d1  mov     [rsp+arg_10], rsi
0x1801551d6  push    rdi
0x1801551d7  sub     rsp, 30h
0x1801551db  mov     rbx, rcx
0x1801551de  mov     rsi, rdx
0x1801551e1  mov     rcx, [rcx]; Block
0x1801551e4  mov     qword ptr [rbx], 0
0x1801551eb  test    rcx, rcx
0x1801551ee  jz      short loc_1801551F5
0x1801551f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801551f5  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1801551fc  mov     [rsp+38h+TokenInformationLength], 0
0x180155204  test    rsi, rsi
0x180155207  cmovz   rsi, rax
0x18015520b  xor     r9d, r9d; TokenInformationLength
0x18015520e  lea     rax, [rsp+38h+TokenInformationLength]
0x180155213  xor     r8d, r8d; TokenInformation
0x180155216  mov     rcx, rsi; TokenHandle
0x180155219  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18015521e  lea     edx, [r9+19h]; TokenInformationClass
0x180155222  call    cs:__imp_GetTokenInformation
0x180155228  test    eax, eax
0x18015522a  jnz     loc_1801552D3
0x180155230  call    cs:__imp_GetLastError
0x180155236  cmp     eax, 7Ah ; 'z'
0x180155239  jnz     loc_1801552D3
0x18015523f  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180155243  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18015524a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18015524f  mov     rdi, rax
0x180155252  test    rax, rax
0x180155255  jnz     short loc_180155279
0x180155257  mov     rcx, [rsp+38h]; this
0x18015525c  lea     r8, aOnecoreInterna_21; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180155263  mov     ebx, 8007000Eh
0x180155268  mov     edx, 119h; void *
0x18015526d  mov     r9d, ebx; char *
0x180155270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180155275  mov     eax, ebx
0x180155277  jmp     short loc_1801552E9
0x180155279  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18015527e  lea     rax, [rsp+38h+TokenInformationLength]
0x180155283  mov     r8, rdi; TokenInformation
0x180155286  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18015528b  mov     edx, 19h; TokenInformationClass
0x180155290  mov     rcx, rsi; TokenHandle
0x180155293  call    cs:__imp_GetTokenInformation
0x180155299  test    eax, eax
0x18015529b  jnz     short loc_1801552BF
0x18015529d  mov     rcx, [rsp+38h]; this
0x1801552a2  lea     r8, aOnecoreInterna_21; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801552a9  mov     edx, 11Ah; void *
0x1801552ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801552b3  mov     rcx, rdi; Block
0x1801552b6  mov     ebx, eax
0x1801552b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801552bd  jmp     short loc_180155275
0x1801552bf  mov     rcx, [rbx]; Block
0x1801552c2  mov     [rbx], rdi
0x1801552c5  test    rcx, rcx
0x1801552c8  jz      short loc_1801552CF
0x1801552ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801552cf  xor     eax, eax
0x1801552d1  jmp     short loc_1801552E9
0x1801552d3  mov     rcx, [rsp+38h]; this
0x1801552d8  lea     r8, aOnecoreInterna_21; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1801552df  mov     edx, 117h; void *
0x1801552e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801552e9  mov     rbx, [rsp+38h+arg_8]
0x1801552ee  mov     rsi, [rsp+38h+arg_10]
0x1801552f3  add     rsp, 30h
0x1801552f7  pop     rdi
0x1801552f8  retn
```
