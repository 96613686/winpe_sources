# UtilIsLowRightsToken(void *)

- ea: `0x180012610`
- end: `0x180012712`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012598`

## callees

- `0x180012610`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800126d6`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x1800126d6`
- `ADVAPI32!GetSidSubAuthority` at `0x1800126e6`
- `ADVAPI32!GetSidSubAuthority` at `0x1800126e6`
- `ADVAPI32!GetTokenInformation` at `0x180012667`
- `ADVAPI32!GetTokenInformation` at `0x1800126a8`
- `ADVAPI32!GetTokenInformation` at `0x180012667`
- `ADVAPI32!GetTokenInformation` at `0x1800126a8`
- `KERNEL32!GetLastError` at `0x180012671`
- `KERNEL32!GetLastError` at `0x1800126b2`
- `KERNEL32!GetLastError` at `0x180012671`
- `KERNEL32!GetLastError` at `0x1800126b2`

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
0x180012610  push    rbx
0x180012612  sub     rsp, 0B0h
0x180012619  mov     rax, cs:__security_cookie
0x180012620  xor     rax, rsp
0x180012623  mov     [rsp+0B8h+var_18], rax
0x18001262b  xor     edx, edx; Val
0x18001262d  mov     rbx, rcx
0x180012630  lea     rcx, [rsp+0B8h+pSid]; void *
0x180012635  lea     r8d, [rdx+58h]; Size
0x180012639  call    memset_0
0x18001263e  mov     r9d, 4; TokenInformationLength
0x180012644  mov     [rsp+0B8h+TokenInformation], 0
0x18001264c  lea     rax, [rsp+0B8h+var_84]
0x180012651  mov     [rsp+0B8h+var_84], r9d
0x180012656  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18001265b  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180012660  mov     rcx, rbx; TokenHandle
0x180012663  lea     edx, [r9+19h]; TokenInformationClass
0x180012667  call    cs:__imp_GetTokenInformation
0x18001266d  test    eax, eax
0x18001266f  jnz     short loc_1800126C6
0x180012671  call    cs:__imp_GetLastError
0x180012677  test    eax, eax
0x180012679  jle     short loc_180012685
0x18001267b  movzx   eax, ax
0x18001267e  or      eax, 80070000h
0x180012683  test    eax, eax
0x180012685  jz      short loc_1800126CD
0x180012687  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18001268d  lea     rax, [rsp+0B8h+var_80]
0x180012692  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x180012697  mov     [rsp+0B8h+var_80], r9d
0x18001269c  mov     rcx, rbx; TokenHandle
0x18001269f  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800126a4  lea     edx, [r9-3Bh]; TokenInformationClass
0x1800126a8  call    cs:__imp_GetTokenInformation
0x1800126ae  test    eax, eax
0x1800126b0  jnz     short loc_1800126D1
0x1800126b2  call    cs:__imp_GetLastError
0x1800126b8  test    eax, eax
0x1800126ba  jle     short loc_1800126F9
0x1800126bc  movzx   eax, ax
0x1800126bf  or      eax, 80070000h
0x1800126c4  jmp     short loc_1800126F9
0x1800126c6  cmp     [rsp+0B8h+TokenInformation], 0
0x1800126cb  jz      short loc_180012687
0x1800126cd  xor     eax, eax
0x1800126cf  jmp     short loc_1800126F9
0x1800126d1  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1800126d6  call    cs:__imp_GetSidSubAuthorityCount
0x1800126dc  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1800126e1  movzx   edx, byte ptr [rax]
0x1800126e4  dec     edx; nSubAuthority
0x1800126e6  call    cs:__imp_GetSidSubAuthority
0x1800126ec  xor     ecx, ecx
0x1800126ee  cmp     dword ptr [rax], 2000h
0x1800126f4  setnb   cl
0x1800126f7  mov     eax, ecx
0x1800126f9  mov     rcx, [rsp+0B8h+var_18]
0x180012701  xor     rcx, rsp; StackCookie
0x180012704  call    __security_check_cookie
0x180012709  add     rsp, 0B0h
0x180012710  pop     rbx
0x180012711  retn
```
