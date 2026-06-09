# wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)

- ea: `0x180022780`
- end: `0x1800228c0`
- name: `??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024070`

## callees

- `0x1800016a4`
- `0x1800020b4`
- `0x180013524`
- `0x180013544`
- `0x180022780`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800227ea`
- `KERNEL32!GetLastError` at `0x1800227ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800227d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022853`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800227d6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180022853`

## string_xrefs

- `0x18002281c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180022868`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x18002289e`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

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
0x180022780  mov     [rsp+arg_8], rbx
0x180022785  mov     [rsp+arg_10], rsi
0x18002278a  push    rdi
0x18002278b  sub     rsp, 30h
0x18002278f  mov     rbx, rcx
0x180022792  mov     rsi, rdx
0x180022795  mov     rcx, [rcx]; Block
0x180022798  mov     qword ptr [rbx], 0
0x18002279f  test    rcx, rcx
0x1800227a2  jz      short loc_1800227A9
0x1800227a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800227a9  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1800227b0  mov     [rsp+38h+TokenInformationLength], 0
0x1800227b8  test    rsi, rsi
0x1800227bb  cmovz   rsi, rax
0x1800227bf  xor     r9d, r9d; TokenInformationLength
0x1800227c2  lea     rax, [rsp+38h+TokenInformationLength]
0x1800227c7  xor     r8d, r8d; TokenInformation
0x1800227ca  mov     rcx, rsi; TokenHandle
0x1800227cd  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800227d2  lea     edx, [r9+19h]; TokenInformationClass
0x1800227d6  call    cs:__imp_GetTokenInformation
0x1800227dd  nop     dword ptr [rax+rax+00h]
0x1800227e2  test    eax, eax
0x1800227e4  jnz     loc_180022899
0x1800227ea  call    cs:__imp_GetLastError
0x1800227f1  nop     dword ptr [rax+rax+00h]
0x1800227f6  cmp     eax, 7Ah ; 'z'
0x1800227f9  jnz     loc_180022899
0x1800227ff  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180022803  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002280a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002280f  mov     rdi, rax
0x180022812  test    rax, rax
0x180022815  jnz     short loc_180022839
0x180022817  mov     rcx, [rsp+38h]; this
0x18002281c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022823  mov     ebx, 8007000Eh
0x180022828  mov     edx, 119h; void *
0x18002282d  mov     r9d, ebx; char *
0x180022830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022835  mov     eax, ebx
0x180022837  jmp     short loc_1800228AF
0x180022839  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002283e  lea     rax, [rsp+38h+TokenInformationLength]
0x180022843  mov     r8, rdi; TokenInformation
0x180022846  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18002284b  mov     edx, 19h; TokenInformationClass
0x180022850  mov     rcx, rsi; TokenHandle
0x180022853  call    cs:__imp_GetTokenInformation
0x18002285a  nop     dword ptr [rax+rax+00h]
0x18002285f  test    eax, eax
0x180022861  jnz     short loc_180022885
0x180022863  mov     rcx, [rsp+38h]; this
0x180022868  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002286f  mov     edx, 11Ah; void *
0x180022874  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022879  mov     rcx, rdi; Block
0x18002287c  mov     ebx, eax
0x18002287e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022883  jmp     short loc_180022835
0x180022885  mov     rcx, [rbx]; Block
0x180022888  mov     [rbx], rdi
0x18002288b  test    rcx, rcx
0x18002288e  jz      short loc_180022895
0x180022890  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180022895  xor     eax, eax
0x180022897  jmp     short loc_1800228AF
0x180022899  mov     rcx, [rsp+38h]; this
0x18002289e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800228a5  mov     edx, 117h; void *
0x1800228aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800228af  mov     rbx, [rsp+38h+arg_8]
0x1800228b4  mov     rsi, [rsp+38h+arg_10]
0x1800228b9  add     rsp, 30h
0x1800228bd  pop     rdi
0x1800228be  retn
```
