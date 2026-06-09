# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180027db4`
- end: `0x180027ee1`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `301`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027f34`

## callees

- `0x180002574`
- `0x18000299c`
- `0x180008914`
- `0x180008934`
- `0x180027db4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027e0a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027e7b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027e0a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027e7b`

## string_xrefs

- `0x180027e44`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180027e8a`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x180027ec0`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
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
0x180027db4  mov     [rsp+arg_8], rbx
0x180027db9  mov     [rsp+arg_10], rsi
0x180027dbe  push    rdi
0x180027dbf  sub     rsp, 30h
0x180027dc3  mov     rbx, rcx
0x180027dc6  mov     rsi, rdx
0x180027dc9  mov     rcx, [rcx]; Block
0x180027dcc  mov     qword ptr [rbx], 0
0x180027dd3  test    rcx, rcx
0x180027dd6  jz      short loc_180027DDD
0x180027dd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027ddd  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180027de4  mov     [rsp+38h+TokenInformationLength], 0
0x180027dec  test    rsi, rsi
0x180027def  cmovz   rsi, rax
0x180027df3  xor     r9d, r9d; TokenInformationLength
0x180027df6  lea     rax, [rsp+38h+TokenInformationLength]
0x180027dfb  xor     r8d, r8d; TokenInformation
0x180027dfe  mov     rcx, rsi; TokenHandle
0x180027e01  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180027e06  lea     edx, [r9+1]; TokenInformationClass
0x180027e0a  call    cs:__imp_GetTokenInformation
0x180027e10  test    eax, eax
0x180027e12  jnz     loc_180027EBB
0x180027e18  call    cs:__imp_GetLastError
0x180027e1e  cmp     eax, 7Ah ; 'z'
0x180027e21  jnz     loc_180027EBB
0x180027e27  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180027e2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027e32  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027e37  mov     rdi, rax
0x180027e3a  test    rax, rax
0x180027e3d  jnz     short loc_180027E61
0x180027e3f  mov     rcx, [rsp+38h]; this
0x180027e44  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027e4b  mov     ebx, 8007000Eh
0x180027e50  mov     edx, 119h; void *
0x180027e55  mov     r9d, ebx; char *
0x180027e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e5d  mov     eax, ebx
0x180027e5f  jmp     short loc_180027ED1
0x180027e61  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180027e66  lea     rax, [rsp+38h+TokenInformationLength]
0x180027e6b  mov     r8, rdi; TokenInformation
0x180027e6e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180027e73  mov     edx, 1; TokenInformationClass
0x180027e78  mov     rcx, rsi; TokenHandle
0x180027e7b  call    cs:__imp_GetTokenInformation
0x180027e81  test    eax, eax
0x180027e83  jnz     short loc_180027EA7
0x180027e85  mov     rcx, [rsp+38h]; this
0x180027e8a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027e91  mov     edx, 11Ah; void *
0x180027e96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027e9b  mov     rcx, rdi; Block
0x180027e9e  mov     ebx, eax
0x180027ea0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027ea5  jmp     short loc_180027E5D
0x180027ea7  mov     rcx, [rbx]; Block
0x180027eaa  mov     [rbx], rdi
0x180027ead  test    rcx, rcx
0x180027eb0  jz      short loc_180027EB7
0x180027eb2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027eb7  xor     eax, eax
0x180027eb9  jmp     short loc_180027ED1
0x180027ebb  mov     rcx, [rsp+38h]; this
0x180027ec0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027ec7  mov     edx, 117h; void *
0x180027ecc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027ed1  mov     rbx, [rsp+38h+arg_8]
0x180027ed6  mov     rsi, [rsp+38h+arg_10]
0x180027edb  add     rsp, 30h
0x180027edf  pop     rdi
0x180027ee0  retn
```
