# AgCxFilesCleanup

- ea: `0x1800a9c18`
- end: `0x1800aa39d`
- name: `AgCxFilesCleanup`
- size: `1925`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180060d50`

## callees

- `0x180039f94`
- `0x180047ef0`
- `0x180052364`
- `0x1800a9a3c`
- `0x1800a9c18`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800aa130`
- `msvcrt!wcstoul` at `0x1800aa130`
- `msvcrt!wcsstr` at `0x1800a9f7a`
- `msvcrt!wcsstr` at `0x1800aa113`
- `msvcrt!wcsstr` at `0x1800aa15f`
- `msvcrt!wcsstr` at `0x1800a9f7a`
- `msvcrt!wcsstr` at `0x1800aa113`
- `msvcrt!wcsstr` at `0x1800aa15f`
- `msvcrt!_wcsupr` at `0x1800a9f69`
- `msvcrt!_wcsupr` at `0x1800a9f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa18b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa021`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa0e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa021`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aa0e0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a9d57`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800aa1b1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800a9d57`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800aa1b1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800aa37c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800aa37c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800aa011`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800aa011`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800aa0d0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800aa0d0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800aa038`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800aa038`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a9f52`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800a9f52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa05f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa091`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa0b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa05f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa091`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800aa0b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9cde`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a9cde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800aa177`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800aa177`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800a9caf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800a9caf`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800aa0c1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800aa0c1`

## pseudocode

```c
__int64 AgCxFilesCleanup()
{
  __int64 FirstFileW; // r12
  _QWORD *v1; // rsi
  DWORD LastError; // ebx
  _QWORD *v3; // rax
  __int64 v4; // rdi
  _QWORD *v5; // r15
  PSID *v6; // rbx
  DWORD LengthSid; // eax
  unsigned __int8 *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // r9
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  wchar_t *v21; // rax
  const wchar_t *v22; // rbx
  __int64 v23; // rcx
  DWORD v24; // ecx
  DWORD i; // edi
  void *v26; // r8
  unsigned int v28; // r14d
  const WCHAR *v29; // rbx
  BOOL v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  HLOCAL v33; // r11
  __int64 v34; // rbx
  __int64 v35; // r9
  unsigned __int8 *v36; // r8
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // r9
  __int64 v40; // r9
  __int64 v41; // r9
  __int64 v42; // r9
  __int64 v43; // r9
  __int64 v44; // r9
  PSID **v45; // rdi
  __int64 v46; // r10
  DWORD pCount; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-B8h]
  wchar_t *EndPtr; // [rsp+50h] [rbp-B0h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+60h] [rbp-A0h]
  PSID *v54; // [rsp+68h] [rbp-98h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  pCount = 0;
  v54 = 0;
  EndPtr = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v49 = 0;
  FirstFileW = -1;
  lpMem = 0;
  ppSessionInfo = 0;
  hMem = 0;
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    v1 = 0;
LABEL_3:
    LastError = GetLastError();
    goto LABEL_37;
  }
  v3 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 32LL * pCount);
  v1 = v3;
  if ( !v3 )
  {
LABEL_5:
    LastError = 8;
    goto LABEL_37;
  }
  memset_0(v3, 0, 32LL * pCount);
  v4 = 0;
  if ( pCount )
  {
    while ( (unsigned int)PfSvGetSessionUserInfo(ppSessionInfo[v4].SessionId, &v54) )
    {
LABEL_26:
      v4 = (unsigned int)(v4 + 1);
      if ( (unsigned int)v4 >= pCount )
        goto LABEL_27;
    }
    v5 = &v1[4 * (unsigned int)v4];
    v6 = v54;
    v5[2] = &ppSessionInfo[v4];
    v5[3] = v6;
    LengthSid = GetLengthSid(*v6);
    v8 = (unsigned __int8 *)*v6;
    v9 = 314159;
    v10 = LengthSid;
    if ( LengthSid >= 8uLL )
    {
      do
      {
        v10 -= 8;
        v11 = v8[7];
        v12 = 37
            * (v8[6] + 37 * (v8[5] + 37 * (v8[4] + 37 * (v8[3] + 37 * (v8[2] + 37 * (v8[1] + 37 * (*v8 + 37 * v9)))))));
        v8 += 8;
        v9 = v11 + v12;
      }
      while ( v10 >= 8 );
    }
    v13 = v10 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              v18 = v17 - 1;
              if ( v18 )
              {
                if ( v18 != 1 )
                {
LABEL_24:
                  v5[1] = v9;
                  if ( !(unsigned int)PfDbRehashIfNeededEx(0, &v49, v8) )
                    goto LABEL_5;
                  v53 = v5[1] & (-1LL << (BYTE4(v49) & 0x1F));
                  v19 = lpMem;
                  v20 = ((HIDWORD(v49) >> 5) - 1)
                      & (HIBYTE(v53)
                       + 37
                       * (BYTE6(v53)
                        + 37
                        * (BYTE5(v53)
                         + 37
                         * (BYTE4(v53)
                          + 37
                          * (BYTE3(v53) + 37 * (BYTE2(v53) + 37 * (BYTE1(v53) + 37 * ((unsigned __int8)v53 + 11623883))))))));
                  *v5 = *((_QWORD *)lpMem + v20);
                  v19[v20] = v5;
                  LODWORD(v49) = v49 + 1;
                  goto LABEL_26;
                }
                v9 = *v8++ + 37 * v9;
              }
              v9 = *v8++ + 37 * v9;
            }
            v9 = *v8++ + 37 * v9;
          }
          v9 = *v8++ + 37 * v9;
        }
        v9 = *v8++ + 37 * v9;
      }
      v9 = *v8++ + 37 * v9;
    }
    v9 = *v8 + 37 * v9;
    goto LABEL_24;
  }
