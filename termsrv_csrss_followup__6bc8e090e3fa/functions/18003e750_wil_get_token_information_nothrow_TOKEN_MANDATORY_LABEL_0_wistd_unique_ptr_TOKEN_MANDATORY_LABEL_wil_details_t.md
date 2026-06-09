# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x18003e750`
- end: `0x18003e890`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
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
- `0x18003e750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e7a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e823`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e7a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003e823`

## string_xrefs

- `0x18003e7ec`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003e838`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18003e86e`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
0x18003e750  mov     [rsp+arg_8], rbx
0x18003e755  mov     [rsp+arg_10], rsi
0x18003e75a  push    rdi
0x18003e75b  sub     rsp, 30h
0x18003e75f  mov     rbx, rcx
0x18003e762  mov     rsi, rdx
0x18003e765  mov     rcx, [rcx]; Block
0x18003e768  mov     qword ptr [rbx], 0
0x18003e76f  test    rcx, rcx
0x18003e772  jz      short loc_18003E779
0x18003e774  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e779  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003e780  mov     [rsp+38h+TokenInformationLength], 0
0x18003e788  test    rsi, rsi
0x18003e78b  cmovz   rsi, rax
0x18003e78f  xor     r9d, r9d; TokenInformationLength
0x18003e792  lea     rax, [rsp+38h+TokenInformationLength]
0x18003e797  xor     r8d, r8d; TokenInformation
0x18003e79a  mov     rcx, rsi; TokenHandle
0x18003e79d  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18003e7a2  lea     edx, [r9+19h]; TokenInformationClass
0x18003e7a6  call    cs:__imp_GetTokenInformation
0x18003e7ad  nop     dword ptr [rax+rax+00h]
0x18003e7b2  test    eax, eax
0x18003e7b4  jnz     loc_18003E869
0x18003e7ba  call    cs:__imp_GetLastError
0x18003e7c1  nop     dword ptr [rax+rax+00h]
0x18003e7c6  cmp     eax, 7Ah ; 'z'
0x18003e7c9  jnz     loc_18003E869
0x18003e7cf  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003e7d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e7da  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e7df  mov     rdi, rax
0x18003e7e2  test    rax, rax
0x18003e7e5  jnz     short loc_18003E809
0x18003e7e7  mov     rcx, [rsp+38h]; this
0x18003e7ec  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e7f3  mov     ebx, 8007000Eh
0x18003e7f8  mov     edx, 119h; void *
0x18003e7fd  mov     r9d, ebx; char *
0x18003e800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e805  mov     eax, ebx
0x18003e807  jmp     short loc_18003E87F
0x18003e809  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18003e80e  lea     rax, [rsp+38h+TokenInformationLength]
0x18003e813  mov     r8, rdi; TokenInformation
0x18003e816  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18003e81b  mov     edx, 19h; TokenInformationClass
0x18003e820  mov     rcx, rsi; TokenHandle
0x18003e823  call    cs:__imp_GetTokenInformation
0x18003e82a  nop     dword ptr [rax+rax+00h]
0x18003e82f  test    eax, eax
0x18003e831  jnz     short loc_18003E855
0x18003e833  mov     rcx, [rsp+38h]; this
0x18003e838  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e83f  mov     edx, 11Ah; void *
0x18003e844  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e849  mov     rcx, rdi; Block
0x18003e84c  mov     ebx, eax
0x18003e84e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e853  jmp     short loc_18003E805
0x18003e855  mov     rcx, [rbx]; Block
0x18003e858  mov     [rbx], rdi
0x18003e85b  test    rcx, rcx
0x18003e85e  jz      short loc_18003E865
0x18003e860  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e865  xor     eax, eax
0x18003e867  jmp     short loc_18003E87F
0x18003e869  mov     rcx, [rsp+38h]; this
0x18003e86e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e875  mov     edx, 117h; void *
0x18003e87a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e87f  mov     rbx, [rsp+38h+arg_8]
0x18003e884  mov     rsi, [rsp+38h+arg_10]
0x18003e889  add     rsp, 30h
0x18003e88d  pop     rdi
0x18003e88e  retn
```
