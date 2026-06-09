# _CmiCollectMatchingInfoDir(void *,tagRECINFO *,ulong,ushort const *,ushort *,ushort *,int,tagCMIPFN *)

- ea: `0x180033948`
- end: `0x1800343b1`
- name: `?_CmiCollectMatchingInfoDir@@YA?AW4CMI_RESULT@@PEAXPEAUtagRECINFO@@KPEBGPEAG3HPEAUtagCMIPFN@@@Z`
- size: `2665`
- prototype: `__int64 __fastcall(void *, _DWORD *, int, const WCHAR *, unsigned __int16 *, unsigned __int16 *, int, __int64)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004fa8`
- `0x180033948`

## callees

- `0x180004ed0`
- `0x1800052d0`
- `0x180013688`
- `0x180018f0c`
- `0x180029044`
- `0x18002ad28`
- `0x18003359c`
- `0x180033948`
- `0x18004c940`
- `0x180050db0`
- `0x180051754`
- `0x1800517cc`
- `0x1800aa06c`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033a30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033a30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034386`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034386`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341b4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003413a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003436d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003413a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003436d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180034129`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180034292`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180034129`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180034292`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033b3a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033b61`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033c76`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800340e9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003431b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033b3a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033b61`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033c76`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800340e9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003431b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180033aae`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800341a0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180033aae`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800341a0`

## string_xrefs

- `0x180033acb`: `[_CmiCollectMatchingInfoDir] FindFirstFile failed (error code=%d) (path=%S).\n`
- `0x1800341bd`: `[_CmiCollectMatchingInfoDir] FindFirstFile failed (error code=%d) (path=%S).\n`
- `0x180033afa`: `<?xml version="1.0" encoding="UTF-16"?>\n<DATABASE>\n`

## pseudocode

```c
__int64 __fastcall _CmiCollectMatchingInfoDir(
        void *a1,
        _DWORD *a2,
        int a3,
        const WCHAR *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7,
        __int64 a8)
{
  const WCHAR *v8; // r12
  unsigned __int16 v9; // bx
  unsigned int v10; // edi
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 v13; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rbx
  __int64 v16; // rax
  unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // rcx
  DWORD LastError; // eax
  unsigned __int16 *v20; // rsi
  HANDLE v21; // r15
  __int64 v22; // r8
  unsigned __int16 *v23; // rsi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  unsigned __int16 *v27; // r15
  unsigned __int16 *v28; // rdx
  unsigned __int16 *cFileName; // rcx
  int v30; // ecx
  const unsigned __int16 *v31; // rax
  __int64 v32; // rcx
  int v33; // esi
  unsigned int (__fastcall **v34)(const WCHAR *, __int64 *, char *); // rdi
  unsigned __int16 *v35; // r14
  int v36; // r13d
  unsigned int v37; // r15d
  __int64 v38; // r12
  __int64 v39; // rdi
  __int64 v40; // rdx
  __int64 v41; // r8
  _DWORD *v42; // rcx
  unsigned int v43; // eax
  unsigned __int64 v44; // r15
  unsigned __int16 *v45; // rdi
  DWORD v46; // eax
  unsigned int v47; // r10d
  __int64 v48; // r8
  HANDLE v49; // rax
  __int64 v51; // [rsp+40h] [rbp-C0h]
  __int64 NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v53; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 FirstFileW; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v60; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v61; // [rsp+90h] [rbp-70h]
  const WCHAR *v62; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v63; // [rsp+A0h] [rbp-60h]
  _DWORD *v64; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v65; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v66; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *Extension; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v68[2]; // [rsp+D0h] [rbp-30h] BYREF
  const WCHAR *v69; // [rsp+D8h] [rbp-28h]
  _BYTE v70[256]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v71[256]; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+2E0h] [rbp+1E0h] BYREF

  v8 = a4;
  v9 = a3;
  v60 = a5;
  v64 = a2;
  hFile = a1;
  v59 = a8;
  v62 = a4;
  LODWORD(v56) = a3;
  v66 = a6;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v53 = 0;
  v10 = 0;
  v58 = 0;
  LODWORD(NumberOfBytesWritten) = 0;
  HIDWORD(v55) = 0;
  LODWORD(v51) = 0;
  if ( a6 )
  {
    if ( a6 >= v8 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v8[v11] );
      if ( &v8[v11] >= a6 )
      {
        v12 = v9;
        HIDWORD(v51) = v9;
        if ( !a7 || (unsigned int)v9 - 4 > 1 )
        {
          v13 = -1;
          ProcessHeap = GetProcessHeap();
          v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x2000u);
          if ( !v15 )
            goto LABEL_141;
          v16 = -1;
          do
            ++v16;
          while ( a6[v16] );
          v17 = v60;
          v18 = &a6[v16];
          v63 = v18;
          v65 = 4096 - (v18 - v8);
          if ( (_DWORD)v12 != 5 )
            v17 = L"*";
          if ( (int)StringCchCopyW(v18, 4096 - (v18 - v8), v17) < 0 )
            goto LABEL_141;
          FirstFileW = (__int64)FindFirstFileW(v8, &FindFileData);
          v13 = FirstFileW;
          if ( FirstFileW == -1 )
          {
            LastError = GetLastError();
            _CmiDebugPrintA(
              "[_CmiCollectMatchingInfoDir] FindFirstFile failed (error code=%d) (path=%S).\n",
              LastError,
              v8);
            goto LABEL_141;
          }
          v61 = 0;
          v20 = 0;
          if ( a7 )
          {
            v21 = hFile;
            goto LABEL_36;
          }
          if ( v64[6] )
          {
            *v63 = 0;
            if ( (int)StringCchPrintfW(v15, 0x1000u, L"<?xml version=\"1.0\" encoding=\"UTF-16\"?>\r\n<DATABASE>\r\n") < 0 )
              goto LABEL_141;
            v21 = hFile;
            WriteFile(hFile, byte_1800D9370, 2u, (LPDWORD)&NumberOfBytesWritten, 0);
            v22 = -1;
            do
              ++v22;
            while ( v15[v22] );
            WriteFile(v21, v15, 2 * v22, (LPDWORD)&NumberOfBytesWritten, 0);
          }
          else
          {
            v21 = hFile;
          }
          v23 = v60;
          if ( (_DWORD)v12 != 4 )
            goto LABEL_31;
          v24 = -1;
          do
            ++v24;
          while ( v60[v24] );
          if ( (int)StringCchCopyW(v60, v24 + 1, L"SYSTEM INFO") >= 0 )
          {
LABEL_31:
            if ( (int)StringCchPrintfExW(v15, 0x1000u, 0, &v53, 0, L"<EXE NAME=\"") >= 0
              && _CmiSanitizeXML(&v15[4096 - (int)v53], v53, v23) )
            {
              v25 = -1;
              do
                ++v25;
              while ( v15[v25] );
              if ( (int)StringCchPrintfExW(
                          &v15[(int)v25],
                          (unsigned int)(4096 - v25),
                          0,
                          &v53,
                          0,
                          L"\" FILTER=\"%s\">\r\n",
                          (&g_szFilterDesc)[v12]) >= 0 )
              {
                v20 = v15;
                v61 = v15;
                v26 = -1;
                do
                  ++v26;
                while ( v15[v26] );
                WriteFile(v21, v15, 2 * v26, (LPDWORD)&NumberOfBytesWritten, 0);
LABEL_36:
                LODWORD(v55) = 0;
                if ( (_DWORD)v12 == 1 || (unsigned int)(v12 - 4) <= 1 )
                  LODWORD(v55) = 10;
                while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
LABEL_109:
                  if ( !FindNextFileW((HANDLE)v13, &FindFileData) )
                  {
                    FindClose((HANDLE)v13);
                    v13 = -1;
                    FirstFileW = -1;
                    if ( (unsigned int)(v12 - 4) <= 1 )
                    {
LABEL_125:
                      v21 = hFile;
LABEL_126:
                      v10 = v51;
                      if ( !a7 )
                      {
                        v13 = FirstFileW;
                        goto LABEL_128;
                      }
LABEL_134:
                      v13 = FirstFileW;
                      if ( v10 != -1 )
                        v10 = 1;
                    }
                    else
                    {
                      if ( a7 < 3 && (int)v56 >= 0 )
                      {
                        v44 = v65;
                        v45 = v63;
                        if ( (int)StringCchCopyW(v63, v65, L"*") >= 0 )
                        {
                          FirstFileW = (__int64)FindFirstFileW(v8, &FindFileData);
                          v13 = FirstFileW;
                          if ( FirstFileW != -1 )
                          {
                            while ( 1 )
                            {
                              if ( (FindFileData.dwFileAttributes & 0x10) != 0
                                && (FindFileData.cFileName[0] != 46
                                 || FindFileData.cFileName[1]
                                 && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
                              {
                                if ( (int)StringCchCopyW(v45, v44, FindFileData.cFileName) < 0
                                  || (int)StringCchCatW(v45, v44, L"\\") < 0 )
                                {
                                  goto LABEL_140;
                                }
                                LODWORD(v51) = _CmiCollectMatchingInfoDir(
                                                 hFile,
                                                 v64,
                                                 (unsigned int)v56,
                                                 v8,
                                                 0,
                                                 v66,
                                                 a7 + 1,
                                                 v59,
                                                 v51,
                                                 NumberOfBytesWritten,
                                                 v53,
                                                 hFile,
                                                 v55,
                                                 v56,
                                                 FirstFileW);
                                if ( (_DWORD)v51 == -1 )
                                  goto LABEL_125;
                              }
                              if ( !FindNextFileW((HANDLE)v13, &FindFileData) )
                                goto LABEL_125;
                            }
                          }
                          v46 = GetLastError();
                          _CmiDebugPrintA(
                            "[_CmiCollectMatchingInfoDir] FindFirstFile failed (error code=%d) (path=%S).\n",
                            v46,
                            v8);
                        }
LABEL_140:
                        v10 = v51;
                        goto LABEL_141;
                      }
                      v10 = 1;
                      if ( a7 )
                        goto LABEL_141;
LABEL_128:
                      if ( (int)StringCchCopyW(v20, 0x1000u, L"</EXE>\r\n") >= 0
                        && ((v56 & 0x10000000) != 0 || (int)StringCchCatW(v20, v47, L"</DATABASE>\r\n") >= 0) )
                      {
                        v48 = -1;
                        do
                          ++v48;
                        while ( v20[v48] );
                        WriteFile(v21, v20, 2 * v48, (LPDWORD)&NumberOfBytesWritten, 0);
                        goto LABEL_134;
                      }
                    }
                    goto LABEL_141;
                  }
                }
                if ( (int)StringCchCopyW(v63, v65, FindFileData.cFileName) < 0 )
                  goto LABEL_140;
                Extension = PathFindExtension(v8);
                v27 = Extension;
                if ( (unsigned int)v12 < 2 )
                {
                  if ( aExe[0] )
                  {
                    do
                    {
                      if ( v27 && !wcsicmp(v27, (const wchar_t *)(&g_szGrabmiFilterNormal)[v10]) )
                        break;
                      ++v10;
                    }
                    while ( *(_WORD *)(&g_szGrabmiFilterNormal)[v10] );
                    v8 = v62;
                    LODWORD(v12) = HIDWORD(v51);
                  }
                  if ( *(_WORD *)(&g_szGrabmiFilterNormal)[v10] )
                    goto LABEL_64;
                  goto LABEL_62;
                }
                switch ( (_DWORD)v12 )
                {
                  case 2:
                    if ( !Extension )
                      goto LABEL_65;
                    v28 = L".sys";
                    cFileName = Extension;
                    break;
                  case 4:
                    if ( *(_WORD *)g_szGrabmiFilterSystem )
                    {
                      do
                      {
                        if ( !wcsicmp(FindFileData.cFileName, (const wchar_t *)(&g_szGrabmiFilterSystem)[v10]) )
                          break;
                        ++v10;
                      }
                      while ( *(_WORD *)(&g_szGrabmiFilterSystem)[v10] );
                      v8 = v62;
                      v20 = v61;
                    }
                    v30 = *(_WORD *)(&g_szGrabmiFilterSystem)[v10] == 0;
LABEL_54:
                    if ( !v30 )
                      goto LABEL_64;
LABEL_62:
                    if ( (int)v55 >= 10 )
                    {
                      v10 = 0;
LABEL_108:
                      v21 = hFile;
                      goto LABEL_109;
                    }
                    LODWORD(v55) = v55 + 1;
LABEL_64:
                    if ( (_DWORD)v12 != 2 )
                    {
                      v31 = L"    <MATCHING_FILE NAME=\"";
LABEL_67:
                      if ( (int)StringCchPrintfExW(v15, 0x1000u, 0, &v53, 0, v31) < 0 )
                        goto LABEL_140;
                      if ( !_CmiSanitizeXML(&v15[4096 - (int)v53], v53, v66) )
                        goto LABEL_140;
                      v32 = -1;
                      do
                        ++v32;
                      while ( v15[v32] );
                      if ( (int)StringCchPrintfExW(&v15[(int)v32], (unsigned int)(4096 - v32), 0, &v53, 0, L"\" ") < 0 )
                        goto LABEL_140;
                      v33 = 4096 - v53;
                      v34 = (unsigned int (__fastcall **)(const WCHAR *, __int64 *, char *))v59;
                      v35 = &v15[4096 - (int)v53];
                      if ( v58 )
                      {
                        (*(void (**)(void))(v59 + 16))();
                        v58 = 0;
                      }
                      if ( (*v34)(v8, &v58, (char *)&v55 + 4) )
                      {
                        v36 = 0;
                        if ( HIDWORD(v55) )
                        {
                          while ( 1 )
                          {
                            v37 = 4096 - v33;
                            v38 = 16LL * v36;
                            if ( v34[1]((const WCHAR *)(v38 + v58), (__int64 *)v35, (char *)(unsigned int)(4096 - v33)) )
                            {
                              v39 = -1;
                              do
                                ++v39;
                              while ( v35[v39] );
                              if ( HIDWORD(v51) != 2
                                || *(_WORD *)(v38 + v58) == 16413
                                || *(_WORD *)(v38 + v58) == 16414
                                || *(_WORD *)(v38 + v58) == 20483
                                || *(_WORD *)(v38 + v58) == 20486 )
                              {
                                if ( v37 > 5 && !wcsncmp_0(L"16BIT", v35, 5u) )
                                {
                                  *(_QWORD *)v35 = *(_QWORD *)L"BIT16";
                                  v35[4] = aBit16[4];
                                }
                                if ( (int)StringCchCatW(v35, v37 - (unsigned int)v39, L" ") < 0 )
                                {
                                  v13 = FirstFileW;
                                  goto LABEL_140;
                                }
                                v33 += v39 + 1;
                                v35 += (int)v39 + 1;
                              }
                              v34 = (unsigned int (__fastcall **)(const WCHAR *, __int64 *, char *))v59;
                            }
                            if ( (unsigned int)++v36 >= HIDWORD(v55) )
                            {
                              v27 = Extension;
                              v8 = v62;
                              break;
                            }
                          }
                        }
                        v13 = FirstFileW;
                      }
                      v10 = 0;
                      if ( v27 && (!wcsicmp(v27, L".exe") || !wcsicmp(v27, L".dll")) )
                      {
                        memset_0(v70, 0, 0x200u);
                        v68[1] = 528;
                        v68[0] = 1;
                        v69 = v8;
                        if ( (int)AeWERQueryFileInfo((__int64)v68) >= 0 )
                        {
                          v40 = -1;
                          do
                            ++v40;
                          while ( v15[v40] );
                          StringCchPrintfExW(
                            v35,
                            (unsigned int)(4096 - v40),
                            &Extension,
                            &v53,
                            0,
                            L"FILE_ID=\"%s\" PROGRAM_ID=\"%s\" ",
                            v71,
                            v70);
                        }
                      }
                      if ( (int)StringCchCatW(v15, 0x1000u, L"/>\r\n") >= 0 )
                      {
                        v20 = v15;
                        v61 = v15;
                        v41 = -1;
                        do
                          ++v41;
                        while ( v15[v41] );
                        v21 = hFile;
                        WriteFile(hFile, v15, 2 * v41, (LPDWORD)&NumberOfBytesWritten, 0);
                        v42 = v64;
                        v43 = v64[4];
                        if ( v43 )
                        {
                          ++v64[5];
                          if ( v42[5] >= v43 )
                            goto LABEL_126;
                        }
                        LODWORD(v12) = HIDWORD(v51);
                        goto LABEL_109;
                      }
                      v20 = v61;
                      LODWORD(v12) = HIDWORD(v51);
                      goto LABEL_108;
                    }
LABEL_65:
                    v31 = L"    <SYS NAME=\"";
                    goto LABEL_67;
                  case 5:
                    v28 = v60;
                    cFileName = FindFileData.cFileName;
                    break;
                  default:
                    goto LABEL_64;
                }
                v30 = wcsicmp(cFileName, v28);
                goto LABEL_54;
              }
            }
          }
LABEL_141:
          if ( v58 )
          {
            (*(void (**)(void))(v59 + 16))();
            v58 = 0;
          }
          if ( v13 != -1 )
            FindClose((HANDLE)v13);
          if ( v15 )
          {
            v49 = GetProcessHeap();
            HeapFree(v49, 0, v15);
          }
        }
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180033948  push    rbp
0x18003394a  push    rbx
0x18003394b  push    rsi
0x18003394c  push    rdi
0x18003394d  push    r12
0x18003394f  push    r13
0x180033951  push    r14
0x180033953  push    r15
0x180033955  lea     rbp, [rsp-448h]
0x18003395d  sub     rsp, 548h
0x180033964  mov     rax, cs:__security_cookie
0x18003396b  xor     rax, rsp
0x18003396e  mov     [rbp+480h+var_50], rax
0x180033975  mov     rax, [rbp+480h+arg_20]
0x18003397c  mov     r12, r9
0x18003397f  mov     rsi, [rbp+480h+arg_28]
0x180033986  mov     ebx, r8d
0x180033989  mov     r8d, 250h; Size
0x18003398f  mov     [rbp+480h+var_4F8], rax
0x180033993  mov     rax, [rbp+480h+arg_38]
0x18003399a  mov     [rbp+480h+var_4D8], rdx
0x18003399e  xor     edx, edx; Val
0x1800339a0  mov     [rsp+580h+hFile], rcx
0x1800339a5  lea     rcx, [rbp+480h+FindFileData]; void *
0x1800339ac  mov     [rbp+480h+var_500], rax
0x1800339b0  mov     [rbp+480h+var_4E8], r9
0x1800339b4  mov     dword ptr [rsp+580h+var_518], ebx
0x1800339b8  mov     [rbp+480h+var_4C8], rsi
0x1800339bc  call    memset_0
0x1800339c1  xor     ecx, ecx
0x1800339c3  mov     [rsp+580h+var_530], rcx
0x1800339c8  mov     edi, ecx
0x1800339ca  mov     [rsp+580h+var_508], rcx
0x1800339cf  mov     dword ptr [rsp+580h+NumberOfBytesWritten], ecx
0x1800339d3  mov     [rsp+580h+var_51C], ecx
0x1800339d7  mov     [rsp+580h+var_540], ecx
0x1800339db  test    rsi, rsi
0x1800339de  jz      loc_18003438C
0x1800339e4  cmp     rsi, r12
0x1800339e7  jb      loc_18003438C
0x1800339ed  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800339f1  mov     rax, rdx
0x1800339f4  inc     rax
0x1800339f7  cmp     [r12+rax*2], cx
0x1800339fc  jnz     short loc_1800339F4
0x1800339fe  lea     rax, [r12+rax*2]
0x180033a02  cmp     rax, rsi
0x180033a05  jb      loc_18003438C
0x180033a0b  mov     r15d, [rbp+480h+arg_30]
0x180033a12  movzx   r14d, bx
0x180033a16  mov     [rsp+580h+var_53C], r14d
0x180033a1b  test    r15d, r15d
0x180033a1e  jz      short loc_180033A2D
0x180033a20  lea     eax, [r14-4]
0x180033a24  cmp     eax, 1
0x180033a27  jbe     loc_18003438C
0x180033a2d  mov     r13, rdx
0x180033a30  call    cs:__imp_GetProcessHeap
0x180033a36  mov     edx, 8; dwFlags
0x180033a3b  mov     r8d, 2000h; dwBytes
0x180033a41  mov     rcx, rax; hHeap
0x180033a44  call    cs:__imp_HeapAlloc
0x180033a4a  xor     r10d, r10d
0x180033a4d  mov     rbx, rax
0x180033a50  test    rax, rax
0x180033a53  jz      loc_180034345
0x180033a59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033a5d  inc     rax
0x180033a60  cmp     [rsi+rax*2], r10w
0x180033a65  jnz     short loc_180033A5D
0x180033a67  mov     r8, [rbp+480h+var_4F8]
0x180033a6b  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x180033a6f  mov     rax, rcx
0x180033a72  mov     [rbp+480h+var_4E0], rcx
0x180033a76  sub     rax, r12
0x180033a79  mov     edx, 1000h
0x180033a7e  sar     rax, 1
0x180033a81  sub     rdx, rax; unsigned __int64
0x180033a84  lea     rax, asc_1800B2BE8; "*"
0x180033a8b  cmp     r14d, 5
0x180033a8f  mov     [rbp+480h+var_4D0], rdx
0x180033a93  cmovnz  r8, rax; unsigned __int16 *
0x180033a97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033a9c  test    eax, eax
0x180033a9e  js      loc_180034345
0x180033aa4  lea     rdx, [rbp+480h+FindFileData]; lpFindFileData
0x180033aab  mov     rcx, r12; lpFileName
0x180033aae  call    cs:__imp_FindFirstFileW
0x180033ab4  mov     [rsp+580h+var_510], rax
0x180033ab9  mov     r13, rax
0x180033abc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033ac0  jnz     short loc_180033ADE
0x180033ac2  call    cs:__imp_GetLastError
0x180033ac8  mov     r8, r12
0x180033acb  lea     rcx, aCmicollectmatc; "[_CmiCollectMatchingInfoDir] FindFirstF"...
0x180033ad2  mov     edx, eax
0x180033ad4  call    ?_CmiDebugPrintA@@YAXPEBDZZ; _CmiDebugPrintA(char const *,...)
0x180033ad9  jmp     loc_180034345
0x180033ade  xor     ecx, ecx
0x180033ae0  mov     [rbp+480h+var_4F0], rcx
0x180033ae4  mov     esi, ecx
0x180033ae6  test    r15d, r15d
0x180033ae9  jnz     loc_180033C7E
0x180033aef  mov     rax, [rbp+480h+var_4D8]
0x180033af3  cmp     [rax+18h], ecx
0x180033af6  jz      short loc_180033B6B
0x180033af8  mov     eax, ecx
0x180033afa  lea     r8, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x180033b01  mov     rcx, [rbp+480h+var_4E0]
0x180033b05  mov     edx, 1000h; unsigned __int64
0x180033b0a  mov     [rcx], ax
0x180033b0d  mov     rcx, rbx; unsigned __int16 *
0x180033b10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033b15  test    eax, eax
0x180033b17  js      loc_180034345
0x180033b1d  mov     r15, [rsp+580h+hFile]
0x180033b22  lea     r9, [rsp+580h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180033b27  mov     rcx, r15; hFile
0x180033b2a  mov     [rsp+580h+lpOverlapped], rsi; lpOverlapped
0x180033b2f  lea     r8d, [rsi+2]; nNumberOfBytesToWrite
0x180033b33  lea     rdx, byte_1800D9370; lpBuffer
0x180033b3a  call    cs:__imp_WriteFile
0x180033b40  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033b44  inc     r8
0x180033b47  cmp     [rbx+r8*2], si
0x180033b4c  jnz     short loc_180033B44
0x180033b4e  add     r8d, r8d; nNumberOfBytesToWrite
0x180033b51  mov     [rsp+580h+lpOverlapped], rsi; lpOverlapped
0x180033b56  lea     r9, [rsp+580h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180033b5b  mov     rdx, rbx; lpBuffer
0x180033b5e  mov     rcx, r15; hFile
0x180033b61  call    cs:__imp_WriteFile
0x180033b67  xor     ecx, ecx
0x180033b69  jmp     short loc_180033B70
0x180033b6b  mov     r15, [rsp+580h+hFile]
0x180033b70  mov     rsi, [rbp+480h+var_4F8]
0x180033b74  cmp     r14d, 4
0x180033b78  jnz     short loc_180033BA3
0x180033b7a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180033b7e  inc     rdx
0x180033b81  cmp     [rsi+rdx*2], cx
0x180033b85  jnz     short loc_180033B7E
0x180033b87  inc     rdx; unsigned __int64
0x180033b8a  lea     r8, aSystemInfo; "SYSTEM INFO"
0x180033b91  mov     rcx, rsi; unsigned __int16 *
0x180033b94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033b99  xor     ecx, ecx
0x180033b9b  test    eax, eax
0x180033b9d  js      loc_180034345
0x180033ba3  lea     rax, aExeName; "<EXE NAME=\""
0x180033baa  xor     r8d, r8d; unsigned __int16 **
0x180033bad  mov     [rsp+580h+var_558], rax; unsigned __int16 *
0x180033bb2  lea     r9, [rsp+580h+var_530]; unsigned __int64 *
0x180033bb7  mov     [rsp+580h+lpOverlapped], rcx; unsigned int
0x180033bbc  mov     edx, 1000h; unsigned __int64
0x180033bc1  mov     rcx, rbx; Buffer
0x180033bc4  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180033bc9  test    eax, eax
0x180033bcb  js      loc_180034345
0x180033bd1  mov     eax, 1000h
0x180033bd6  mov     edx, 1000h
0x180033bdb  sub     eax, dword ptr [rsp+580h+var_530]
0x180033bdf  mov     r8, rsi; unsigned __int16 *
0x180033be2  sub     edx, eax; int
0x180033be4  cdqe
0x180033be6  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x180033bea  call    ?_CmiSanitizeXML@@YAHPEAGHPEBG@Z; _CmiSanitizeXML(ushort *,int,ushort const *)
0x180033bef  xor     esi, esi
0x180033bf1  test    eax, eax
0x180033bf3  jz      loc_180034345
0x180033bf9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180033bfd  inc     rcx
0x180033c00  cmp     [rbx+rcx*2], si
0x180033c04  jnz     short loc_180033BFD
0x180033c06  movsxd  rax, ecx
0x180033c09  lea     r9, [rsp+580h+var_530]; unsigned __int64 *
0x180033c0e  mov     edx, 1000h
0x180033c13  xor     r8d, r8d; unsigned __int16 **
0x180033c16  sub     edx, ecx; unsigned __int64
0x180033c18  lea     rcx, [rbx+rax*2]; Buffer
0x180033c1c  lea     rax, __ImageBase
0x180033c23  mov     rax, ds:rva ?g_szFilterDesc@@3PAPEAGA[rax+r14*8]; ushort * near * g_szFilterDesc ...
0x180033c2b  mov     [rsp+580h+var_550], rax
0x180033c30  lea     rax, aFilterS; "\" FILTER=\"%s\">\r\n"
0x180033c37  mov     [rsp+580h+var_558], rax; unsigned __int16 *
0x180033c3c  mov     [rsp+580h+lpOverlapped], rsi; unsigned int
0x180033c41  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180033c46  test    eax, eax
0x180033c48  js      loc_180034345
0x180033c4e  mov     rsi, rbx
0x180033c51  mov     [rbp+480h+var_4F0], rbx
0x180033c55  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033c59  inc     r8
0x180033c5c  cmp     [rbx+r8*2], di
0x180033c61  jnz     short loc_180033C59
0x180033c63  add     r8d, r8d; nNumberOfBytesToWrite
0x180033c66  mov     [rsp+580h+lpOverlapped], rdi; lpOverlapped
0x180033c6b  lea     r9, [rsp+580h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180033c70  mov     rdx, rbx; lpBuffer
0x180033c73  mov     rcx, r15; hFile
0x180033c76  call    cs:__imp_WriteFile
0x180033c7c  jmp     short loc_180033C83
0x180033c7e  mov     r15, [rsp+580h+hFile]
0x180033c83  mov     eax, r14d
0x180033c86  mov     [rsp+580h+var_520], edi
0x180033c8a  sub     eax, 1
0x180033c8d  jz      short loc_180033C99
0x180033c8f  sub     eax, 3
0x180033c92  jz      short loc_180033C99
0x180033c94  cmp     eax, 1
0x180033c97  jnz     short loc_180033CA1
0x180033c99  mov     [rsp+580h+var_520], 0Ah
0x180033ca1  test    byte ptr [rbp+480h+FindFileData.dwFileAttributes], 10h
0x180033ca8  jnz     loc_18003411F
0x180033cae  mov     rdx, [rbp+480h+var_4D0]; unsigned __int64
0x180033cb2  lea     r8, [rbp+480h+FindFileData.cFileName]; unsigned __int16 *
0x180033cb9  mov     rcx, [rbp+480h+var_4E0]; unsigned __int16 *
0x180033cbd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033cc2  test    eax, eax
0x180033cc4  js      loc_180034341
0x180033cca  mov     rcx, r12; unsigned __int16 *
0x180033ccd  call    ?PathFindExtension@@YAPEAGPEBG@Z; PathFindExtension(ushort const *)
0x180033cd2  mov     [rbp+480h+var_4C0], rax
0x180033cd6  mov     r15, rax
0x180033cd9  mov     eax, r14d
0x180033cdc  test    r14d, r14d
0x180033cdf  jz      loc_180033D9C
0x180033ce5  sub     eax, 1
0x180033ce8  jz      loc_180033D9C
0x180033cee  sub     eax, 1
0x180033cf1  jz      loc_180033D7C
0x180033cf7  sub     eax, 2
0x180033cfa  jz      short loc_180033D12
0x180033cfc  cmp     eax, 1
0x180033cff  jnz     loc_180033E17
0x180033d05  mov     rdx, [rbp+480h+var_4F8]
0x180033d09  lea     rcx, [rbp+480h+FindFileData.cFileName]
0x180033d10  jmp     short loc_180033D8F
0x180033d12  mov     rax, cs:?g_szGrabmiFilterSystem@@3PAPEAGA; ushort * near * g_szGrabmiFilterSystem
0x180033d19  xor     ecx, ecx
0x180033d1b  cmp     [rax], cx
0x180033d1e  jz      short loc_180033D5E
0x180033d20  xor     esi, esi
0x180033d22  lea     r12, __ImageBase
0x180033d29  movsxd  rdx, edi
0x180033d2c  lea     rcx, [rbp+480h+FindFileData.cFileName]; String1
0x180033d33  mov     rdx, ds:rva ?g_szGrabmiFilterSystem@@3PAPEAGA[r12+rdx*8]; String2
0x180033d3b  call    _wcsicmp
0x180033d40  test    eax, eax
0x180033d42  jz      short loc_180033D56
0x180033d44  inc     edi
0x180033d46  movsxd  rax, edi
0x180033d49  mov     rax, ds:rva ?g_szGrabmiFilterSystem@@3PAPEAGA[r12+rax*8]; ushort * near * g_szGrabmiFilterSystem ...
0x180033d51  cmp     [rax], si
0x180033d54  jnz     short loc_180033D29
0x180033d56  mov     r12, [rbp+480h+var_4E8]
0x180033d5a  mov     rsi, [rbp+480h+var_4F0]
0x180033d5e  movsxd  rax, edi
0x180033d61  lea     rcx, __ImageBase
0x180033d68  xor     edi, edi
0x180033d6a  mov     rax, ds:rva ?g_szGrabmiFilterSystem@@3PAPEAGA[rcx+rax*8]; ushort * near * g_szGrabmiFilterSystem ...
0x180033d72  mov     ecx, edi
0x180033d74  cmp     [rax], di
0x180033d77  setz    cl
0x180033d7a  jmp     short loc_180033D96
0x180033d7c  test    r15, r15
0x180033d7f  jz      loc_180033E1D
0x180033d85  lea     rdx, String2; ".sys"
0x180033d8c  mov     rcx, r15; String1
0x180033d8f  call    _wcsicmp
0x180033d94  mov     ecx, eax
0x180033d96  test    ecx, ecx
0x180033d98  jz      short loc_180033E17
0x180033d9a  jmp     short loc_180033E02
0x180033d9c  xor     eax, eax
0x180033d9e  cmp     word ptr cs:aExe, ax; ".exe"
0x180033da5  jz      short loc_180033DE9
0x180033da7  xor     r12d, r12d
0x180033daa  lea     r14, __ImageBase
0x180033db1  test    r15, r15
0x180033db4  jz      short loc_180033DCD
0x180033db6  movsxd  rdx, edi
0x180033db9  mov     rcx, r15; String1
0x180033dbc  mov     rdx, ds:rva ?g_szGrabmiFilterNormal@@3PAPEAGA[r14+rdx*8]; String2
0x180033dc4  call    _wcsicmp
0x180033dc9  test    eax, eax
0x180033dcb  jz      short loc_180033DE0
0x180033dcd  inc     edi
0x180033dcf  movsxd  rax, edi
0x180033dd2  mov     rax, ds:rva ?g_szGrabmiFilterNormal@@3PAPEAGA[r14+rax*8]; ushort * near * g_szGrabmiFilterNormal ...
0x180033dda  cmp     [rax], r12w
0x180033dde  jnz     short loc_180033DB1
0x180033de0  mov     r12, [rbp+480h+var_4E8]
0x180033de4  mov     r14d, [rsp+580h+var_53C]
0x180033de9  movsxd  rax, edi
0x180033dec  lea     rcx, __ImageBase
0x180033df3  xor     edi, edi
0x180033df5  mov     rax, ds:rva ?g_szGrabmiFilterNormal@@3PAPEAGA[rcx+rax*8]; ushort * near * g_szGrabmiFilterNormal ...
0x180033dfd  cmp     [rax], di
0x180033e00  jnz     short loc_180033E17
  ... truncated ...
```