LABEL_27:
  StringCbPrintfW(pszDest, 0x208u, L"%ws\\AgCx_*.db", *(_QWORD *)&PfSvcGlobals + 888LL);
  FirstFileW = (__int64)FindFirstFileW(pszDest, &FindFileData);
  if ( FirstFileW == -1 )
    goto LABEL_3;
  do
  {
    _wcsupr(FindFileData.cFileName);
    v21 = wcsstr(FindFileData.cFileName, L"AGCX_");
    if ( v21[5] != 83 )
      goto LABEL_33;
    v22 = v21 + 6;
    if ( v21[6] != 67 )
    {
      if ( !wcsstr(v21 + 6, L".SNP.DB") || (v28 = wcstoul(v22, &EndPtr, 10), v22 == EndPtr) || *EndPtr != 95 )
      {
LABEL_32:
        StringCbPrintfW(pszDest, 0x208u, L"%ws\\%ws", *(_QWORD *)&PfSvcGlobals + 888LL, FindFileData.cFileName);
        DeleteFileW(pszDest);
        goto LABEL_33;
      }
      v29 = EndPtr + 1;
      EndPtr = wcsstr(EndPtr + 1, L".SNP.DB");
      *EndPtr = 0;
      v30 = ConvertStringSidToSidW(v29, &hMem);
      *EndPtr = 46;
      if ( !v30 )
      {
        v31 = GetLastError();
        LastError = v31;
        if ( v31 != 1337 && v31 != 87 )
          goto LABEL_37;
        goto LABEL_32;
      }
      v32 = GetLengthSid(hMem);
      v33 = hMem;
      v34 = 314159;
      v35 = v32;
      v36 = (unsigned __int8 *)hMem;
      if ( v32 >= 8uLL )
      {
        do
        {
          v35 -= 8;
          v37 = v36[6]
              + 37 * (v36[5] + 37 * (v36[4] + 37 * (v36[3] + 37 * (v36[2] + 37 * (v36[1] + 37 * (*v36 + 37 * v34))))));
          v38 = v36[7];
          v36 += 8;
          v34 = v38 + 37 * v37;
        }
        while ( v35 >= 8 );
      }
      v39 = v35 - 1;
      if ( v39 )
      {
        v40 = v39 - 1;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            v42 = v41 - 1;
            if ( v42 )
            {
              v43 = v42 - 1;
              if ( v43 )
              {
                v44 = v43 - 1;
                if ( v44 )
                {
                  if ( v44 != 1 )
                  {
LABEL_75:
                    v45 = 0;
LABEL_76:
                    v46 = v34 & (-1LL << (BYTE4(v49) & 0x1F));
                    if ( v45 )
                      goto LABEL_79;
                    if ( HIDWORD(v49) >> 5 )
                    {
                      v53 = v34 & (-1LL << (BYTE4(v49) & 0x1F));
                      v45 = (PSID **)((char *)lpMem
                                    + 8
                                    * (((HIDWORD(v49) >> 5) - 1)
                                     & (HIBYTE(v46)
                                      + 37
                                      * (BYTE6(v46)
                                       + 37
                                       * (BYTE5(v46)
                                        + 37
                                        * (BYTE4(v46)
                                         + 37
                                         * (BYTE3(v46)
                                          + 37
                                          * (BYTE2(v46) + 37 * (BYTE1(v46) + 37 * ((unsigned __int8)v46 + 11623883))))))))));
LABEL_79:
                      while ( 1 )
                      {
                        v45 = (PSID **)*v45;
                        if ( ((unsigned __int8)v45 & 1) != 0 )
                          break;
                        if ( v46 == ((-1LL << (BYTE4(v49) & 0x1F)) & (unsigned __int64)v45[1]) )
                        {
                          if ( !v45 )
                            goto LABEL_32;
                          if ( !EqualSid(v33, *v45[3]) || v28 != *(_DWORD *)v45[2] )
                          {
                            v33 = hMem;
                            goto LABEL_76;
                          }
                          goto LABEL_33;
                        }
                      }
                    }
                    goto LABEL_32;
                  }
                  v34 = *v36++ + 37 * v34;
                }
                v34 = *v36++ + 37 * v34;
              }
              v34 = *v36++ + 37 * v34;
            }
            v34 = *v36++ + 37 * v34;
          }
          v34 = *v36++ + 37 * v34;
        }
        v34 = *v36++ + 37 * v34;
      }
      v34 = *v36 + 37 * v34;
      goto LABEL_75;
    }
    if ( v21[7] == 51 )
    {
      StringCbPrintfW(pszDest, 0x208u, L"%ws\\%ws", *(_QWORD *)&PfSvcGlobals + 888LL, FindFileData.cFileName);
      if ( (unsigned int)AgCxFUSDbDeleteCheck(v23, pszDest) )
        goto LABEL_32;
    }
