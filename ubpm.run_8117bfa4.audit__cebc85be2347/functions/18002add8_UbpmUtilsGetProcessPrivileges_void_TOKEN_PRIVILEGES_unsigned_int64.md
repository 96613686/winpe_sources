# UbpmUtilsGetProcessPrivileges(void *,_TOKEN_PRIVILEGES * *,unsigned __int64 *)

- ea: `0x18002add8`
- end: `0x18002aea6`
- name: `?UbpmUtilsGetProcessPrivileges@@YAKPEAXPEAPEAU_TOKEN_PRIVILEGES@@PEA_K@Z`
- size: `206`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_PRIVILEGES **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ac90`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18002add8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ae0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ae47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ae0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002ae47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae80`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetProcessPrivileges(
        HANDLE TokenHandle,
        struct _TOKEN_PRIVILEGES **a2,
        unsigned __int64 *a3)
{
  struct _TOKEN_PRIVILEGES *v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD LastError; // edi
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  int v12; // [rsp+54h] [rbp+1Ch]

  v12 = HIDWORD(a3);
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) || GetLastError() == 122 )
  {
    v5 = (struct _TOKEN_PRIVILEGES *)UbpmAlloc(TokenInformationLength);
    if ( v5 && GetTokenInformation(TokenHandle, TokenPrivileges, v5, TokenInformationLength, &TokenInformationLength) )
    {
      if ( a2 )
      {
        *a2 = v5;
        v5 = 0;
      }
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    v5 = 0;
    LastError = 13;
  }
  UBPM_MIDL_user_free(v5, v6, v7, v8);
  return LastError;
}

```

## disassembly

```asm
0x18002add8  mov     rax, rsp
0x18002addb  mov     [rax+8], rbx
0x18002addf  mov     [rax+10h], rsi
0x18002ade3  mov     [rax+18h], r8
0x18002ade7  push    rdi
0x18002ade8  sub     rsp, 30h
0x18002adec  xor     r9d, r9d; TokenInformationLength
0x18002adef  mov     dword ptr [rax+18h], 0
0x18002adf6  mov     rdi, rdx
0x18002adf9  lea     rax, [rax+18h]
0x18002adfd  xor     r8d, r8d; TokenInformation
0x18002ae00  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002ae05  mov     rsi, rcx
0x18002ae08  lea     edx, [r9+3]; TokenInformationClass
0x18002ae0c  call    cs:__imp_GetTokenInformation
0x18002ae13  nop     dword ptr [rax+rax+00h]
0x18002ae18  test    eax, eax
0x18002ae1a  jz      short loc_18002AE80
0x18002ae1c  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x18002ae20  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002ae25  mov     rbx, rax
0x18002ae28  test    rax, rax
0x18002ae2b  jz      short loc_18002AE57
0x18002ae2d  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002ae32  lea     rax, [rsp+38h+TokenInformationLength]
0x18002ae37  mov     r8, rbx; TokenInformation
0x18002ae3a  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002ae3f  mov     edx, 3; TokenInformationClass
0x18002ae44  mov     rcx, rsi; TokenHandle
0x18002ae47  call    cs:__imp_GetTokenInformation
0x18002ae4e  nop     dword ptr [rax+rax+00h]
0x18002ae53  test    eax, eax
0x18002ae55  jnz     short loc_18002AE98
0x18002ae57  call    cs:__imp_GetLastError
0x18002ae5e  nop     dword ptr [rax+rax+00h]
0x18002ae63  mov     edi, eax
0x18002ae65  mov     rcx, rbx
0x18002ae68  call    UBPM_MIDL_user_free
0x18002ae6d  mov     rbx, [rsp+38h+arg_0]
0x18002ae72  mov     eax, edi
0x18002ae74  mov     rsi, [rsp+38h+arg_8]
0x18002ae79  add     rsp, 30h
0x18002ae7d  pop     rdi
0x18002ae7e  retn
0x18002ae80  call    cs:__imp_GetLastError
0x18002ae87  nop     dword ptr [rax+rax+00h]
0x18002ae8c  cmp     eax, 7Ah ; 'z'
0x18002ae8f  jz      short loc_18002AE1C
0x18002ae91  xor     ebx, ebx
0x18002ae93  lea     edi, [rbx+0Dh]
0x18002ae96  jmp     short loc_18002AE65
0x18002ae98  test    rdi, rdi
0x18002ae9b  jz      short loc_18002AEA2
0x18002ae9d  mov     [rdi], rbx
0x18002aea0  xor     ebx, ebx
0x18002aea2  xor     edi, edi
0x18002aea4  jmp     short loc_18002AE65
```
