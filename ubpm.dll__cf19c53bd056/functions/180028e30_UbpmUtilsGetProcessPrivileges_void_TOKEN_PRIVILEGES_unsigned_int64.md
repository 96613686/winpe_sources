# UbpmUtilsGetProcessPrivileges(void *,_TOKEN_PRIVILEGES * *,unsigned __int64 *)

- ea: `0x180028e30`
- end: `0x180028ee5`
- name: `?UbpmUtilsGetProcessPrivileges@@YAKPEAXPEAPEAU_TOKEN_PRIVILEGES@@PEA_K@Z`
- size: `181`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, struct _TOKEN_PRIVILEGES **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028cf8`

## callees

- `0x18000f9a0`
- `0x180019d90`
- `0x180028e30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028e64`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028e99`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028e64`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028e99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ec5`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetProcessPrivileges(
        HANDLE TokenHandle,
        struct _TOKEN_PRIVILEGES **a2,
        unsigned __int64 *a3)
{
  struct _TOKEN_PRIVILEGES *v5; // rbx
  DWORD LastError; // edi
  DWORD TokenInformationLength; // [rsp+50h] [rbp+18h] BYREF
  int v9; // [rsp+54h] [rbp+1Ch]

  v9 = HIDWORD(a3);
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
  UBPM_MIDL_user_free(v5);
  return LastError;
}

```

## disassembly

```asm
0x180028e30  mov     rax, rsp
0x180028e33  mov     [rax+8], rbx
0x180028e37  mov     [rax+10h], rsi
0x180028e3b  mov     [rax+18h], r8
0x180028e3f  push    rdi
0x180028e40  sub     rsp, 30h
0x180028e44  xor     r9d, r9d; TokenInformationLength
0x180028e47  mov     dword ptr [rax+18h], 0
0x180028e4e  mov     rdi, rdx
0x180028e51  lea     rax, [rax+18h]
0x180028e55  xor     r8d, r8d; TokenInformation
0x180028e58  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180028e5d  mov     rsi, rcx
0x180028e60  lea     edx, [r9+3]; TokenInformationClass
0x180028e64  call    cs:__imp_GetTokenInformation
0x180028e6a  test    eax, eax
0x180028e6c  jz      short loc_180028EC5
0x180028e6e  mov     ecx, [rsp+38h+TokenInformationLength]; Size
0x180028e72  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180028e77  mov     rbx, rax
0x180028e7a  test    rax, rax
0x180028e7d  jz      short loc_180028EA3
0x180028e7f  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180028e84  lea     rax, [rsp+38h+TokenInformationLength]
0x180028e89  mov     r8, rbx; TokenInformation
0x180028e8c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180028e91  mov     edx, 3; TokenInformationClass
0x180028e96  mov     rcx, rsi; TokenHandle
0x180028e99  call    cs:__imp_GetTokenInformation
0x180028e9f  test    eax, eax
0x180028ea1  jnz     short loc_180028ED7
0x180028ea3  call    cs:__imp_GetLastError
0x180028ea9  mov     edi, eax
0x180028eab  mov     rcx, rbx
0x180028eae  call    UBPM_MIDL_user_free
0x180028eb3  mov     rbx, [rsp+38h+arg_0]
0x180028eb8  mov     eax, edi
0x180028eba  mov     rsi, [rsp+38h+arg_8]
0x180028ebf  add     rsp, 30h
0x180028ec3  pop     rdi
0x180028ec4  retn
0x180028ec5  call    cs:__imp_GetLastError
0x180028ecb  cmp     eax, 7Ah ; 'z'
0x180028ece  jz      short loc_180028E6E
0x180028ed0  xor     ebx, ebx
0x180028ed2  lea     edi, [rbx+0Dh]
0x180028ed5  jmp     short loc_180028EAB
0x180028ed7  test    rdi, rdi
0x180028eda  jz      short loc_180028EE1
0x180028edc  mov     [rdi], rbx
0x180028edf  xor     ebx, ebx
0x180028ee1  xor     edi, edi
0x180028ee3  jmp     short loc_180028EAB
```
