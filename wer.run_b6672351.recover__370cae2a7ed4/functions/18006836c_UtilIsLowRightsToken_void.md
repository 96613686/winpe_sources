# UtilIsLowRightsToken(void *)

- ea: `0x18006836c`
- end: `0x180068493`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800682e8`

## callees

- `0x180053300`
- `0x180053d3c`
- `0x18006836c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800683d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800683d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068420`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800683c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068410`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800683c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068410`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180068460`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180068460`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006844a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006844a`

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
0x18006836c  push    rbx
0x18006836e  sub     rsp, 0B0h
0x180068375  mov     rax, cs:__security_cookie
0x18006837c  xor     rax, rsp
0x18006837f  mov     [rsp+0B8h+var_18], rax
0x180068387  xor     edx, edx; Val
0x180068389  mov     rbx, rcx
0x18006838c  lea     rcx, [rsp+0B8h+pSid]; void *
0x180068391  lea     r8d, [rdx+58h]; Size
0x180068395  call    memset_0
0x18006839a  mov     r9d, 4; TokenInformationLength
0x1800683a0  mov     [rsp+0B8h+TokenInformation], 0
0x1800683a8  lea     rax, [rsp+0B8h+var_84]
0x1800683ad  mov     [rsp+0B8h+var_84], r9d
0x1800683b2  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800683b7  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800683bc  mov     rcx, rbx; TokenHandle
0x1800683bf  lea     edx, [r9+19h]; TokenInformationClass
0x1800683c3  call    cs:__imp_GetTokenInformation
0x1800683ca  nop     dword ptr [rax+rax+00h]
0x1800683cf  test    eax, eax
0x1800683d1  jnz     short loc_18006843A
0x1800683d3  call    cs:__imp_GetLastError
0x1800683da  nop     dword ptr [rax+rax+00h]
0x1800683df  test    eax, eax
0x1800683e1  jle     short loc_1800683ED
0x1800683e3  movzx   eax, ax
0x1800683e6  or      eax, 80070000h
0x1800683eb  test    eax, eax
0x1800683ed  jz      short loc_180068441
0x1800683ef  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800683f5  lea     rax, [rsp+0B8h+var_80]
0x1800683fa  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x1800683ff  mov     [rsp+0B8h+var_80], r9d
0x180068404  mov     rcx, rbx; TokenHandle
0x180068407  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18006840c  lea     edx, [r9-3Bh]; TokenInformationClass
0x180068410  call    cs:__imp_GetTokenInformation
0x180068417  nop     dword ptr [rax+rax+00h]
0x18006841c  test    eax, eax
0x18006841e  jnz     short loc_180068445
0x180068420  call    cs:__imp_GetLastError
0x180068427  nop     dword ptr [rax+rax+00h]
0x18006842c  test    eax, eax
0x18006842e  jle     short loc_180068479
0x180068430  movzx   eax, ax
0x180068433  or      eax, 80070000h
0x180068438  jmp     short loc_180068479
0x18006843a  cmp     [rsp+0B8h+TokenInformation], 0
0x18006843f  jz      short loc_1800683EF
0x180068441  xor     eax, eax
0x180068443  jmp     short loc_180068479
0x180068445  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18006844a  call    cs:__imp_GetSidSubAuthorityCount
0x180068451  nop     dword ptr [rax+rax+00h]
0x180068456  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18006845b  movzx   edx, byte ptr [rax]
0x18006845e  dec     edx; nSubAuthority
0x180068460  call    cs:__imp_GetSidSubAuthority
0x180068467  nop     dword ptr [rax+rax+00h]
0x18006846c  xor     ecx, ecx
0x18006846e  cmp     dword ptr [rax], 2000h
0x180068474  setnb   cl
0x180068477  mov     eax, ecx
0x180068479  mov     rcx, [rsp+0B8h+var_18]
0x180068481  xor     rcx, rsp; StackCookie
0x180068484  call    __security_check_cookie
0x180068489  add     rsp, 0B0h
0x180068490  pop     rbx
0x180068491  retn
```
