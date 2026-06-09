# NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)

- ea: `0x140051cac`
- end: `0x140051ddd`
- name: `?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z`
- size: `305`
- prototype: `__int64 __fastcall(NSecurityLibrary::TSidUserContext *__hidden this, struct _LUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400473bc`

## callees

- `0x140007bdc`
- `0x14002abc0`
- `0x14002b810`
- `0x140051cac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140051d4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140051d8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140051d4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140051d8f`
- `ADVAPI32!GetSidSubAuthority` at `0x140051db7`
- `ADVAPI32!GetSidSubAuthority` at `0x140051db7`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140051da6`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x140051da6`

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
0x140051cac  push    rbp
0x140051cae  push    rbx
0x140051caf  push    rsi
0x140051cb0  push    rdi
0x140051cb1  push    r14
0x140051cb3  lea     rbp, [rsp-37h]
0x140051cb8  sub     rsp, 0E0h
0x140051cbf  mov     rax, cs:__security_cookie
0x140051cc6  xor     rax, rsp
0x140051cc9  mov     [rbp+57h+var_30], rax
0x140051ccd  xorps   xmm0, xmm0
0x140051cd0  mov     [rbp+57h+TokenInformation], 0
0x140051cd7  xor     eax, eax
0x140051cd9  mov     rsi, r8
0x140051cdc  mov     rdi, rdx
0x140051cdf  mov     [rbp+57h+var_94], eax
0x140051ce2  mov     r14, rcx
0x140051ce5  xor     edx, edx; Val
0x140051ce7  lea     rcx, [rbp+57h+pSid]; void *
0x140051ceb  lea     r8d, [rax+58h]; Size
0x140051cef  movups  [rbp+57h+var_C4], xmm0
0x140051cf3  movups  [rbp+57h+var_B4], xmm0
0x140051cf7  movups  [rbp+57h+var_A4], xmm0
0x140051cfb  call    memset_0
0x140051d00  mov     ebx, [r14+38h]
0x140051d04  mov     r9d, 38h ; '8'; TokenInformationLength
0x140051d0a  mov     [rbp+57h+var_D0], r9d
0x140051d0e  test    ebx, ebx
0x140051d10  js      loc_140051DC1
0x140051d16  test    rdi, rdi
0x140051d19  jz      short loc_140051D20
0x140051d1b  test    rsi, rsi
0x140051d1e  jnz     short loc_140051D2A
0x140051d20  mov     ebx, 80070057h
0x140051d25  jmp     loc_140051DC1
0x140051d2a  mov     qword ptr [rdi], 0
0x140051d31  lea     rax, [rbp+57h+var_D0]
0x140051d35  mov     dword ptr [rsi], 0
0x140051d3b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140051d3f  mov     rcx, [r14+10h]; TokenHandle
0x140051d43  mov     edx, 0Ah; TokenInformationClass
0x140051d48  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140051d4d  call    cs:__imp_GetTokenInformation
0x140051d53  test    eax, eax
0x140051d55  jnz     short loc_140051D64
0x140051d57  call    GetLastErrorAsHResult
0x140051d5c  mov     ebx, eax
0x140051d5e  test    eax, eax
0x140051d60  js      short loc_140051DC1
0x140051d62  jmp     short loc_140051D6D
0x140051d64  mov     rax, qword ptr [rbp+57h+var_C4+4]
0x140051d68  xor     ebx, ebx
0x140051d6a  mov     [rdi], rax
0x140051d6d  mov     rcx, [r14+10h]; TokenHandle
0x140051d71  lea     rax, [rbp+57h+var_D0]
0x140051d75  mov     r9d, 58h ; 'X'; TokenInformationLength
0x140051d7b  mov     [rbp+57h+var_D0], 58h ; 'X'
0x140051d82  lea     r8, [rbp+57h+pSid]; TokenInformation
0x140051d86  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140051d8b  lea     edx, [r9-3Fh]; TokenInformationClass
0x140051d8f  call    cs:__imp_GetTokenInformation
0x140051d95  test    eax, eax
0x140051d97  jnz     short loc_140051DA2
0x140051d99  call    GetLastErrorAsHResult
0x140051d9e  mov     ebx, eax
0x140051da0  jmp     short loc_140051DC1
0x140051da2  mov     rcx, [rbp+57h+pSid]; pSid
0x140051da6  call    cs:__imp_GetSidSubAuthorityCount
0x140051dac  mov     cl, [rax]
0x140051dae  dec     cl
0x140051db0  movzx   edx, cl; nSubAuthority
0x140051db3  mov     rcx, [rbp+57h+pSid]; pSid
0x140051db7  call    cs:__imp_GetSidSubAuthority
0x140051dbd  mov     ecx, [rax]
0x140051dbf  mov     [rsi], ecx
0x140051dc1  mov     eax, ebx
0x140051dc3  mov     rcx, [rbp+57h+var_30]
0x140051dc7  xor     rcx, rsp; StackCookie
0x140051dca  call    __security_check_cookie
0x140051dcf  add     rsp, 0E0h
0x140051dd6  pop     r14
0x140051dd8  pop     rdi
0x140051dd9  pop     rsi
0x140051dda  pop     rbx
0x140051ddb  pop     rbp
0x140051ddc  retn
```