LABEL_33:
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
  }
  while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
  LastError = 0;
LABEL_37:
  if ( lpMem )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, lpMem);
  if ( v1 )
  {
    v24 = pCount;
    for ( i = 0; i < v24; ++i )
    {
      v26 = (void *)v1[4 * i + 3];
      if ( v26 )
      {
        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v26);
        v24 = pCount;
      }
    }
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v1);
  }
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  if ( hMem )
    LocalFree(hMem);
  return LastError;
}

```

## disassembly

```asm
0x1800a9c18  push    rbp
0x1800a9c1a  push    rbx
0x1800a9c1b  push    rsi
0x1800a9c1c  push    rdi
0x1800a9c1d  push    r12
0x1800a9c1f  push    r14
0x1800a9c21  push    r15
0x1800a9c23  lea     rbp, [rsp-3E0h]
0x1800a9c2b  sub     rsp, 4E0h
0x1800a9c32  mov     rax, cs:__security_cookie
0x1800a9c39  xor     rax, rsp
0x1800a9c3c  mov     [rbp+410h+var_40], rax
0x1800a9c43  xor     edx, edx; Val
0x1800a9c45  mov     [rsp+510h+var_4E0], 0
0x1800a9c4d  mov     r8d, 250h; Size
0x1800a9c53  mov     [rsp+510h+var_4A8], 0
0x1800a9c5c  lea     rcx, [rsp+510h+FindFileData]; void *
0x1800a9c61  mov     [rsp+510h+EndPtr], 0
0x1800a9c6a  call    memset_0
0x1800a9c6f  lea     rax, [rsp+510h+var_4E0]
0x1800a9c74  mov     [rsp+510h+var_4D0], 0
0x1800a9c7d  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a9c81  mov     [rsp+510h+lpMem], 0
0x1800a9c8a  lea     r9, [rsp+510h+ppSessionInfo]; ppSessionInfo
0x1800a9c8f  mov     [rsp+510h+ppSessionInfo], 0
0x1800a9c98  xor     edx, edx; Reserved
0x1800a9c9a  mov     [rsp+510h+hMem], 0
0x1800a9ca3  xor     ecx, ecx; hServer
0x1800a9ca5  mov     [rsp+510h+pCount], rax; pCount
0x1800a9caa  lea     r8d, [r12+2]; Version
0x1800a9caf  call    cs:__imp_WTSEnumerateSessionsW
0x1800a9cb5  test    eax, eax
0x1800a9cb7  jnz     short loc_1800A9CC8
0x1800a9cb9  xor     esi, esi
0x1800a9cbb  call    cs:__imp_GetLastError
0x1800a9cc1  mov     ebx, eax
0x1800a9cc3  jmp     loc_1800AA048
0x1800a9cc8  mov     rcx, cs:PfSvcGlobals
0x1800a9ccf  xor     edx, edx; dwFlags
0x1800a9cd1  mov     r8d, [rsp+510h+var_4E0]
0x1800a9cd6  shl     r8, 5; dwBytes
0x1800a9cda  mov     rcx, [rcx+58h]; hHeap
0x1800a9cde  call    cs:__imp_HeapAlloc
0x1800a9ce4  mov     rsi, rax
0x1800a9ce7  test    rax, rax
0x1800a9cea  jnz     short loc_1800A9CF6
0x1800a9cec  mov     ebx, 8
0x1800a9cf1  jmp     loc_1800AA048
0x1800a9cf6  mov     r8d, [rsp+510h+var_4E0]
0x1800a9cfb  xor     edx, edx; Val
0x1800a9cfd  shl     r8, 5; Size
0x1800a9d01  mov     rcx, rsi; void *
0x1800a9d04  call    memset_0
0x1800a9d09  xor     edi, edi
0x1800a9d0b  cmp     [rsp+510h+var_4E0], edi
0x1800a9d0f  jbe     loc_1800A9F1C
0x1800a9d15  mov     rcx, [rsp+510h+ppSessionInfo]
0x1800a9d1a  lea     r14, [rdi+rdi*2]
0x1800a9d1e  lea     rdx, [rsp+510h+var_4A8]
0x1800a9d23  mov     ebx, edi
0x1800a9d25  mov     ecx, [rcx+r14*8]
0x1800a9d29  call    PfSvGetSessionUserInfo
0x1800a9d2e  test    eax, eax
0x1800a9d30  jnz     loc_1800A9F10
0x1800a9d36  mov     rax, [rsp+510h+ppSessionInfo]
0x1800a9d3b  shl     rbx, 5
0x1800a9d3f  lea     rcx, [rax+r14*8]
0x1800a9d43  lea     r15, [rbx+rsi]
0x1800a9d47  mov     rbx, [rsp+510h+var_4A8]
0x1800a9d4c  mov     [r15+10h], rcx
0x1800a9d50  mov     [r15+18h], rbx
0x1800a9d54  mov     rcx, [rbx]; pSid
0x1800a9d57  call    cs:__imp_GetLengthSid
0x1800a9d5d  mov     r8, [rbx]
0x1800a9d60  mov     ecx, 4CB2Fh
0x1800a9d65  mov     r9d, eax
0x1800a9d68  cmp     r9, 8
0x1800a9d6c  jb      short loc_1800A9DDB
0x1800a9d6e  movzx   eax, byte ptr [r8]
0x1800a9d72  sub     r9, 8
0x1800a9d76  imul    rcx, 25h ; '%'
0x1800a9d7a  add     rcx, rax
0x1800a9d7d  movzx   eax, byte ptr [r8+1]
0x1800a9d82  imul    rdx, rcx, 25h ; '%'
0x1800a9d86  add     rdx, rax
0x1800a9d89  movzx   eax, byte ptr [r8+2]
0x1800a9d8e  imul    rcx, rdx, 25h ; '%'
0x1800a9d92  add     rcx, rax
0x1800a9d95  movzx   eax, byte ptr [r8+3]
0x1800a9d9a  imul    rdx, rcx, 25h ; '%'
0x1800a9d9e  add     rdx, rax
0x1800a9da1  movzx   eax, byte ptr [r8+4]
0x1800a9da6  imul    rcx, rdx, 25h ; '%'
0x1800a9daa  add     rcx, rax
0x1800a9dad  movzx   eax, byte ptr [r8+5]
0x1800a9db2  imul    rdx, rcx, 25h ; '%'
0x1800a9db6  add     rdx, rax
0x1800a9db9  movzx   eax, byte ptr [r8+6]
0x1800a9dbe  imul    rcx, rdx, 25h ; '%'
0x1800a9dc2  add     rcx, rax
0x1800a9dc5  movzx   eax, byte ptr [r8+7]
0x1800a9dca  imul    rcx, 25h ; '%'
0x1800a9dce  add     r8, 8
0x1800a9dd2  add     rcx, rax
0x1800a9dd5  cmp     r9, 8
0x1800a9dd9  jge     short loc_1800A9D6E
0x1800a9ddb  sub     r9, 1
0x1800a9ddf  jz      short loc_1800A9E59
0x1800a9de1  sub     r9, 1
0x1800a9de5  jz      short loc_1800A9E4B
0x1800a9de7  sub     r9, 1
0x1800a9deb  jz      short loc_1800A9E3D
0x1800a9ded  sub     r9, 1
0x1800a9df1  jz      short loc_1800A9E2F
0x1800a9df3  sub     r9, 1
0x1800a9df7  jz      short loc_1800A9E21
0x1800a9df9  sub     r9, 1
0x1800a9dfd  jz      short loc_1800A9E13
0x1800a9dff  cmp     r9, 1
0x1800a9e03  jnz     short loc_1800A9E64
0x1800a9e05  movzx   eax, byte ptr [r8]
0x1800a9e09  imul    rcx, 25h ; '%'
0x1800a9e0d  add     rcx, rax
0x1800a9e10  inc     r8
0x1800a9e13  movzx   eax, byte ptr [r8]
0x1800a9e17  imul    rcx, 25h ; '%'
0x1800a9e1b  add     rcx, rax
0x1800a9e1e  inc     r8
0x1800a9e21  movzx   eax, byte ptr [r8]
0x1800a9e25  imul    rcx, 25h ; '%'
0x1800a9e29  add     rcx, rax
0x1800a9e2c  inc     r8
0x1800a9e2f  movzx   eax, byte ptr [r8]
0x1800a9e33  imul    rcx, 25h ; '%'
0x1800a9e37  add     rcx, rax
0x1800a9e3a  inc     r8
0x1800a9e3d  movzx   eax, byte ptr [r8]
0x1800a9e41  imul    rcx, 25h ; '%'
0x1800a9e45  add     rcx, rax
0x1800a9e48  inc     r8
0x1800a9e4b  movzx   eax, byte ptr [r8]
0x1800a9e4f  imul    rcx, 25h ; '%'
0x1800a9e53  add     rcx, rax
0x1800a9e56  inc     r8
0x1800a9e59  movzx   eax, byte ptr [r8]
0x1800a9e5d  imul    rcx, 25h ; '%'
0x1800a9e61  add     rcx, rax
0x1800a9e64  mov     [r15+8], rcx
0x1800a9e68  lea     rdx, [rsp+510h+var_4D0]
0x1800a9e6d  xor     ecx, ecx
0x1800a9e6f  call    PfDbRehashIfNeededEx
0x1800a9e74  test    eax, eax
0x1800a9e76  jz      loc_1800A9CEC
0x1800a9e7c  mov     r8d, dword ptr [rsp+510h+var_4D0+4]
0x1800a9e81  lea     r9, [rsp+510h+var_4B0]
0x1800a9e86  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a9e8a  mov     ecx, r8d
0x1800a9e8d  and     ecx, 1Fh
0x1800a9e90  shr     r8d, 5
0x1800a9e94  shl     rax, cl
0x1800a9e97  and     rax, [r15+8]
0x1800a9e9b  mov     [rsp+510h+var_4B0], rax
0x1800a9ea0  movzx   eax, byte ptr [r9]
0x1800a9ea4  add     eax, 0B15DCBh
0x1800a9ea9  imul    ecx, eax, 25h ; '%'
0x1800a9eac  movzx   eax, byte ptr [r9+1]
0x1800a9eb1  add     ecx, eax
0x1800a9eb3  movzx   eax, byte ptr [r9+2]
0x1800a9eb8  imul    edx, ecx, 25h ; '%'
0x1800a9ebb  add     edx, eax
0x1800a9ebd  movzx   eax, byte ptr [r9+3]
0x1800a9ec2  imul    ecx, edx, 25h ; '%'
0x1800a9ec5  add     ecx, eax
0x1800a9ec7  movzx   eax, byte ptr [r9+4]
0x1800a9ecc  imul    edx, ecx, 25h ; '%'
0x1800a9ecf  add     edx, eax
0x1800a9ed1  movzx   eax, byte ptr [r9+5]
0x1800a9ed6  imul    ecx, edx, 25h ; '%'
0x1800a9ed9  add     ecx, eax
0x1800a9edb  movzx   eax, byte ptr [r9+6]
0x1800a9ee0  imul    edx, ecx, 25h ; '%'
0x1800a9ee3  mov     rcx, [rsp+510h+lpMem]
0x1800a9ee8  add     edx, eax
0x1800a9eea  movzx   eax, byte ptr [r9+7]
0x1800a9eef  imul    edx, 25h ; '%'
0x1800a9ef2  add     edx, eax
0x1800a9ef4  lea     eax, [r8-1]
0x1800a9ef8  and     rdx, rax
0x1800a9efb  mov     rax, [rcx+rdx*8]
0x1800a9eff  mov     [r15], rax
0x1800a9f02  mov     [rcx+rdx*8], r15
0x1800a9f06  mov     eax, dword ptr [rsp+510h+var_4D0]
0x1800a9f0a  inc     eax
0x1800a9f0c  mov     dword ptr [rsp+510h+var_4D0], eax
0x1800a9f10  inc     edi
0x1800a9f12  cmp     edi, [rsp+510h+var_4E0]
0x1800a9f16  jb      loc_1800A9D15
0x1800a9f1c  mov     r9, cs:PfSvcGlobals
0x1800a9f23  lea     r8, aWsAgcxDb; "%ws\\AgCx_*.db"
0x1800a9f2a  mov     r15d, 208h
0x1800a9f30  lea     rcx, [rbp+410h+pszDest]; pszDest
0x1800a9f37  add     r9, 378h
0x1800a9f3e  mov     edx, r15d; cbDest
0x1800a9f41  call    StringCbPrintfW
0x1800a9f46  lea     rdx, [rsp+510h+FindFileData]; lpFindFileData
0x1800a9f4b  lea     rcx, [rbp+410h+pszDest]; lpFileName
0x1800a9f52  call    cs:__imp_FindFirstFileW
0x1800a9f58  mov     r12, rax
0x1800a9f5b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a9f5f  jz      loc_1800A9CBB
0x1800a9f65  lea     rcx, [rbp+410h+FindFileData.cFileName]; String
0x1800a9f69  call    cs:__imp__wcsupr
0x1800a9f6f  lea     rdx, aAgcx; "AGCX_"
0x1800a9f76  lea     rcx, [rbp+410h+FindFileData.cFileName]; Str
0x1800a9f7a  call    cs:__imp_wcsstr
0x1800a9f80  cmp     word ptr [rax+0Ah], 53h ; 'S'
0x1800a9f85  jnz     loc_1800AA017
0x1800a9f8b  lea     rbx, [rax+0Ch]
0x1800a9f8f  cmp     word ptr [rbx], 43h ; 'C'
0x1800a9f93  jnz     loc_1800AA109
0x1800a9f99  cmp     word ptr [rbx+2], 33h ; '3'
0x1800a9f9e  jnz     short loc_1800AA017
0x1800a9fa0  mov     r9, cs:PfSvcGlobals
0x1800a9fa7  lea     rax, [rbp+410h+FindFileData.cFileName]
0x1800a9fab  add     r9, 378h
0x1800a9fb2  mov     [rsp+510h+pCount], rax
0x1800a9fb7  lea     r8, aWsWs_0; "%ws\\%ws"
0x1800a9fbe  mov     rdx, r15; cbDest
0x1800a9fc1  lea     rcx, [rbp+410h+pszDest]; pszDest
0x1800a9fc8  call    StringCbPrintfW
0x1800a9fcd  lea     rdx, [rbp+410h+pszDest]
0x1800a9fd4  call    AgCxFUSDbDeleteCheck
0x1800a9fd9  test    eax, eax
0x1800a9fdb  jz      short loc_1800AA017
0x1800a9fdd  mov     r9, cs:PfSvcGlobals
0x1800a9fe4  lea     rax, [rbp+410h+FindFileData.cFileName]
0x1800a9fe8  add     r9, 378h
0x1800a9fef  mov     [rsp+510h+pCount], rax
0x1800a9ff4  lea     r8, aWsWs_0; "%ws\\%ws"
0x1800a9ffb  mov     rdx, r15; cbDest
0x1800a9ffe  lea     rcx, [rbp+410h+pszDest]; pszDest
0x1800aa005  call    StringCbPrintfW
0x1800aa00a  lea     rcx, [rbp+410h+pszDest]; lpFileName
0x1800aa011  call    cs:__imp_DeleteFileW
0x1800aa017  mov     rcx, [rsp+510h+hMem]; hMem
0x1800aa01c  test    rcx, rcx
0x1800aa01f  jz      short loc_1800AA030
0x1800aa021  call    cs:__imp_LocalFree
0x1800aa027  mov     [rsp+510h+hMem], 0
0x1800aa030  lea     rdx, [rsp+510h+FindFileData]; lpFindFileData
0x1800aa035  mov     rcx, r12; hFindFile
0x1800aa038  call    cs:__imp_FindNextFileW
0x1800aa03e  test    eax, eax
0x1800aa040  jnz     loc_1800A9F65
0x1800aa046  xor     ebx, ebx
0x1800aa048  mov     r8, [rsp+510h+lpMem]; lpMem
0x1800aa04d  test    r8, r8
0x1800aa050  jz      short loc_1800AA065
0x1800aa052  mov     rcx, cs:PfSvcGlobals
0x1800aa059  xor     edx, edx; dwFlags
0x1800aa05b  mov     rcx, [rcx+58h]; hHeap
0x1800aa05f  call    cs:__imp_HeapFree
0x1800aa065  test    rsi, rsi
0x1800aa068  jz      short loc_1800AA0B7
0x1800aa06a  mov     ecx, [rsp+510h+var_4E0]
0x1800aa06e  xor     edi, edi
0x1800aa070  test    ecx, ecx
0x1800aa072  jz      short loc_1800AA0A1
0x1800aa074  mov     eax, edi
0x1800aa076  shl     rax, 5
0x1800aa07a  mov     r8, [rax+rsi+18h]; lpMem
0x1800aa07f  test    r8, r8
0x1800aa082  jz      short loc_1800AA09B
0x1800aa084  mov     rcx, cs:PfSvcGlobals
0x1800aa08b  xor     edx, edx; dwFlags
0x1800aa08d  mov     rcx, [rcx+58h]; hHeap
0x1800aa091  call    cs:__imp_HeapFree
0x1800aa097  mov     ecx, [rsp+510h+var_4E0]
0x1800aa09b  inc     edi
0x1800aa09d  cmp     edi, ecx
0x1800aa09f  jb      short loc_1800AA074
0x1800aa0a1  mov     rcx, cs:PfSvcGlobals
0x1800aa0a8  mov     r8, rsi; lpMem
0x1800aa0ab  xor     edx, edx; dwFlags
0x1800aa0ad  mov     rcx, [rcx+58h]; hHeap
0x1800aa0b1  call    cs:__imp_HeapFree
0x1800aa0b7  mov     rcx, [rsp+510h+ppSessionInfo]; pMemory
0x1800aa0bc  test    rcx, rcx
0x1800aa0bf  jz      short loc_1800AA0C7
0x1800aa0c1  call    cs:__imp_WTSFreeMemory
0x1800aa0c7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1800aa0cb  jz      short loc_1800AA0D6
0x1800aa0cd  mov     rcx, r12; hFindFile
0x1800aa0d0  call    cs:__imp_FindClose
0x1800aa0d6  mov     rcx, [rsp+510h+hMem]; hMem
0x1800aa0db  test    rcx, rcx
0x1800aa0de  jz      short loc_1800AA0E6
0x1800aa0e0  call    cs:__imp_LocalFree
0x1800aa0e6  mov     eax, ebx
0x1800aa0e8  mov     rcx, [rbp+410h+var_40]
  ... truncated ...
```
