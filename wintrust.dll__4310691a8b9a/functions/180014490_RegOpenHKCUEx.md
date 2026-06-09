# RegOpenHKCUEx

- ea: `0x180014490`
- end: `0x180014966`
- name: `RegOpenHKCUEx`
- size: `1238`
- prototype: `DWORD __fastcall(HKEY *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a410`
- `0x180013ec0`
- `0x180013f60`

## callees

- `0x180014070`
- `0x180014490`
- `0x180014970`
- `0x180014bb8`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800145d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014764`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800147d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800145d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014764`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800147d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800148f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014944`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800144d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800144d6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800144ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800144ee`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001451b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001451b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014587`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800147f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014903`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014587`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800147f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014903`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001475c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001475c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800145ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001478e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800148a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001478e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800148a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001457a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001457a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180014604`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180014604`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001459e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001459e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800145e7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800145e7`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800145f8`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800145f8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001455d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800148d2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001455d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800148d2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800146e9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800146e9`

## pseudocode

```c
DWORD __fastcall RegOpenHKCUEx(HKEY *a1)
{
  void *v1; // r14
  unsigned int v2; // esi
  HKEY *v3; // rdi
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  void *v6; // r12
  wchar_t *v7; // r13
  BOOL v8; // ebx
  PSID *v9; // rdi
  PSID *v10; // r15
  DWORD LengthSid; // r12d
  HLOCAL v12; // rax
  void *v13; // r15
  DWORD LastError; // edi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rbx
  DWORD v16; // edi
  HRESULT v17; // eax
  DWORD i; // ebx
  int v19; // eax
  DWORD v20; // edi
  wchar_t *v21; // rdx
  LSTATUS v22; // ebx
  DWORD result; // eax
  DWORD v24; // ecx
  wchar_t *v25; // rax
  __int64 v26; // [rsp+30h] [rbp-D0h]
  __int64 v27; // [rsp+30h] [rbp-D0h]
  DWORD TokenInformationLength; // [rsp+60h] [rbp-A0h] BYREF
  size_t pcchRemaining; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+70h] [rbp-90h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+78h] [rbp-88h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-80h] BYREF
  PHKEY phkResult; // [rsp+88h] [rbp-78h]
  _BYTE TokenInformation[256]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pszDest[256]; // [rsp+190h] [rbp+90h] BYREF

  v1 = 0;
  phkResult = a1;
  v2 = 256;
  *a1 = 0;
  v30 = 256;
  v3 = a1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      goto LABEL_37;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      goto LABEL_37;
  }
  v6 = TokenHandle;
  TokenInformationLength = 256;
  v7 = 0;
  v8 = GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &TokenInformationLength);
  if ( v8 )
  {
    v9 = 0;
    v10 = (PSID *)TokenInformation;
LABEL_6:
    v8 = 0;
    LengthSid = GetLengthSid(*v10);
    v12 = LocalAlloc(0, LengthSid);
    v1 = v12;
    if ( v12 )
    {
      v8 = CopySid(LengthSid, v12, *v10);
      if ( !v8 )
      {
        freeWithSavedLastError(v1);
        v1 = 0;
      }
    }
    if ( !v9 )
      goto LABEL_10;
    goto LABEL_44;
  }
  if ( GetLastError() != 122 )
    goto LABEL_10;
  v9 = (PSID *)LocalAlloc(0, TokenInformationLength);
  if ( !v9 )
    goto LABEL_10;
  v10 = v9;
  v8 = GetTokenInformation(v6, TokenUser, v9, TokenInformationLength, &TokenInformationLength);
  if ( v8 )
    goto LABEL_6;
LABEL_44:
  freeWithSavedLastError(v9);
