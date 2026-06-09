# wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)

- ea: `0x18007c318`
- end: `0x18007c434`
- name: `??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180075a3c`

## callees

- `0x18006b91c`
- `0x18006b9b4`
- `0x180078a34`
- `0x180079030`
- `0x18007c318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c36c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c36c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c35e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c3d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c35e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007c3d3`

## string_xrefs

- `0x18007c398`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18007c3e2`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x18007c418`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

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
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v4);
  }
  v5 = operator new((unsigned int)TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v5 )
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
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
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
0x18007c318  mov     [rsp+arg_0], rbx
0x18007c31d  mov     [rsp+TokenInformationLength], rdx
0x18007c322  push    rdi
0x18007c323  sub     rsp, 30h
0x18007c327  mov     rbx, rcx
0x18007c32a  mov     rcx, [rcx]; Block
0x18007c32d  mov     qword ptr [rbx], 0
0x18007c334  test    rcx, rcx
0x18007c337  jz      short loc_18007C33E
0x18007c339  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c33e  xor     r9d, r9d; TokenInformationLength
0x18007c341  mov     dword ptr [rsp+38h+TokenInformationLength], 0
0x18007c349  lea     rax, [rsp+38h+TokenInformationLength]
0x18007c34e  xor     r8d, r8d; TokenInformation
0x18007c351  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x18007c356  lea     edx, [r9+1]; TokenInformationClass
0x18007c35a  lea     rcx, [r9-6]; TokenHandle
0x18007c35e  call    cs:__imp_GetTokenInformation
0x18007c364  test    eax, eax
0x18007c366  jnz     loc_18007C413
0x18007c36c  call    cs:__imp_GetLastError
0x18007c372  cmp     eax, 7Ah ; 'z'
0x18007c375  jnz     loc_18007C413
0x18007c37b  mov     ecx, dword ptr [rsp+38h+TokenInformationLength]; unsigned __int64
0x18007c37f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007c386  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007c38b  mov     rdi, rax
0x18007c38e  test    rax, rax
0x18007c391  jnz     short loc_18007C3B5
0x18007c393  mov     rcx, [rsp+38h]; this
0x18007c398  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007c39f  mov     ebx, 8007000Eh
0x18007c3a4  mov     edx, 119h; void *
0x18007c3a9  mov     r9d, ebx; char *
0x18007c3ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c3b1  mov     eax, ebx
0x18007c3b3  jmp     short loc_18007C429
0x18007c3b5  mov     r9d, dword ptr [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18007c3ba  lea     rax, [rsp+38h+TokenInformationLength]
0x18007c3bf  mov     r8, rdi; TokenInformation
0x18007c3c2  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18007c3c7  mov     edx, 1; TokenInformationClass
0x18007c3cc  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18007c3d3  call    cs:__imp_GetTokenInformation
0x18007c3d9  test    eax, eax
0x18007c3db  jnz     short loc_18007C3FF
0x18007c3dd  mov     rcx, [rsp+38h]; this
0x18007c3e2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007c3e9  mov     edx, 11Ah; void *
0x18007c3ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007c3f3  mov     rcx, rdi; Block
0x18007c3f6  mov     ebx, eax
0x18007c3f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c3fd  jmp     short loc_18007C3B1
0x18007c3ff  mov     rcx, [rbx]; Block
0x18007c402  mov     [rbx], rdi
0x18007c405  test    rcx, rcx
0x18007c408  jz      short loc_18007C40F
0x18007c40a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c40f  xor     eax, eax
0x18007c411  jmp     short loc_18007C429
0x18007c413  mov     rcx, [rsp+38h]; this
0x18007c418  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007c41f  mov     edx, 117h; void *
0x18007c424  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007c429  mov     rbx, [rsp+38h+arg_0]
0x18007c42e  add     rsp, 30h
0x18007c432  pop     rdi
0x18007c433  retn
```
