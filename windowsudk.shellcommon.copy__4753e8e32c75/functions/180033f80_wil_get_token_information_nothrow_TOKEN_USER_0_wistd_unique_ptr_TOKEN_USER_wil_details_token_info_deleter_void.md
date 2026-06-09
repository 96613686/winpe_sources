# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x180033f80`
- end: `0x1800340c1`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033f28`
- `0x1802b2594`

## callees

- `0x180033f80`
- `0x1800e2988`
- `0x1800e34bc`
- `0x18015cb00`
- `0x18015d524`
- `0x18027741c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033fe5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003402c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180033fe5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003402c`

## string_xrefs

- `0x18003404f`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\token_helpers.h`
- `0x180034082`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\token_helpers.h`
- `0x1800340a4`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_USER,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rdi
  const char *v7; // r9
  void *v8; // rcx
  unsigned int LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-28h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

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
             (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\token_helpers.h",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return LastError;
  }
  if ( !GetTokenInformation((HANDLE)a2, TokenUser, v6, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11A,
                  (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\token_helpers.h",
                  v7);
    operator delete(v6);
    return LastError;
  }
  v8 = *a1;
  *a1 = v6;
  if ( v8 )
    operator delete(v8);
  return 0;
}

```

## disassembly

```asm
0x180033f80  mov     [rsp+arg_10], rbx
0x180033f85  mov     [rsp+arg_18], rsi
0x180033f8a  push    rdi
0x180033f8b  sub     rsp, 40h
0x180033f8f  mov     rax, cs:__security_cookie
0x180033f96  xor     rax, rsp
0x180033f99  mov     [rsp+48h+var_10], rax
0x180033f9e  mov     rbx, rcx
0x180033fa1  mov     rsi, rdx
0x180033fa4  mov     rcx, [rcx]; Block
0x180033fa7  mov     qword ptr [rbx], 0
0x180033fae  test    rcx, rcx
0x180033fb1  jz      short loc_180033FB8
0x180033fb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033fb8  mov     rax, 0FFFFFFFFFFFFFFFAh
0x180033fbf  mov     [rsp+48h+TokenInformationLength], 0
0x180033fc7  test    rsi, rsi
0x180033fca  cmovz   rsi, rax
0x180033fce  xor     r9d, r9d; TokenInformationLength
0x180033fd1  lea     rax, [rsp+48h+TokenInformationLength]
0x180033fd6  xor     r8d, r8d; TokenInformation
0x180033fd9  mov     rcx, rsi; TokenHandle
0x180033fdc  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x180033fe1  lea     edx, [r9+1]; TokenInformationClass
0x180033fe5  call    cs:__imp_GetTokenInformation
0x180033feb  test    eax, eax
0x180033fed  jnz     short loc_18003404A
0x180033fef  call    cs:__imp_GetLastError
0x180033ff5  cmp     eax, 7Ah ; 'z'
0x180033ff8  jnz     short loc_18003404A
0x180033ffa  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x180033ffe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034005  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003400a  mov     rdi, rax
0x18003400d  test    rax, rax
0x180034010  jz      short loc_18003407D
0x180034012  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180034017  lea     rax, [rsp+48h+TokenInformationLength]
0x18003401c  mov     r8, rdi; TokenInformation
0x18003401f  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x180034024  mov     edx, 1; TokenInformationClass
0x180034029  mov     rcx, rsi; TokenHandle
0x18003402c  call    cs:__imp_GetTokenInformation
0x180034032  test    eax, eax
0x180034034  jz      short loc_18003409F
0x180034036  mov     rcx, [rbx]; Block
0x180034039  mov     [rbx], rdi
0x18003403c  test    rcx, rcx
0x18003403f  jz      short loc_180034046
0x180034041  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034046  xor     eax, eax
0x180034048  jmp     short loc_180034060
0x18003404a  mov     rcx, [rsp+48h]; this
0x18003404f  lea     r8, aOnecoreInterna_5; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x180034056  mov     edx, 117h; void *
0x18003405b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034060  mov     rcx, [rsp+48h+var_10]
0x180034065  xor     rcx, rsp; StackCookie
0x180034068  call    __security_check_cookie
0x18003406d  mov     rbx, [rsp+48h+arg_10]
0x180034072  mov     rsi, [rsp+48h+arg_18]
0x180034077  add     rsp, 40h
0x18003407b  pop     rdi
0x18003407c  retn
0x18003407d  mov     rcx, [rsp+48h]; this
0x180034082  lea     r8, aOnecoreInterna_5; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x180034089  mov     ebx, 8007000Eh
0x18003408e  mov     edx, 119h; void *
0x180034093  mov     r9d, ebx; char *
0x180034096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003409b  mov     eax, ebx
0x18003409d  jmp     short loc_180034060
0x18003409f  mov     rcx, [rsp+48h]; this
0x1800340a4  lea     r8, aOnecoreInterna_5; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x1800340ab  mov     edx, 11Ah; void *
0x1800340b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800340b5  mov     rcx, rdi; Block
0x1800340b8  mov     ebx, eax
0x1800340ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800340bf  jmp     short loc_18003409B
```
