# UtilIsVirtualAccountToken(void *)

- ea: `0x180029bc0`
- end: `0x180029ca5`
- name: `?UtilIsVirtualAccountToken@@YAJPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027460`

## callees

- `0x1800029d0`
- `0x180029bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c28`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029c1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180029c1e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029c46`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180029c46`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180029c6f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180029c6f`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180029c53`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180029c53`

## pseudocode

```c
__int64 __fastcall UtilIsVirtualAccountToken(void *a1)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  PSID v3; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  DWORD ReturnLength; // [rsp+38h] [rbp-21h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-19h] BYREF

  ReturnLength = 0;
  if ( a1 )
  {
    v1 = 1;
    if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
    {
      v3 = TokenInformation[0];
      if ( *GetSidSubAuthorityCount(TokenInformation[0]) )
      {
        SidIdentifierAuthority = GetSidIdentifierAuthority(v3);
        if ( !*(_DWORD *)SidIdentifierAuthority->Value && *(_WORD *)&SidIdentifierAuthority->Value[4] == 1280 )
          return *GetSidSubAuthority(v3, 0) - 80 > 0x1F;
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x180029bc0  mov     [rsp-8+arg_8], rbx
0x180029bc5  mov     [rsp-8+arg_10], rdi
0x180029bca  push    rbp
0x180029bcb  lea     rbp, [rsp-57h]
0x180029bd0  sub     rsp, 0B0h
0x180029bd7  mov     rax, cs:__security_cookie
0x180029bde  xor     rax, rsp
0x180029be1  mov     [rbp+57h+var_10], rax
0x180029be5  mov     [rbp+57h+var_78], 0
0x180029bec  mov     [rbp+57h+var_80], 0
0x180029bf3  mov     [rbp+57h+var_7C], 500h
0x180029bf9  test    rcx, rcx
0x180029bfc  jnz     short loc_180029C05
0x180029bfe  mov     ebx, 80070057h
0x180029c03  jmp     short loc_180029C82
0x180029c05  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180029c0b  lea     rax, [rbp+57h+var_78]
0x180029c0f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180029c13  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180029c18  lea     ebx, [r9-53h]
0x180029c1c  mov     edx, ebx; TokenInformationClass
0x180029c1e  call    cs:__imp_GetTokenInformation
0x180029c24  test    eax, eax
0x180029c26  jnz     short loc_180029C3F
0x180029c28  call    cs:__imp_GetLastError
0x180029c2e  mov     ebx, eax
0x180029c30  test    eax, eax
0x180029c32  jle     short loc_180029C82
0x180029c34  movzx   ebx, ax
0x180029c37  or      ebx, 80070000h
0x180029c3d  jmp     short loc_180029C82
0x180029c3f  mov     rdi, [rbp+57h+TokenInformation]
0x180029c43  mov     rcx, rdi; pSid
0x180029c46  call    cs:__imp_GetSidSubAuthorityCount
0x180029c4c  cmp     [rax], bl
0x180029c4e  jb      short loc_180029C82
0x180029c50  mov     rcx, rdi; pSid
0x180029c53  call    cs:__imp_GetSidIdentifierAuthority
0x180029c59  mov     edx, [rax]
0x180029c5b  cmp     edx, [rbp+57h+var_80]
0x180029c5e  jnz     short loc_180029C82
0x180029c60  movzx   eax, word ptr [rax+4]
0x180029c64  cmp     ax, [rbp+57h+var_7C]
0x180029c68  jnz     short loc_180029C82
0x180029c6a  xor     edx, edx; nSubAuthority
0x180029c6c  mov     rcx, rdi; pSid
0x180029c6f  call    cs:__imp_GetSidSubAuthority
0x180029c75  xor     ecx, ecx
0x180029c77  mov     edx, [rax]
0x180029c79  sub     edx, 50h ; 'P'
0x180029c7c  cmp     edx, 1Fh
0x180029c7f  cmovbe  ebx, ecx
0x180029c82  mov     eax, ebx
0x180029c84  mov     rcx, [rbp+57h+var_10]
0x180029c88  xor     rcx, rsp; StackCookie
0x180029c8b  call    __security_check_cookie
0x180029c90  lea     r11, [rsp+0B0h+var_s0]
0x180029c98  mov     rbx, [r11+18h]
0x180029c9c  mov     rdi, [r11+20h]
0x180029ca0  mov     rsp, r11
0x180029ca3  pop     rbp
0x180029ca4  retn
```
