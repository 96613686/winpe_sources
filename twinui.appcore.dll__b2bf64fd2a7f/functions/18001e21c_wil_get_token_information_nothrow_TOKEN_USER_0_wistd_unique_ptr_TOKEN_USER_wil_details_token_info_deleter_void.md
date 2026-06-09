# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18001e21c`
- end: `0x18001e338`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e1c4`

## callees

- `0x18001cc38`
- `0x18001e21c`
- `0x18001e340`
- `0x18002b1e0`
- `0x18002b5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e270`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e262`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e2d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e262`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e2d7`

## string_xrefs

- `0x18001e29c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001e2e6`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18001e31c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v3; // rcx
  const char *v4; // r9
  void *v5; // rdi
  unsigned int LastError; // ebx
  const char *v8; // r9
  void *v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = a2;
  v3 = *a1;
  *a1 = 0;
  if ( v3 )
    operator delete(v3);
  LODWORD(TokenInformationLength) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, (PDWORD)&TokenInformationLength)
    || GetLastError() != 122 )
  {
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
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
  if ( !GetTokenInformation(
          (HANDLE)0xFFFFFFFFFFFFFFFALL,
          TokenUser,
          v5,
          TokenInformationLength,
          (PDWORD)&TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v8);
    operator delete(v5);
    return LastError;
  }
  v9 = *a1;
  *a1 = v5;
  if ( v9 )
    operator delete(v9);
  return 0;
}

```

## disassembly

```asm
0x18001e21c  mov     [rsp+arg_0], rbx
0x18001e221  mov     [rsp+TokenInformationLength], rdx
0x18001e226  push    rdi
0x18001e227  sub     rsp, 30h
0x18001e22b  mov     rbx, rcx
0x18001e22e  mov     rcx, [rcx]; Block
0x18001e231  mov     qword ptr [rbx], 0
0x18001e238  test    rcx, rcx
0x18001e23b  jz      short loc_18001E242
0x18001e23d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e242  xor     r9d, r9d; TokenInformationLength
0x18001e245  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x18001e24d  lea     rax, [rsp+38h+TokenInformationLength]
0x18001e252  xor     r8d, r8d; TokenInformation
0x18001e255  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18001e25a  lea     edx, [r9+1]; TokenInformationClass
0x18001e25e  lea     rcx, [r9-6]; TokenHandle
0x18001e262  call    cs:__imp_GetTokenInformation
0x18001e268  test    eax, eax
0x18001e26a  jnz     loc_18001E317
0x18001e270  call    cs:__imp_GetLastError
0x18001e276  cmp     eax, 7Ah ; 'z'
0x18001e279  jnz     loc_18001E317
0x18001e27f  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x18001e283  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e28a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e28f  mov     rdi, rax
0x18001e292  test    rax, rax
0x18001e295  jnz     short loc_18001E2B9
0x18001e297  mov     rcx, [rsp+38h]; this
0x18001e29c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e2a3  mov     ebx, 8007000Eh
0x18001e2a8  mov     edx, 119h; void *
0x18001e2ad  mov     r9d, ebx; char *
0x18001e2b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e2b5  mov     eax, ebx
0x18001e2b7  jmp     short loc_18001E32D
0x18001e2b9  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18001e2be  lea     rax, [rsp+38h+TokenInformationLength]
0x18001e2c3  mov     r8, rdi; TokenInformation
0x18001e2c6  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18001e2cb  mov     edx, 1; TokenInformationClass
0x18001e2d0  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18001e2d7  call    cs:__imp_GetTokenInformation
0x18001e2dd  test    eax, eax
0x18001e2df  jnz     short loc_18001E303
0x18001e2e1  mov     rcx, [rsp+38h]; this
0x18001e2e6  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e2ed  mov     edx, 11Ah; void *
0x18001e2f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e2f7  mov     rcx, rdi; Block
0x18001e2fa  mov     ebx, eax
0x18001e2fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e301  jmp     short loc_18001E2B5
0x18001e303  mov     rcx, [rbx]; Block
0x18001e306  mov     [rbx], rdi
0x18001e309  test    rcx, rcx
0x18001e30c  jz      short loc_18001E313
0x18001e30e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e313  xor     eax, eax
0x18001e315  jmp     short loc_18001E32D
0x18001e317  mov     rcx, [rsp+38h]; this
0x18001e31c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001e323  mov     edx, 117h; void *
0x18001e328  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e32d  mov     rbx, [rsp+38h+arg_0]
0x18001e332  add     rsp, 30h
0x18001e336  pop     rdi
0x18001e337  retn
```
