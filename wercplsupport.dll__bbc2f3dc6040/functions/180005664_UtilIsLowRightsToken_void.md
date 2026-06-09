# UtilIsLowRightsToken(void *)

- ea: `0x180005664`
- end: `0x180005766`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005e04`

## callees

- `0x180005664`
- `0x18001218a`
- `0x1800121b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056fc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056bb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800056fc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000572a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000572a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000573a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000573a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005706`

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
0x180005664  push    rbx
0x180005666  sub     rsp, 0B0h
0x18000566d  mov     rax, cs:__security_cookie
0x180005674  xor     rax, rsp
0x180005677  mov     [rsp+0B8h+var_18], rax
0x18000567f  xor     edx, edx; Val
0x180005681  mov     rbx, rcx
0x180005684  lea     rcx, [rsp+0B8h+pSid]; void *
0x180005689  lea     r8d, [rdx+58h]; Size
0x18000568d  call    memset_0
0x180005692  mov     r9d, 4; TokenInformationLength
0x180005698  mov     [rsp+0B8h+TokenInformation], 0
0x1800056a0  lea     rax, [rsp+0B8h+var_84]
0x1800056a5  mov     [rsp+0B8h+var_84], r9d
0x1800056aa  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800056af  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800056b4  mov     rcx, rbx; TokenHandle
0x1800056b7  lea     edx, [r9+19h]; TokenInformationClass
0x1800056bb  call    cs:__imp_GetTokenInformation
0x1800056c1  test    eax, eax
0x1800056c3  jnz     short loc_18000571A
0x1800056c5  call    cs:__imp_GetLastError
0x1800056cb  test    eax, eax
0x1800056cd  jle     short loc_1800056D9
0x1800056cf  movzx   eax, ax
0x1800056d2  or      eax, 80070000h
0x1800056d7  test    eax, eax
0x1800056d9  jz      short loc_180005721
0x1800056db  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800056e1  lea     rax, [rsp+0B8h+var_80]
0x1800056e6  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x1800056eb  mov     [rsp+0B8h+var_80], r9d
0x1800056f0  mov     rcx, rbx; TokenHandle
0x1800056f3  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800056f8  lea     edx, [r9-3Bh]; TokenInformationClass
0x1800056fc  call    cs:__imp_GetTokenInformation
0x180005702  test    eax, eax
0x180005704  jnz     short loc_180005725
0x180005706  call    cs:__imp_GetLastError
0x18000570c  test    eax, eax
0x18000570e  jle     short loc_18000574D
0x180005710  movzx   eax, ax
0x180005713  or      eax, 80070000h
0x180005718  jmp     short loc_18000574D
0x18000571a  cmp     [rsp+0B8h+TokenInformation], 0
0x18000571f  jz      short loc_1800056DB
0x180005721  xor     eax, eax
0x180005723  jmp     short loc_18000574D
0x180005725  mov     rcx, [rsp+0B8h+pSid]; pSid
0x18000572a  call    cs:__imp_GetSidSubAuthorityCount
0x180005730  mov     rcx, [rsp+0B8h+pSid]; pSid
0x180005735  movzx   edx, byte ptr [rax]
0x180005738  dec     edx; nSubAuthority
0x18000573a  call    cs:__imp_GetSidSubAuthority
0x180005740  xor     ecx, ecx
0x180005742  cmp     dword ptr [rax], 2000h
0x180005748  setnb   cl
0x18000574b  mov     eax, ecx
0x18000574d  mov     rcx, [rsp+0B8h+var_18]
0x180005755  xor     rcx, rsp; StackCookie
0x180005758  call    __security_check_cookie
0x18000575d  add     rsp, 0B0h
0x180005764  pop     rbx
0x180005765  retn
```
