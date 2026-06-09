# GetAppPackageSidFromToken(void *,ushort * *)

- ea: `0x180123d64`
- end: `0x180123e4f`
- name: `?GetAppPackageSidFromToken@@YAKPEAXPEAPEAG@Z`
- size: `235`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801243f8`

## callees

- `0x180123d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180123e37`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180123e37`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180123dd5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180123dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123e0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180123e0a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123da8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123e00`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123da8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180123e00`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180123e1f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180123e1f`

## pseudocode

```c
__int64 __fastcall GetAppPackageSidFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  DWORD LastError; // ebx
  DWORD v5; // ebx
  PSID *v6; // rsi
  DWORD TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF

  TokenInformationLength = 0;
  if ( !TokenHandle || !StringSid )
    return 87;
  *StringSid = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength)
    || (LastError = GetLastError(), LastError == 122) )
  {
    v5 = TokenInformationLength;
    if ( !TokenInformationLength )
      return 13;
    v6 = (PSID *)malloc(TokenInformationLength);
    if ( !v6 )
      return 14;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v6, v5, &TokenInformationLength) )
    {
      if ( !*v6 || ConvertSidToStringSidW(*v6, StringSid) )
      {
        LastError = 0;
        goto LABEL_15;
      }
      *StringSid = 0;
    }
    LastError = GetLastError();
LABEL_15:
    free(v6);
  }
  return LastError;
}

```

## disassembly

```asm
0x180123d64  push    rbx
0x180123d66  push    rbp
0x180123d67  push    rsi
0x180123d68  push    rdi
0x180123d69  sub     rsp, 38h
0x180123d6d  mov     [rsp+58h+TokenInformationLength], 0
0x180123d75  mov     rdi, rdx
0x180123d78  mov     rbp, rcx
0x180123d7b  test    rcx, rcx
0x180123d7e  jz      loc_180123E3F
0x180123d84  test    rdx, rdx
0x180123d87  jz      loc_180123E3F
0x180123d8d  xor     r9d, r9d; TokenInformationLength
0x180123d90  mov     qword ptr [rdx], 0
0x180123d97  lea     rax, [rsp+58h+TokenInformationLength]
0x180123d9c  xor     r8d, r8d; TokenInformation
0x180123d9f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180123da4  lea     edx, [r9+1Fh]; TokenInformationClass
0x180123da8  call    cs:__imp_GetTokenInformation
0x180123dae  test    eax, eax
0x180123db0  jnz     short loc_180123DC3
0x180123db2  call    cs:__imp_GetLastError
0x180123db8  mov     ebx, eax
0x180123dba  cmp     eax, 7Ah ; 'z'
0x180123dbd  jnz     loc_180123E44
0x180123dc3  mov     ebx, [rsp+58h+TokenInformationLength]
0x180123dc7  test    ebx, ebx
0x180123dc9  jnz     short loc_180123DD2
0x180123dcb  mov     ebx, 0Dh
0x180123dd0  jmp     short loc_180123E44
0x180123dd2  mov     rcx, rbx; Size
0x180123dd5  call    cs:__imp_malloc
0x180123ddb  mov     rsi, rax
0x180123dde  test    rax, rax
0x180123de1  jnz     short loc_180123DE8
0x180123de3  lea     ebx, [rax+0Eh]
0x180123de6  jmp     short loc_180123E44
0x180123de8  lea     rax, [rsp+58h+TokenInformationLength]
0x180123ded  mov     r9d, ebx; TokenInformationLength
0x180123df0  mov     r8, rsi; TokenInformation
0x180123df3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180123df8  mov     edx, 1Fh; TokenInformationClass
0x180123dfd  mov     rcx, rbp; TokenHandle
0x180123e00  call    cs:__imp_GetTokenInformation
0x180123e06  test    eax, eax
0x180123e08  jnz     short loc_180123E14
0x180123e0a  call    cs:__imp_GetLastError
0x180123e10  mov     ebx, eax
0x180123e12  jmp     short loc_180123E34
0x180123e14  mov     rcx, [rsi]; Sid
0x180123e17  test    rcx, rcx
0x180123e1a  jz      short loc_180123E32
0x180123e1c  mov     rdx, rdi; StringSid
0x180123e1f  call    cs:__imp_ConvertSidToStringSidW
0x180123e25  test    eax, eax
0x180123e27  jnz     short loc_180123E32
0x180123e29  mov     qword ptr [rdi], 0
0x180123e30  jmp     short loc_180123E0A
0x180123e32  xor     ebx, ebx
0x180123e34  mov     rcx, rsi; Block
0x180123e37  call    cs:__imp_free
0x180123e3d  jmp     short loc_180123E44
0x180123e3f  mov     ebx, 57h ; 'W'
0x180123e44  mov     eax, ebx
0x180123e46  add     rsp, 38h
0x180123e4a  pop     rdi
0x180123e4b  pop     rsi
0x180123e4c  pop     rbp
0x180123e4d  pop     rbx
0x180123e4e  retn
```