LABEL_10:
  v13 = TokenHandle;
  if ( TokenHandle )
  {
    LastError = GetLastError();
    CloseHandle(v13);
    SetLastError(LastError);
  }
  if ( !v8 )
    goto LABEL_25;
  if ( !IsValidSid(v1) )
  {
LABEL_36:
    v8 = 0;
    goto LABEL_25;
  }
  SidIdentifierAuthority = GetSidIdentifierAuthority(v1);
  v16 = *GetSidSubAuthorityCount(v1);
  if ( 12 * v16 + 28 > 0x100 )
  {
    v2 = 12 * v16 + 28;
    v30 = v2;
    v24 = 122;
    goto LABEL_35;
  }
  ppszDestEnd = pszDest;
  pcchRemaining = 256;
  v17 = StringCchPrintfExW(pszDest, 0x100u, &ppszDestEnd, &pcchRemaining, 0, L"S-%lu-", 1);
  if ( v17 < 0 )
    goto LABEL_34;
  if ( !*(_WORD *)SidIdentifierAuthority->Value )
  {
    LODWORD(v26) = SidIdentifierAuthority->Value[5]
                 + (SidIdentifierAuthority->Value[4] << 8)
                 + (SidIdentifierAuthority->Value[3] << 16)
                 + (SidIdentifierAuthority->Value[2] << 24);
    v17 = StringCchPrintfExW(ppszDestEnd, pcchRemaining, &ppszDestEnd, &pcchRemaining, 0, L"%lu", v26);
    if ( v17 >= 0 )
      goto LABEL_18;
    goto LABEL_34;
  }
  LODWORD(v26) = SidIdentifierAuthority->Value[0];
  v17 = StringCchPrintfExW(
          ppszDestEnd,
          pcchRemaining,
          &ppszDestEnd,
          &pcchRemaining,
          0,
          L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
          v26,
          SidIdentifierAuthority->Value[1],
          SidIdentifierAuthority->Value[2],
          SidIdentifierAuthority->Value[3],
          SidIdentifierAuthority->Value[4],
          SidIdentifierAuthority->Value[5]);
  if ( v17 < 0 )
  {
LABEL_34:
    v24 = v17;
LABEL_35:
    SetLastError(v24);
    goto LABEL_36;
  }
LABEL_18:
  for ( i = 0; i < v16; ++i )
  {
    LODWORD(v27) = *GetSidSubAuthority(v1, i);
    v17 = StringCchPrintfExW(ppszDestEnd, pcchRemaining, &ppszDestEnd, &pcchRemaining, 0, L"-%lu", v27);
    if ( v17 < 0 )
      goto LABEL_34;
  }
  v19 = pcchRemaining;
  if ( pcchRemaining )
    v19 = pcchRemaining - 1;
  v2 = 256 - v19;
  v8 = 1;
  v30 = 256 - v19;
LABEL_25:
  if ( v1 )
  {
    v20 = GetLastError();
    LocalFree(v1);
    SetLastError(v20);
  }
  v3 = phkResult;
  if ( v8 )
  {
    v21 = pszDest;
LABEL_29:
    v22 = RegOpenKeyExW(HKEY_USERS, v21, 0, 0x2000000u, v3);
    if ( v22 )
      v22 = RegOpenKeyExW(HKEY_USERS, L".Default", 0, 0x2000000u, v3);
    if ( v7 )
      freeWithSavedLastError(v7);
    return v22;
  }
LABEL_37:
  if ( GetLastError() == 122 )
  {
    v25 = (wchar_t *)LocalAlloc(0, 2LL * v2);
    v7 = v25;
    if ( v25 )
    {
      if ( (unsigned int)GetUserTextualSidHKCU(v25) )
      {
        v21 = v7;
        goto LABEL_29;
      }
      freeWithSavedLastError(v7);
    }
  }
  result = GetLastError();
  if ( !result )
    return 13;
  return result;
}

