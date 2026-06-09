# SsCreateClusterAccountSecurityObjectIfNeccesary

- ea: `0x1800284b4`
- end: `0x18002870f`
- name: `SsCreateClusterAccountSecurityObjectIfNeccesary`
- size: `603`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800289a4`

## callees

- `0x18000aa8c`
- `0x18000b940`
- `0x18001d230`
- `0x180027f60`
- `0x1800280f8`
- `0x1800284b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002850c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002855b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002850c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002855b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002862f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028683`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002862f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002868d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002868d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800285b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028650`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800285b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028575`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800286ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028575`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800285dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800286ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002851f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002851f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800284eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800284eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002853a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002853a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800286fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800286fc`

## string_xrefs

- `0x1800286ac`: `ClusterAccountSecurityObject`

## pseudocode

```c
__int64 __fastcall SsCreateClusterAccountSecurityObjectIfNeccesary(STRSAFE_LPCWSTR pszSrc)
{
  char v2; // bl
  HLOCAL v4; // rdi
  unsigned int ClusterAccountToken; // ebx
  size_t v6; // rbx
  HLOCAL v7; // rax
  void *v8; // r11
  DWORD v9; // r9d
  unsigned int v10; // [rsp+30h] [rbp-20h]
  __int16 v11; // [rsp+40h] [rbp-10h] BYREF
  char v12; // [rsp+42h] [rbp-Eh]
  int v13; // [rsp+44h] [rbp-Ch]
  HLOCAL v14; // [rsp+48h] [rbp-8h]
  DWORD ReturnLength; // [rsp+88h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+90h] [rbp+40h] BYREF
  size_t pcchLength; // [rsp+98h] [rbp+48h] BYREF

  v13 = 0x20000;
  v11 = 0;
  v12 = 0;
  pcchLength = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  AcquireSRWLockShared(&SsClusterAccountSDRWLock);
  if ( !SsClusterAccountSecurityDescriptorInitialized
    || !SsClusterAccountName
    || (v2 = 0, (unsigned int)_o__wcsicmp(SsClusterAccountName, pszSrc)) )
  {
    v2 = 1;
  }
  ReleaseSRWLockShared(&SsClusterAccountSDRWLock);
  if ( !v2 )
    return 0;
  v4 = 0;
  AcquireSRWLockExclusive(&SsClusterAccountSDRWLock);
  if ( !SsClusterAccountSecurityDescriptorInitialized )
  {
LABEL_10:
    if ( SsClusterAccountName )
    {
      LocalFree(SsClusterAccountName);
      SsClusterAccountName = 0;
    }
    goto LABEL_12;
  }
  if ( SsClusterAccountName )
  {
    ClusterAccountToken = 0;
    if ( !(unsigned int)_o__wcsicmp(SsClusterAccountName, pszSrc) )
      goto LABEL_30;
    goto LABEL_10;
  }
LABEL_12:
  if ( StringCchLengthW(pszSrc, 0x100u, &pcchLength) >= 0 )
  {
    v6 = pcchLength;
    v7 = LocalAlloc(0x40u, 2 * pcchLength + 2);
    SsClusterAccountName = v7;
    if ( v7 && StringCchCopyW((STRSAFE_LPWSTR)v7, v6 + 1, pszSrc) < 0 )
    {
      LocalFree(v8);
      SsClusterAccountName = 0;
    }
    if ( SsClusterAccountSecurityDescriptorInitialized )
    {
      DeleteSecurityObject(SsClusterAccountSecurityObject);
      SsClusterAccountSecurityDescriptorInitialized = 0;
    }
    ClusterAccountToken = GetClusterAccountToken(&TokenHandle);
    if ( ClusterAccountToken )
      goto LABEL_30;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &ReturnLength) )
    {
      v9 = 0;
    }
    else
    {
      ClusterAccountToken = GetLastError();
      if ( ClusterAccountToken != 122 )
        goto LABEL_30;
      v4 = LocalAlloc(0x40u, ReturnLength);
      if ( !v4 )
      {
        ClusterAccountToken = 1450;
        goto LABEL_30;
      }
      v9 = ReturnLength;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, v9, &ReturnLength) )
    {
      LOBYTE(v10) = 1;
      v14 = v4;
      ClusterAccountToken = CreateSecurityObject(
                              (const WCHAR **)SsClusterAccountSecurityObject,
                              L"ClusterAccountSecurityObject",
                              (struct _GENERIC_MAPPING *)SsClusterAccountMapping,
                              (int)&v11,
                              1,
                              0,
                              v10);
      if ( !ClusterAccountToken )
        SsClusterAccountSecurityDescriptorInitialized = 1;
    }
    else
    {
      ClusterAccountToken = GetLastError();
    }
    goto LABEL_30;
  }
  ClusterAccountToken = 1315;
