# UtilIsLowRightsToken(void *)

- ea: `0x14000bd00`
- end: `0x14000be02`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c798`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x14000bd00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bda2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bd61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bda2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x14000bdd6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x14000bdd6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x14000bdc6`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x14000bdc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000bd57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000bd98`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000bd57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14000bd98`

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
0x14000bd00  push    rbx
0x14000bd02  sub     rsp, 0B0h
0x14000bd09  mov     rax, cs:__security_cookie
0x14000bd10  xor     rax, rsp
0x14000bd13  mov     [rsp+0B8h+var_18], rax
0x14000bd1b  xor     edx, edx; Val
0x14000bd1d  mov     rbx, rcx
0x14000bd20  lea     rcx, [rsp+0B8h+pSid]; void *
0x14000bd25  lea     r8d, [rdx+58h]; Size
0x14000bd29  call    memset_0
0x14000bd2e  mov     r9d, 4; TokenInformationLength
0x14000bd34  mov     [rsp+0B8h+TokenInformation], 0
0x14000bd3c  lea     rax, [rsp+0B8h+var_84]
0x14000bd41  mov     [rsp+0B8h+var_84], r9d
0x14000bd46  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x14000bd4b  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x14000bd50  mov     rcx, rbx; TokenHandle
0x14000bd53  lea     edx, [r9+19h]; TokenInformationClass
0x14000bd57  call    cs:__imp_GetTokenInformation
0x14000bd5d  test    eax, eax
0x14000bd5f  jnz     short loc_14000BDB6
0x14000bd61  call    cs:__imp_GetLastError
0x14000bd67  test    eax, eax
0x14000bd69  jle     short loc_14000BD75
0x14000bd6b  movzx   eax, ax
0x14000bd6e  or      eax, 80070000h
0x14000bd73  test    eax, eax
0x14000bd75  jz      short loc_14000BDBD
0x14000bd77  mov     r9d, 54h ; 'T'; TokenInformationLength
0x14000bd7d  lea     rax, [rsp+0B8h+var_80]
0x14000bd82  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x14000bd87  mov     [rsp+0B8h+var_80], r9d
0x14000bd8c  mov     rcx, rbx; TokenHandle
0x14000bd8f  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x14000bd94  lea     edx, [r9-3Bh]; TokenInformationClass
0x14000bd98  call    cs:__imp_GetTokenInformation
0x14000bd9e  test    eax, eax
0x14000bda0  jnz     short loc_14000BDC1
0x14000bda2  call    cs:__imp_GetLastError
0x14000bda8  test    eax, eax
0x14000bdaa  jle     short loc_14000BDE9
0x14000bdac  movzx   eax, ax
0x14000bdaf  or      eax, 80070000h
0x14000bdb4  jmp     short loc_14000BDE9
0x14000bdb6  cmp     [rsp+0B8h+TokenInformation], 0
0x14000bdbb  jz      short loc_14000BD77
0x14000bdbd  xor     eax, eax
0x14000bdbf  jmp     short loc_14000BDE9
0x14000bdc1  mov     rcx, [rsp+0B8h+pSid]; pSid
0x14000bdc6  call    cs:__imp_GetSidSubAuthorityCount
0x14000bdcc  mov     rcx, [rsp+0B8h+pSid]; pSid
0x14000bdd1  movzx   edx, byte ptr [rax]
0x14000bdd4  dec     edx; nSubAuthority
0x14000bdd6  call    cs:__imp_GetSidSubAuthority
0x14000bddc  xor     ecx, ecx
0x14000bdde  cmp     dword ptr [rax], 2000h
0x14000bde4  setnb   cl
0x14000bde7  mov     eax, ecx
0x14000bde9  mov     rcx, [rsp+0B8h+var_18]
0x14000bdf1  xor     rcx, rsp; StackCookie
0x14000bdf4  call    __security_check_cookie
0x14000bdf9  add     rsp, 0B0h
0x14000be00  pop     rbx
0x14000be01  retn
```