```

## disassembly

```asm
0x180014490  mov     [rsp-8+arg_18], rbx
0x180014495  push    rbp
0x180014496  push    rsi
0x180014497  push    rdi
0x180014498  push    r13
0x18001449a  push    r14
0x18001449c  lea     rbp, [rsp-2A0h]
0x1800144a4  sub     rsp, 3A0h
0x1800144ab  mov     rax, cs:__security_cookie
0x1800144b2  xor     rax, rsp
0x1800144b5  mov     [rbp+2C0h+var_30], rax
0x1800144bc  xor     r14d, r14d
0x1800144bf  mov     [rbp+2C0h+phkResult], rcx
0x1800144c3  mov     esi, 100h
0x1800144c8  mov     [rcx], r14
0x1800144cb  mov     [rsp+3C0h+var_350], esi
0x1800144cf  mov     rdi, rcx
0x1800144d2  mov     [rbp+2C0h+TokenHandle], r14
0x1800144d6  call    cs:__imp_GetCurrentThread
0x1800144dc  lea     r9, [rbp+2C0h+TokenHandle]; TokenHandle
0x1800144e0  mov     edx, 8; DesiredAccess
0x1800144e5  mov     rcx, rax; ThreadHandle
0x1800144e8  mov     r8d, 1; OpenAsSelf
0x1800144ee  call    cs:__imp_OpenThreadToken
0x1800144f4  test    eax, eax
0x1800144f6  jnz     short loc_180014529
0x1800144f8  call    cs:__imp_GetLastError
0x1800144fe  cmp     eax, 3F0h
0x180014503  jnz     loc_1800147DF
0x180014509  call    cs:__imp_GetCurrentProcess
0x18001450f  lea     r8, [rbp+2C0h+TokenHandle]; TokenHandle
0x180014513  mov     edx, 8; DesiredAccess
0x180014518  mov     rcx, rax; ProcessHandle
0x18001451b  call    cs:__imp_OpenProcessToken
0x180014521  test    eax, eax
0x180014523  jz      loc_1800147DF
0x180014529  mov     [rsp+3C0h+arg_8], r12
0x180014531  lea     rax, [rsp+3C0h+TokenInformationLength]
0x180014536  mov     r12, [rbp+2C0h+TokenHandle]
0x18001453a  lea     r8, [rbp+2C0h+TokenInformation]; TokenInformation
0x18001453e  mov     rcx, r12; TokenHandle
0x180014541  mov     [rsp+3C0h+arg_10], r15
0x180014549  mov     r9d, esi; TokenInformationLength
0x18001454c  mov     [rsp+3C0h+TokenInformationLength], esi
0x180014550  mov     edx, 1; TokenInformationClass
0x180014555  mov     [rsp+3C0h+ReturnLength], rax; ReturnLength
0x18001455a  mov     r13, r14
0x18001455d  call    cs:__imp_GetTokenInformation
0x180014563  mov     ebx, eax
0x180014565  test    eax, eax
0x180014567  jz      loc_1800148F2
0x18001456d  mov     rdi, r14
0x180014570  lea     r15, [rbp+2C0h+TokenInformation]
0x180014574  mov     rcx, [r15]; pSid
0x180014577  mov     ebx, r14d
0x18001457a  call    cs:__imp_GetLengthSid
0x180014580  mov     edx, eax; uBytes
0x180014582  xor     ecx, ecx; uFlags
0x180014584  mov     r12d, eax
0x180014587  call    cs:__imp_LocalAlloc
0x18001458d  mov     r14, rax
0x180014590  test    rax, rax
0x180014593  jz      short loc_1800145AE
0x180014595  mov     r8, [r15]; pSourceSid
0x180014598  mov     rdx, rax; pDestinationSid
0x18001459b  mov     ecx, r12d; nDestinationSidLength
0x18001459e  call    cs:__imp_CopySid
0x1800145a4  mov     ebx, eax
0x1800145a6  test    eax, eax
0x1800145a8  jz      loc_180014919
0x1800145ae  xor     r12d, r12d
0x1800145b1  test    rdi, rdi
0x1800145b4  jnz     loc_1800148E5
0x1800145ba  mov     r15, [rbp+2C0h+TokenHandle]
0x1800145be  test    r15, r15
0x1800145c1  jz      short loc_1800145DC
0x1800145c3  call    cs:__imp_GetLastError
0x1800145c9  mov     rcx, r15; hObject
0x1800145cc  mov     edi, eax
0x1800145ce  call    cs:__imp_CloseHandle
0x1800145d4  mov     ecx, edi; dwErrCode
0x1800145d6  call    cs:__imp_SetLastError
0x1800145dc  test    ebx, ebx
0x1800145de  jz      loc_18001473C
0x1800145e4  mov     rcx, r14; pSid
0x1800145e7  call    cs:__imp_IsValidSid
0x1800145ed  test    eax, eax
0x1800145ef  jz      loc_1800147D7
0x1800145f5  mov     rcx, r14; pSid
0x1800145f8  call    cs:__imp_GetSidIdentifierAuthority
0x1800145fe  mov     rcx, r14; pSid
0x180014601  mov     rbx, rax
0x180014604  call    cs:__imp_GetSidSubAuthorityCount
0x18001460a  movzx   edi, byte ptr [rax]
0x18001460d  lea     ecx, [rdi+rdi*2]
0x180014610  lea     ecx, ds:1Ch[rcx*4]
0x180014617  cmp     ecx, esi
0x180014619  ja      loc_18001492C
0x18001461f  lea     rax, [rbp+2C0h+pszDest]
0x180014626  mov     dword ptr [rsp+3C0h+var_390], 1
0x18001462e  mov     [rsp+3C0h+ppszDestEnd], rax
0x180014633  lea     r9, [rsp+3C0h+pcchRemaining]; pcchRemaining
0x180014638  lea     rax, aSLu; "S-%lu-"
0x18001463f  mov     [rsp+3C0h+pcchRemaining], rsi
0x180014644  mov     [rsp+3C0h+pszFormat], rax; pszFormat
0x180014649  lea     r8, [rsp+3C0h+ppszDestEnd]; ppszDestEnd
0x18001464e  mov     rdx, rsi; cchDest
0x180014651  mov     [rsp+3C0h+ReturnLength], r12; dwFlags
0x180014656  lea     rcx, [rbp+2C0h+pszDest]; pszDest
0x18001465d  call    StringCchPrintfExW
0x180014662  test    eax, eax
0x180014664  js      loc_1800147CF
0x18001466a  movzx   r10d, byte ptr [rbx]
0x18001466e  test    r10b, r10b
0x180014671  jnz     loc_180014824
0x180014677  cmp     [rbx+1], r13b
0x18001467b  jnz     loc_180014824
0x180014681  movzx   ecx, byte ptr [rbx+2]
0x180014685  lea     r9, [rsp+3C0h+pcchRemaining]; pcchRemaining
0x18001468a  movzx   eax, byte ptr [rbx+3]
0x18001468e  lea     r8, [rsp+3C0h+ppszDestEnd]; ppszDestEnd
0x180014693  mov     rdx, [rsp+3C0h+pcchRemaining]; cchDest
0x180014698  shl     eax, 10h
0x18001469b  shl     ecx, 18h
0x18001469e  add     ecx, eax
0x1800146a0  movzx   eax, byte ptr [rbx+4]
0x1800146a4  shl     eax, 8
0x1800146a7  add     ecx, eax
0x1800146a9  movzx   eax, byte ptr [rbx+5]
0x1800146ad  add     ecx, eax
0x1800146af  lea     rax, aLu_0; "%lu"
0x1800146b6  mov     dword ptr [rsp+3C0h+var_390], ecx
0x1800146ba  mov     rcx, [rsp+3C0h+ppszDestEnd]; pszDest
0x1800146bf  mov     [rsp+3C0h+pszFormat], rax; pszFormat
0x1800146c4  mov     [rsp+3C0h+ReturnLength], r12; dwFlags
0x1800146c9  call    StringCchPrintfExW
0x1800146ce  test    eax, eax
0x1800146d0  js      loc_1800147CF
0x1800146d6  mov     ebx, r12d
0x1800146d9  lea     r15, aLu; "-%lu"
0x1800146e0  cmp     ebx, edi
0x1800146e2  jnb     short loc_180014724
0x1800146e4  mov     edx, ebx; nSubAuthority
0x1800146e6  mov     rcx, r14; pSid
0x1800146e9  call    cs:__imp_GetSidSubAuthority
0x1800146ef  mov     rdx, [rsp+3C0h+pcchRemaining]; cchDest
0x1800146f4  lea     r9, [rsp+3C0h+pcchRemaining]; pcchRemaining
0x1800146f9  lea     r8, [rsp+3C0h+ppszDestEnd]; ppszDestEnd
0x1800146fe  mov     ecx, [rax]
0x180014700  mov     dword ptr [rsp+3C0h+var_390], ecx
0x180014704  mov     rcx, [rsp+3C0h+ppszDestEnd]; pszDest
0x180014709  mov     [rsp+3C0h+pszFormat], r15; pszFormat
0x18001470e  mov     [rsp+3C0h+ReturnLength], r12; dwFlags
0x180014713  call    StringCchPrintfExW
0x180014718  test    eax, eax
0x18001471a  js      loc_1800147CF
0x180014720  inc     ebx
0x180014722  jmp     short loc_1800146E0
0x180014724  mov     rax, [rsp+3C0h+pcchRemaining]
0x180014729  test    rax, rax
0x18001472c  jz      short loc_180014731
0x18001472e  dec     rax
0x180014731  sub     esi, eax
0x180014733  mov     ebx, 1
0x180014738  mov     [rsp+3C0h+var_350], esi
0x18001473c  mov     r15, [rsp+3C0h+arg_10]
0x180014744  mov     r12, [rsp+3C0h+arg_8]
0x18001474c  test    r14, r14
0x18001474f  jz      short loc_18001476A
0x180014751  call    cs:__imp_GetLastError
0x180014757  mov     rcx, r14; hMem
0x18001475a  mov     edi, eax
0x18001475c  call    cs:__imp_LocalFree
0x180014762  mov     ecx, edi; dwErrCode
0x180014764  call    cs:__imp_SetLastError
0x18001476a  mov     rdi, [rbp+2C0h+phkResult]
0x18001476e  test    ebx, ebx
0x180014770  jz      short loc_1800147DF
0x180014772  lea     rdx, [rbp+2C0h+pszDest]; lpSubKey
0x180014779  mov     r9d, 2000000h; samDesired
0x18001477f  mov     [rsp+3C0h+ReturnLength], rdi; phkResult
0x180014784  xor     r8d, r8d; ulOptions
0x180014787  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18001478e  call    cs:__imp_RegOpenKeyExW
0x180014794  mov     ebx, eax
0x180014796  test    eax, eax
0x180014798  jnz     loc_18001488C
0x18001479e  test    r13, r13
0x1800147a1  jnz     loc_180014959
0x1800147a7  mov     eax, ebx
0x1800147a9  mov     rcx, [rbp+2C0h+var_30]
0x1800147b0  xor     rcx, rsp; StackCookie
0x1800147b3  call    __security_check_cookie
0x1800147b8  mov     rbx, [rsp+3C0h+arg_18]
0x1800147c0  add     rsp, 3A0h
0x1800147c7  pop     r14
0x1800147c9  pop     r13
0x1800147cb  pop     rdi
0x1800147cc  pop     rsi
0x1800147cd  pop     rbp
0x1800147ce  retn
0x1800147cf  mov     ecx, eax; dwErrCode
0x1800147d1  call    cs:__imp_SetLastError
0x1800147d7  mov     ebx, r12d
0x1800147da  jmp     loc_18001473C
0x1800147df  call    cs:__imp_GetLastError
0x1800147e5  cmp     eax, 7Ah ; 'z'
0x1800147e8  jnz     loc_180014944
0x1800147ee  mov     edx, esi
0x1800147f0  xor     ecx, ecx; uFlags
0x1800147f2  add     rdx, rdx; uBytes
0x1800147f5  call    cs:__imp_LocalAlloc
0x1800147fb  mov     r13, rax
0x1800147fe  test    rax, rax
0x180014801  jz      loc_180014944
0x180014807  lea     rdx, [rsp+3C0h+var_350]
0x18001480c  mov     rcx, rax; pszDest
0x18001480f  call    GetUserTextualSidHKCU
0x180014814  test    eax, eax
0x180014816  jz      loc_18001493C
0x18001481c  mov     rdx, r13
0x18001481f  jmp     loc_180014779
0x180014824  movzx   eax, byte ptr [rbx+5]
0x180014828  movzx   ecx, byte ptr [rbx+4]
0x18001482c  movzx   edx, byte ptr [rbx+3]
0x180014830  movzx   r8d, byte ptr [rbx+2]
0x180014835  movzx   r9d, byte ptr [rbx+1]
0x18001483a  mov     [rsp+3C0h+var_368], eax
0x18001483e  lea     rax, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x180014845  mov     [rsp+3C0h+var_370], ecx
0x180014849  mov     rcx, [rsp+3C0h+ppszDestEnd]; pszDest
0x18001484e  mov     [rsp+3C0h+var_378], edx
0x180014852  mov     rdx, [rsp+3C0h+pcchRemaining]; cchDest
0x180014857  mov     [rsp+3C0h+var_380], r8d
0x18001485c  lea     r8, [rsp+3C0h+ppszDestEnd]; ppszDestEnd
0x180014861  mov     [rsp+3C0h+var_388], r9d
0x180014866  lea     r9, [rsp+3C0h+pcchRemaining]; pcchRemaining
0x18001486b  mov     dword ptr [rsp+3C0h+var_390], r10d
0x180014870  mov     [rsp+3C0h+pszFormat], rax; pszFormat
0x180014875  mov     [rsp+3C0h+ReturnLength], r12; dwFlags
0x18001487a  call    StringCchPrintfExW
0x18001487f  test    eax, eax
0x180014881  jns     loc_1800146D6
0x180014887  jmp     loc_1800147CF
0x18001488c  mov     r9d, 2000000h; samDesired
0x180014892  mov     [rsp+3C0h+ReturnLength], rdi; phkResult
0x180014897  xor     r8d, r8d; ulOptions
0x18001489a  lea     rdx, aDefault; ".Default"
0x1800148a1  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800148a8  call    cs:__imp_RegOpenKeyExW
0x1800148ae  mov     ebx, eax
0x1800148b0  jmp     loc_18001479E
0x1800148b5  mov     r9d, [rsp+3C0h+TokenInformationLength]; TokenInformationLength
0x1800148ba  lea     rax, [rsp+3C0h+TokenInformationLength]
0x1800148bf  mov     r8, rdi; TokenInformation
0x1800148c2  mov     [rsp+3C0h+ReturnLength], rax; ReturnLength
0x1800148c7  mov     edx, 1; TokenInformationClass
0x1800148cc  mov     rcx, r12; TokenHandle
0x1800148cf  mov     r15, rdi
0x1800148d2  call    cs:__imp_GetTokenInformation
0x1800148d8  mov     ebx, eax
0x1800148da  test    eax, eax
0x1800148dc  jnz     loc_180014574
0x1800148e2  xor     r12d, r12d
0x1800148e5  mov     rcx, rdi; hMem
0x1800148e8  call    freeWithSavedLastError
0x1800148ed  jmp     loc_1800145BA
0x1800148f2  call    cs:__imp_GetLastError
0x1800148f8  cmp     eax, 7Ah ; 'z'
0x1800148fb  jnz     short loc_180014911
0x1800148fd  mov     edx, [rsp+3C0h+TokenInformationLength]; uBytes
0x180014901  xor     ecx, ecx; uFlags
0x180014903  call    cs:__imp_LocalAlloc
0x180014909  mov     rdi, rax
0x18001490c  test    rax, rax
0x18001490f  jnz     short loc_1800148B5
0x180014911  xor     r12d, r12d
0x180014914  jmp     loc_1800145BA
0x180014919  mov     rcx, r14; hMem
0x18001491c  call    freeWithSavedLastError
0x180014921  xor     r12d, r12d
0x180014924  mov     r14d, r12d
0x180014927  jmp     loc_1800145B1
0x18001492c  mov     esi, ecx
0x18001492e  mov     [rsp+3C0h+var_350], ecx
0x180014932  mov     ecx, 7Ah ; 'z'
0x180014937  jmp     loc_1800147D1
0x18001493c  mov     rcx, r13; hMem
0x18001493f  call    freeWithSavedLastError
0x180014944  call    cs:__imp_GetLastError
0x18001494a  test    eax, eax
0x18001494c  mov     ecx, 0Dh
0x180014951  cmovz   eax, ecx
0x180014954  jmp     loc_1800147A9
0x180014959  mov     rcx, r13; hMem
0x18001495c  call    freeWithSavedLastError
0x180014961  jmp     loc_1800147A7
```