LABEL_30:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v4 )
    LocalFree(v4);
  ReleaseSRWLockExclusive(&SsClusterAccountSDRWLock);
  return ClusterAccountToken;
}

```

## disassembly

```asm
0x1800284b4  push    rbp
0x1800284b6  push    rbx
0x1800284b7  push    rsi
0x1800284b8  push    rdi
0x1800284b9  push    r14
0x1800284bb  mov     rbp, rsp
0x1800284be  sub     rsp, 50h
0x1800284c2  xor     r14d, r14d
0x1800284c5  mov     [rbp+var_C], 20000h
0x1800284cc  mov     rsi, rcx
0x1800284cf  mov     [rbp+var_10], r14w
0x1800284d4  lea     rcx, SsClusterAccountSDRWLock; SRWLock
0x1800284db  mov     [rbp+var_E], r14b
0x1800284df  mov     [rbp+pcchLength], r14
0x1800284e3  mov     [rbp+TokenHandle], r14
0x1800284e7  mov     [rbp+arg_8], r14d
0x1800284eb  call    cs:__imp_AcquireSRWLockShared
0x1800284f1  cmp     cs:SsClusterAccountSecurityDescriptorInitialized, r14b
0x1800284f8  jz      short loc_180028516
0x1800284fa  mov     rcx, cs:SsClusterAccountName
0x180028501  test    rcx, rcx
0x180028504  jz      short loc_180028516
0x180028506  mov     rdx, rsi
0x180028509  mov     bl, r14b
0x18002850c  call    cs:__imp__o__wcsicmp
0x180028512  test    eax, eax
0x180028514  jz      short loc_180028518
0x180028516  mov     bl, 1
0x180028518  lea     rcx, SsClusterAccountSDRWLock; SRWLock
0x18002851f  call    cs:__imp_ReleaseSRWLockShared
0x180028525  test    bl, bl
0x180028527  jnz     short loc_180028530
0x180028529  xor     eax, eax
0x18002852b  jmp     loc_180028704
0x180028530  lea     rcx, SsClusterAccountSDRWLock; SRWLock
0x180028537  mov     rdi, r14
0x18002853a  call    cs:__imp_AcquireSRWLockExclusive
0x180028540  cmp     cs:SsClusterAccountSecurityDescriptorInitialized, r14b
0x180028547  jz      short loc_180028569
0x180028549  mov     rcx, cs:SsClusterAccountName
0x180028550  test    rcx, rcx
0x180028553  jz      short loc_180028582
0x180028555  mov     rdx, rsi
0x180028558  mov     ebx, r14d
0x18002855b  call    cs:__imp__o__wcsicmp
0x180028561  test    eax, eax
0x180028563  jz      loc_1800286D8
0x180028569  mov     rcx, cs:SsClusterAccountName; hMem
0x180028570  test    rcx, rcx
0x180028573  jz      short loc_180028582
0x180028575  call    cs:__imp_LocalFree
0x18002857b  mov     cs:SsClusterAccountName, r14
0x180028582  lea     r8, [rbp+pcchLength]; pcchLength
0x180028586  mov     edx, 100h; cchMax
0x18002858b  mov     rcx, rsi; psz
0x18002858e  call    StringCchLengthW
0x180028593  test    eax, eax
0x180028595  jns     short loc_1800285A1
0x180028597  mov     ebx, 523h
0x18002859c  jmp     loc_1800286D8
0x1800285a1  mov     rbx, [rbp+pcchLength]
0x1800285a5  mov     ecx, 40h ; '@'; uFlags
0x1800285aa  lea     rdx, ds:2[rbx*2]; uBytes
0x1800285b2  call    cs:__imp_LocalAlloc
0x1800285b8  mov     cs:SsClusterAccountName, rax
0x1800285bf  mov     r11, rax
0x1800285c2  test    rax, rax
0x1800285c5  jz      short loc_1800285EA
0x1800285c7  lea     rdx, [rbx+1]; cchDest
0x1800285cb  mov     r8, rsi; pszSrc
0x1800285ce  mov     rcx, rax; pszDest
0x1800285d1  call    StringCchCopyW
0x1800285d6  test    eax, eax
0x1800285d8  jns     short loc_1800285EA
0x1800285da  mov     rcx, r11; hMem
0x1800285dd  call    cs:__imp_LocalFree
0x1800285e3  mov     cs:SsClusterAccountName, r14
0x1800285ea  cmp     cs:SsClusterAccountSecurityDescriptorInitialized, r14b
0x1800285f1  jz      short loc_180028606
0x1800285f3  lea     rcx, SsClusterAccountSecurityObject
0x1800285fa  call    DeleteSecurityObject
0x1800285ff  mov     cs:SsClusterAccountSecurityDescriptorInitialized, r14b
0x180028606  lea     rcx, [rbp+TokenHandle]; phNewToken
0x18002860a  call    GetClusterAccountToken
0x18002860f  mov     ebx, eax
0x180028611  test    eax, eax
0x180028613  jnz     loc_1800286D8
0x180028619  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002861d  lea     rax, [rbp+arg_8]
0x180028621  xor     r9d, r9d; TokenInformationLength
0x180028624  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180028629  xor     r8d, r8d; TokenInformation
0x18002862c  lea     edx, [rbx+1]; TokenInformationClass
0x18002862f  call    cs:__imp_GetTokenInformation
0x180028635  test    eax, eax
0x180028637  jnz     short loc_18002866B
0x180028639  call    cs:__imp_GetLastError
0x18002863f  mov     ebx, eax
0x180028641  cmp     eax, 7Ah ; 'z'
0x180028644  jnz     loc_1800286D8
0x18002864a  mov     edx, [rbp+arg_8]; uBytes
0x18002864d  lea     ecx, [rax-3Ah]; uFlags
0x180028650  call    cs:__imp_LocalAlloc
0x180028656  mov     rdi, rax
0x180028659  test    rax, rax
0x18002865c  jnz     short loc_180028665
0x18002865e  mov     ebx, 5AAh
0x180028663  jmp     short loc_1800286D8
0x180028665  mov     r9d, [rbp+arg_8]
0x180028669  jmp     short loc_18002866E
0x18002866b  mov     r9d, r14d; TokenInformationLength
0x18002866e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180028672  lea     rax, [rbp+arg_8]
0x180028676  mov     r8, rdi; TokenInformation
0x180028679  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18002867e  mov     edx, 1; TokenInformationClass
0x180028683  call    cs:__imp_GetTokenInformation
0x180028689  test    eax, eax
0x18002868b  jnz     short loc_180028697
0x18002868d  call    cs:__imp_GetLastError
0x180028693  mov     ebx, eax
0x180028695  jmp     short loc_1800286D8
0x180028697  mov     byte ptr [rsp+50h+var_20], 1
0x18002869c  lea     r9, [rbp+var_10]
0x1800286a0  mov     [rsp+50h+var_28], r14b
0x1800286a5  lea     r8, SsClusterAccountMapping
0x1800286ac  lea     rdx, aClusteraccount; "ClusterAccountSecurityObject"
0x1800286b3  mov     dword ptr [rsp+50h+ReturnLength], 1
0x1800286bb  lea     rcx, SsClusterAccountSecurityObject
0x1800286c2  mov     [rbp+var_8], rdi
0x1800286c6  call    CreateSecurityObject
0x1800286cb  mov     ebx, eax
0x1800286cd  test    eax, eax
0x1800286cf  jnz     short loc_1800286D8
0x1800286d1  mov     cs:SsClusterAccountSecurityDescriptorInitialized, 1
0x1800286d8  mov     rcx, [rbp+TokenHandle]; hObject
0x1800286dc  test    rcx, rcx
0x1800286df  jz      short loc_1800286E7
0x1800286e1  call    cs:__imp_CloseHandle
0x1800286e7  test    rdi, rdi
0x1800286ea  jz      short loc_1800286F5
0x1800286ec  mov     rcx, rdi; hMem
0x1800286ef  call    cs:__imp_LocalFree
0x1800286f5  lea     rcx, SsClusterAccountSDRWLock; SRWLock
0x1800286fc  call    cs:__imp_ReleaseSRWLockExclusive
0x180028702  mov     eax, ebx
0x180028704  add     rsp, 50h
0x180028708  pop     r14
0x18002870a  pop     rdi
0x18002870b  pop     rsi
0x18002870c  pop     rbx
0x18002870d  pop     rbp
0x18002870e  retn
```
