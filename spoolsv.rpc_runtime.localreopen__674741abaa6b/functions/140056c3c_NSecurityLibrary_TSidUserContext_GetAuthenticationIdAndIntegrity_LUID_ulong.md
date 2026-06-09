# NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)

- ea: `0x140056c3c`
- end: `0x140056d86`
- name: `?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z`
- size: `330`
- prototype: `__int64 __fastcall(NSecurityLibrary::TSidUserContext *__hidden this, struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004b6c4`

## callees

- `0x1400087c8`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140056c3c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140056cdd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140056d25`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140056cdd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140056d25`
- `ADVAPI32!GetSidSubAuthority` at `0x140056d59`
- `ADVAPI32!GetSidSubAuthority` at `0x140056d59`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140056d42`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140056d42`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
        NSecurityLibrary::TSidUserContext *this,
        struct _LUID *a2,
        unsigned int *a3)
{
  int LastErrorAsHResult; // ebx
  void *v7; // rcx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-71h] BYREF
  __int128 v12; // [rsp+3Ch] [rbp-6Dh]
  __int128 v13; // [rsp+4Ch] [rbp-5Dh]
  __int128 v14; // [rsp+5Ch] [rbp-4Dh]
  int v15; // [rsp+6Ch] [rbp-3Dh]
  PSID pSid[12]; // [rsp+70h] [rbp-39h] BYREF

  TokenInformation = 0;
  v15 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  memset_0(pSid, 0, 0x58u);
  LastErrorAsHResult = *((_DWORD *)this + 14);
  ReturnLength = 56;
  if ( LastErrorAsHResult >= 0 )
  {
    if ( a2 && a3 )
    {
      *a2 = 0;
      *a3 = 0;
      if ( GetTokenInformation(*((HANDLE *)this + 2), TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
      {
        LastErrorAsHResult = 0;
        *a2 = *(struct _LUID *)((char *)&v12 + 4);
      }
      else
      {
        LastErrorAsHResult = GetLastErrorAsHResult();
        if ( LastErrorAsHResult < 0 )
          return (unsigned int)LastErrorAsHResult;
      }
      v7 = (void *)*((_QWORD *)this + 2);
      ReturnLength = 88;
      if ( GetTokenInformation(v7, TokenIntegrityLevel, pSid, 0x58u, &ReturnLength) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
        *a3 = *GetSidSubAuthority(pSid[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
      }
      else
      {
        return (unsigned int)GetLastErrorAsHResult();
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140056c3c  push    rbp
0x140056c3e  push    rbx
0x140056c3f  push    rsi
0x140056c40  push    rdi
0x140056c41  push    r14
0x140056c43  lea     rbp, [rsp-37h]
0x140056c48  sub     rsp, 0E0h
0x140056c4f  mov     rax, cs:__security_cookie
0x140056c56  xor     rax, rsp
0x140056c59  mov     [rbp+57h+var_30], rax
0x140056c5d  xorps   xmm0, xmm0
0x140056c60  mov     [rbp+57h+TokenInformation], 0
0x140056c67  xor     eax, eax
0x140056c69  mov     rsi, r8
0x140056c6c  mov     rdi, rdx
0x140056c6f  mov     [rbp+57h+var_94], eax
0x140056c72  mov     r14, rcx
0x140056c75  xor     edx, edx; Val
0x140056c77  lea     rcx, [rbp+57h+pSid]; void *
0x140056c7b  lea     r8d, [rax+58h]; Size
0x140056c7f  movups  [rbp+57h+var_C4], xmm0
0x140056c83  movups  [rbp+57h+var_B4], xmm0
0x140056c87  movups  [rbp+57h+var_A4], xmm0
0x140056c8b  call    memset_0
0x140056c90  mov     ebx, [r14+38h]
0x140056c94  mov     r9d, 38h ; '8'; TokenInformationLength
0x140056c9a  mov     [rbp+57h+var_D0], r9d
0x140056c9e  test    ebx, ebx
0x140056ca0  js      loc_140056D69
0x140056ca6  test    rdi, rdi
0x140056ca9  jz      short loc_140056CB0
0x140056cab  test    rsi, rsi
0x140056cae  jnz     short loc_140056CBA
0x140056cb0  mov     ebx, 80070057h
0x140056cb5  jmp     loc_140056D69
0x140056cba  mov     qword ptr [rdi], 0
0x140056cc1  lea     rax, [rbp+57h+var_D0]
0x140056cc5  mov     dword ptr [rsi], 0
0x140056ccb  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140056ccf  mov     rcx, [r14+10h]; TokenHandle
0x140056cd3  mov     edx, 0Ah; TokenInformationClass
0x140056cd8  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140056cdd  call    cs:__imp_GetTokenInformation
0x140056ce4  nop     dword ptr [rax+rax+00h]
0x140056ce9  test    eax, eax
0x140056ceb  jnz     short loc_140056CFA
0x140056ced  call    GetLastErrorAsHResult
0x140056cf2  mov     ebx, eax
0x140056cf4  test    eax, eax
0x140056cf6  js      short loc_140056D69
0x140056cf8  jmp     short loc_140056D03
0x140056cfa  mov     rax, qword ptr [rbp+57h+var_C4+4]
0x140056cfe  xor     ebx, ebx
0x140056d00  mov     [rdi], rax
0x140056d03  mov     rcx, [r14+10h]; TokenHandle
0x140056d07  lea     rax, [rbp+57h+var_D0]
0x140056d0b  mov     r9d, 58h ; 'X'; TokenInformationLength
0x140056d11  mov     [rbp+57h+var_D0], 58h ; 'X'
0x140056d18  lea     r8, [rbp+57h+pSid]; TokenInformation
0x140056d1c  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140056d21  lea     edx, [r9-3Fh]; TokenInformationClass
0x140056d25  call    cs:__imp_GetTokenInformation
0x140056d2c  nop     dword ptr [rax+rax+00h]
0x140056d31  test    eax, eax
0x140056d33  jnz     short loc_140056D3E
0x140056d35  call    GetLastErrorAsHResult
0x140056d3a  mov     ebx, eax
0x140056d3c  jmp     short loc_140056D69
0x140056d3e  mov     rcx, [rbp+57h+pSid]; pSid
0x140056d42  call    cs:__imp_GetSidSubAuthorityCount
0x140056d49  nop     dword ptr [rax+rax+00h]
0x140056d4e  mov     cl, [rax]
0x140056d50  dec     cl
0x140056d52  movzx   edx, cl; nSubAuthority
0x140056d55  mov     rcx, [rbp+57h+pSid]; pSid
0x140056d59  call    cs:__imp_GetSidSubAuthority
0x140056d60  nop     dword ptr [rax+rax+00h]
0x140056d65  mov     ecx, [rax]
0x140056d67  mov     [rsi], ecx
0x140056d69  mov     eax, ebx
0x140056d6b  mov     rcx, [rbp+57h+var_30]
0x140056d6f  xor     rcx, rsp; StackCookie
0x140056d72  call    __security_check_cookie
0x140056d77  add     rsp, 0E0h
0x140056d7e  pop     r14
0x140056d80  pop     rdi
0x140056d81  pop     rsi
0x140056d82  pop     rbx
0x140056d83  pop     rbp
0x140056d84  retn
```
