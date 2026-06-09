# NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(_LUID *,ulong *)

- ea: `0x140012a9c`
- end: `0x140012bcd`
- name: `?GetAuthenticationIdAndIntegrity@TSidUserContext@NSecurityLibrary@@QEBAJPEAU_LUID@@PEAK@Z`
- size: `305`
- prototype: `__int64 __fastcall(NSecurityLibrary::TSidUserContext *__hidden this, struct _LUID *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006f98`
- `0x14000805c`
- `0x14000fae0`

## callees

- `0x140001ee0`
- `0x1400028b8`
- `0x140012a9c`
- `0x140012bd4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140012b96`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140012b96`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012b3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012b7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012b3d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140012b7f`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140012ba7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140012ba7`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::GetAuthenticationIdAndIntegrity(
        NSecurityLibrary::TSidUserContext *this,
        struct _LUID *a2,
        unsigned int *a3)
{
  int LastErrorAsHResult; // ebx
  NCoreLibrary *v7; // rcx
  void *v8; // rcx
  NCoreLibrary *v9; // rcx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD ReturnLength; // [rsp+30h] [rbp-79h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-71h] BYREF
  __int128 v14; // [rsp+3Ch] [rbp-6Dh]
  __int128 v15; // [rsp+4Ch] [rbp-5Dh]
  __int128 v16; // [rsp+5Ch] [rbp-4Dh]
  int v17; // [rsp+6Ch] [rbp-3Dh]
  PSID pSid[12]; // [rsp+70h] [rbp-39h] BYREF

  TokenInformation = 0;
  v17 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
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
        *a2 = *(struct _LUID *)((char *)&v14 + 4);
      }
      else
      {
        LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v7);
        if ( LastErrorAsHResult < 0 )
          return (unsigned int)LastErrorAsHResult;
      }
      v8 = (void *)*((_QWORD *)this + 2);
      ReturnLength = 88;
      if ( GetTokenInformation(v8, TokenIntegrityLevel, pSid, 0x58u, &ReturnLength) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
        *a3 = *GetSidSubAuthority(pSid[0], (unsigned __int8)(*SidSubAuthorityCount - 1));
      }
      else
      {
        return (unsigned int)NCoreLibrary::GetLastErrorAsHResult(v9);
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
0x140012a9c  push    rbp
0x140012a9e  push    rbx
0x140012a9f  push    rsi
0x140012aa0  push    rdi
0x140012aa1  push    r14
0x140012aa3  lea     rbp, [rsp-37h]
0x140012aa8  sub     rsp, 0E0h
0x140012aaf  mov     rax, cs:__security_cookie
0x140012ab6  xor     rax, rsp
0x140012ab9  mov     [rbp+57h+var_30], rax
0x140012abd  xorps   xmm0, xmm0
0x140012ac0  mov     [rbp+57h+TokenInformation], 0
0x140012ac7  xor     eax, eax
0x140012ac9  mov     rsi, r8
0x140012acc  mov     rdi, rdx
0x140012acf  mov     [rbp+57h+var_94], eax
0x140012ad2  mov     r14, rcx
0x140012ad5  xor     edx, edx; Val
0x140012ad7  lea     rcx, [rbp+57h+pSid]; void *
0x140012adb  lea     r8d, [rax+58h]; Size
0x140012adf  movups  [rbp+57h+var_C4], xmm0
0x140012ae3  movups  [rbp+57h+var_B4], xmm0
0x140012ae7  movups  [rbp+57h+var_A4], xmm0
0x140012aeb  call    memset_0
0x140012af0  mov     ebx, [r14+38h]
0x140012af4  mov     r9d, 38h ; '8'; TokenInformationLength
0x140012afa  mov     [rbp+57h+var_D0], r9d
0x140012afe  test    ebx, ebx
0x140012b00  js      loc_140012BB1
0x140012b06  test    rdi, rdi
0x140012b09  jz      short loc_140012B10
0x140012b0b  test    rsi, rsi
0x140012b0e  jnz     short loc_140012B1A
0x140012b10  mov     ebx, 80070057h
0x140012b15  jmp     loc_140012BB1
0x140012b1a  mov     qword ptr [rdi], 0
0x140012b21  lea     rax, [rbp+57h+var_D0]
0x140012b25  mov     dword ptr [rsi], 0
0x140012b2b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140012b2f  mov     rcx, [r14+10h]; TokenHandle
0x140012b33  mov     edx, 0Ah; TokenInformationClass
0x140012b38  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140012b3d  call    cs:__imp_GetTokenInformation
0x140012b43  test    eax, eax
0x140012b45  jnz     short loc_140012B54
0x140012b47  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140012b4c  mov     ebx, eax
0x140012b4e  test    eax, eax
0x140012b50  js      short loc_140012BB1
0x140012b52  jmp     short loc_140012B5D
0x140012b54  mov     rax, qword ptr [rbp+57h+var_C4+4]
0x140012b58  xor     ebx, ebx
0x140012b5a  mov     [rdi], rax
0x140012b5d  mov     rcx, [r14+10h]; TokenHandle
0x140012b61  lea     rax, [rbp+57h+var_D0]
0x140012b65  mov     r9d, 58h ; 'X'; TokenInformationLength
0x140012b6b  mov     [rbp+57h+var_D0], 58h ; 'X'
0x140012b72  lea     r8, [rbp+57h+pSid]; TokenInformation
0x140012b76  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x140012b7b  lea     edx, [r9-3Fh]; TokenInformationClass
0x140012b7f  call    cs:__imp_GetTokenInformation
0x140012b85  test    eax, eax
0x140012b87  jnz     short loc_140012B92
0x140012b89  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140012b8e  mov     ebx, eax
0x140012b90  jmp     short loc_140012BB1
0x140012b92  mov     rcx, [rbp+57h+pSid]; pSid
0x140012b96  call    cs:__imp_GetSidSubAuthorityCount
0x140012b9c  mov     cl, [rax]
0x140012b9e  dec     cl
0x140012ba0  movzx   edx, cl; nSubAuthority
0x140012ba3  mov     rcx, [rbp+57h+pSid]; pSid
0x140012ba7  call    cs:__imp_GetSidSubAuthority
0x140012bad  mov     ecx, [rax]
0x140012baf  mov     [rsi], ecx
0x140012bb1  mov     eax, ebx
0x140012bb3  mov     rcx, [rbp+57h+var_30]
0x140012bb7  xor     rcx, rsp; StackCookie
0x140012bba  call    __security_check_cookie
0x140012bbf  add     rsp, 0E0h
0x140012bc6  pop     r14
0x140012bc8  pop     rdi
0x140012bc9  pop     rsi
0x140012bca  pop     rbx
0x140012bcb  pop     rbp
0x140012bcc  retn
```
