# wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_PRIVILEGES,wil::details::token_info_deleter> &,void *)

- ea: `0x180036960`
- end: `0x180036aae`
- name: `??$get_token_information_nothrow@U_TOKEN_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180034d04`
- `0x180035088`

## callees

- `0x180003950`
- `0x180003974`
- `0x180036960`
- `0x180042630`
- `0x1800430f8`
- `0x180043160`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800369c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036a34`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800369c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036a34`

## string_xrefs

- `0x1800369ff`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`
- `0x180036a43`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`
- `0x180036a80`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  unsigned int LastError; // edi
  const char *v8; // r9
  void *v9; // rcx
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
  if ( !GetTokenInformation((HANDLE)a2, TokenPrivileges, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      if ( GetTokenInformation((HANDLE)a2, TokenPrivileges, v6, TokenInformationLength, &TokenInformationLength) )
      {
        v9 = *a1;
        *a1 = v6;
        if ( v9 )
          operator delete(v9);
        return 0;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\"
                                  "wil\\token_helpers.h",
                    v8);
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\token_helpers.h",
        (const char *)0x8007000ELL,
        ReturnLength);
    }
    if ( v6 )
      operator delete(v6);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x117,
           (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\token_helpers.h",
           v5);
}

```

## disassembly

```asm
0x180036960  mov     [rsp+arg_10], rbx
0x180036965  mov     [rsp+arg_18], rsi
0x18003696a  push    rdi
0x18003696b  sub     rsp, 40h
0x18003696f  mov     rax, cs:__security_cookie
0x180036976  xor     rax, rsp
0x180036979  mov     [rsp+48h+var_10], rax
0x18003697e  mov     rdi, rcx
0x180036981  mov     rsi, rdx
0x180036984  mov     rcx, [rcx]; Block
0x180036987  mov     qword ptr [rdi], 0
0x18003698e  test    rcx, rcx
0x180036991  jz      short loc_180036998
0x180036993  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036998  mov     rax, 0FFFFFFFFFFFFFFFAh
0x18003699f  mov     [rsp+48h+TokenInformationLength], 0
0x1800369a7  test    rsi, rsi
0x1800369aa  cmovz   rsi, rax
0x1800369ae  xor     r9d, r9d; TokenInformationLength
0x1800369b1  lea     rax, [rsp+48h+TokenInformationLength]
0x1800369b6  xor     r8d, r8d; TokenInformation
0x1800369b9  mov     rcx, rsi; TokenHandle
0x1800369bc  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800369c1  lea     edx, [r9+3]; TokenInformationClass
0x1800369c5  call    cs:__imp_GetTokenInformation
0x1800369cb  test    eax, eax
0x1800369cd  jnz     loc_180036A7B
0x1800369d3  call    cs:__imp_GetLastError
0x1800369d9  cmp     eax, 7Ah ; 'z'
0x1800369dc  jnz     loc_180036A7B
0x1800369e2  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x1800369e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800369ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800369f2  mov     rbx, rax
0x1800369f5  test    rax, rax
0x1800369f8  jnz     short loc_180036A1A
0x1800369fa  mov     rcx, [rsp+48h]; this
0x1800369ff  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180036a06  mov     edi, 8007000Eh
0x180036a0b  mov     edx, 119h; void *
0x180036a10  mov     r9d, edi; char *
0x180036a13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036a18  jmp     short loc_180036A56
0x180036a1a  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180036a1f  lea     rax, [rsp+48h+TokenInformationLength]
0x180036a24  mov     r8, rbx; TokenInformation
0x180036a27  mov     qword ptr [rsp+48h+ReturnLength], rax; ReturnLength
0x180036a2c  mov     edx, 3; TokenInformationClass
0x180036a31  mov     rcx, rsi; TokenHandle
0x180036a34  call    cs:__imp_GetTokenInformation
0x180036a3a  test    eax, eax
0x180036a3c  jnz     short loc_180036A65
0x180036a3e  mov     rcx, [rsp+48h]; this
0x180036a43  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180036a4a  mov     edx, 11Ah; void *
0x180036a4f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036a54  mov     edi, eax
0x180036a56  test    rbx, rbx
0x180036a59  jz      short loc_180036A77
0x180036a5b  mov     rcx, rbx; Block
0x180036a5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036a63  jmp     short loc_180036A77
0x180036a65  mov     rcx, [rdi]; Block
0x180036a68  mov     [rdi], rbx
0x180036a6b  test    rcx, rcx
0x180036a6e  jz      short loc_180036A75
0x180036a70  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036a75  xor     edi, edi
0x180036a77  mov     eax, edi
0x180036a79  jmp     short loc_180036A91
0x180036a7b  mov     rcx, [rsp+48h]; this
0x180036a80  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180036a87  mov     edx, 117h; void *
0x180036a8c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036a91  mov     rcx, [rsp+48h+var_10]
0x180036a96  xor     rcx, rsp; StackCookie
0x180036a99  call    __security_check_cookie
0x180036a9e  mov     rbx, [rsp+48h+arg_10]
0x180036aa3  mov     rsi, [rsp+48h+arg_18]
0x180036aa8  add     rsp, 40h
0x180036aac  pop     rdi
0x180036aad  retn
```
