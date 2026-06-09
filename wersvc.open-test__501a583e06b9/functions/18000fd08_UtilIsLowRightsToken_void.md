# UtilIsLowRightsToken(void *)

- ea: `0x18000fd08`
- end: `0x18000fe0a`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800106f4`
- `0x180027460`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x18000fd08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fdaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fd5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fda0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fd5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000fda0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000fdce`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000fdce`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000fdde`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000fdde`

## pseudocode

```c
signed int __fastcall UtilIsLowRightsToken(HANDLE TokenHandle)
{
  signed int LastError; // eax
  bool v3; // zf
  signed int result; // eax
  PUCHAR SidSubAuthorityCount; // rax
  int TokenInformation; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-84h] BYREF
  DWORD v8; // [rsp+38h] [rbp-80h] BYREF
  PSID pSid[12]; // [rsp+40h] [rbp-78h] BYREF

  memset_0(pSid, 0, 0x58u);
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v3 = LastError == 0;
    if ( LastError > 0 )
      v3 = 0;
    if ( !v3 )
      goto LABEL_5;
    return 0;
  }
  if ( TokenInformation )
    return 0;
LABEL_5:
  v8 = 84;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, pSid, 0x54u, &v8) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
    return *GetSidSubAuthority(pSid[0], (unsigned int)*SidSubAuthorityCount - 1) >= 0x2000;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000fd08  push    rbx
0x18000fd0a  sub     rsp, 0B0h
0x18000fd11  mov     rax, cs:__security_cookie
0x18000fd18  xor     rax, rsp
0x18000fd1b  mov     [rsp+0B8h+var_18], rax
0x18000fd23  xor     edx, edx; Val
0x18000fd25  mov     rbx, rcx
0x18000fd28  lea     rcx, [rsp+0B8h+pSid]; void *
0x18000fd2d  lea     r8d, [rdx+58h]; Size
0x18000fd31  call    memset_0
0x18000fd36  mov     r9d, 4; TokenInformationLength
0x18000fd3c  mov     [rsp+0B8h+TokenInformation], 0
0x18000fd44  lea     rax, [rsp+0B8h+var_84]
0x18000fd49  mov     [rsp+0B8h+var_84], r9d
0x18000fd4e  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18000fd53  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18000fd58  mov     rcx, rbx; TokenHandle
0x18000fd5b  lea     edx, [r9+19h]; TokenInformationClass
0x18000fd5f  call    cs:__imp_GetTokenInformation
0x18000fd65  test    eax, eax
0x18000fd67  jnz     short loc_18000FDBE
0x18000fd69  call    cs:__imp_GetLastError
0x18000fd6f  test    eax, eax
0x18000fd71  jle     short loc_18000FD7D
0x18000fd73  movzx   eax, ax
0x18000fd76  or      eax, 80070000h
0x18000fd7b  test    eax, eax
0x18000fd7d  jz      short loc_18000FDC5
0x18000fd7f  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000fd85  lea     rax, [rsp+0B8h+var_80]
0x18000fd8a  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x18000fd8f  mov     [rsp+0B8h+var_80], r9d
0x18000fd94  mov     rcx, rbx; TokenHandle
0x18000fd97  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18000fd9c  lea     edx, [r9-3Bh]; TokenInformationClass
0x18000fda0  call    cs:__imp_GetTokenInformation
0x18000fda6  test    eax, eax
0x18000fda8  jnz     short loc_18000FDC9
0x18000fdaa  call    cs:__imp_GetLastError
0x18000fdb0  test    eax, eax
0x18000fdb2  jle     short loc_18000FDF1
0x18000fdb4  movzx   eax, ax
0x18000fdb7  or      eax, 80070000h
0x18000fdbc  jmp     short loc_18000FDF1
0x18000fdbe  cmp     [rsp+0B8h+TokenInformation], 0
0x18000fdc3  jz      short loc_18000FD7F
0x18000fdc5  xor     eax, eax
0x18000fdc7  jmp     short loc_18000FDF1
0x18000fdc9  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18000fdce  call    cs:__imp_GetSidSubAuthorityCount
0x18000fdd4  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18000fdd9  movzx   edx, byte ptr [rax]
0x18000fddc  dec     edx; nSubAuthority
0x18000fdde  call    cs:__imp_GetSidSubAuthority
0x18000fde4  xor     ecx, ecx
0x18000fde6  cmp     dword ptr [rax], 2000h
0x18000fdec  setnb   cl
0x18000fdef  mov     eax, ecx
0x18000fdf1  mov     rcx, [rsp+0B8h+var_18]
0x18000fdf9  xor     rcx, rsp; StackCookie
0x18000fdfc  call    __security_check_cookie
0x18000fe01  add     rsp, 0B0h
0x18000fe08  pop     rbx
0x18000fe09  retn
```
