# _CmiCollectMatchingInfoDir(void *,tagRECINFO *,ulong,ushort const *,ushort *,ushort *,int,tagCMIPFN *)

- ea: `0x1800353c0`
- end: `0x180035e94`
- name: `?_CmiCollectMatchingInfoDir@@YA?AW4CMI_RESULT@@PEAXPEAUtagRECINFO@@KPEBGPEAG3HPEAUtagCMIPFN@@@Z`
- size: `2772`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004fec`
- `0x1800353c0`

## callees

- `0x180004790`
- `0x180005330`
- `0x180016f0c`
- `0x18001ad94`
- `0x18002a368`
- `0x18002c6ac`
- `0x180034fe0`
- `0x1800353c0`
- `0x18004ed08`
- `0x180053300`
- `0x180053cc4`
- `0x180053d3c`
- `0x1800af07c`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035e4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800354a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035e4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035e62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035e62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800354c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800354c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003554c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003554c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c6e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035be8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035e3d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035be8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035e3d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180035bd1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180035d52`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180035bd1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180035d52`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800355ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800355f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035712`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035b8b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035de1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800355ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800355f7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035712`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035b8b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180035de1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035532`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035c54`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035532`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180035c54`

## string_xrefs

- `0x18003555b`: `[_CmiCollectMatchingInfoDir] FindFirstFile failed (error code=%d) (path=%S).\n`
- `0x180035c7d`: `[_CmiCollectMatchingInfoDir] FindFirstFile failed (error code=%d) (path=%S).\n`
- `0x18003558a`: `<?xml version="1.0" encoding="UTF-16"?>\n<DATABASE>\n`

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
  unsigned int (__fastcall **v34)(const WCHAR *, __int64 *, unsigned int *); // rdi
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
  unsigned int v51; // [rsp+40h] [rbp-C0h]
  int v52; // [rsp+44h] [rbp-BCh]
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v54; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-A8h]
  int v56; // [rsp+60h] [rbp-A0h]
  unsigned int v57; // [rsp+64h] [rbp-9Ch] BYREF
  int v58; // [rsp+68h] [rbp-98h]
  __int64 FirstFileW; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h] BYREF
  __int64 v61; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v62; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  const WCHAR *v64; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v65; // [rsp+A0h] [rbp-60h]
  _DWORD *v66; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v67; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v68; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *Extension; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v70[2]; // [rsp+D0h] [rbp-30h] BYREF
  const WCHAR *v71; // [rsp+D8h] [rbp-28h]
  _BYTE v72[256]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v73[256]; // [rsp+1E0h] [rbp+E0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+2E0h] [rbp+1E0h] BYREF

  v8 = a4;
  v9 = a3;
  v62 = a5;
  v66 = a2;
  hFile = a1;
  v61 = a8;
  v64 = a4;
  v58 = a3;
  v68 = a6;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v54 = 0;
  v10 = 0;
  v60 = 0;
  NumberOfBytesWritten = 0;
  v57 = 0;
  v51 = 0;
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
        v52 = v9;
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
          v17 = v62;
          v18 = &a6[v16];
          v65 = v18;
          v67 = 4096 - (v18 - v8);
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
          v63 = 0;
          v20 = 0;
          if ( a7 )
          {
            v21 = hFile;
            goto LABEL_36;
          }
          if ( v66[6] )
          {
            *v65 = 0;
            if ( (int)StringCchPrintfW(v15, 0x1000u, L"<?xml version=\"1.0\" encoding=\"UTF-16\"?>\r\n<DATABASE>\r\n") < 0 )
              goto LABEL_141;
            v21 = hFile;
            WriteFile(hFile, byte_1800DE370, 2u, &NumberOfBytesWritten, 0);
            v22 = -1;
            do
              ++v22;
            while ( v15[v22] );
            WriteFile(v21, v15, 2 * v22, &NumberOfBytesWritten, 0);
          }
          else
          {
            v21 = hFile;
          }
          v23 = v62;
          if ( (_DWORD)v12 != 4 )
            goto LABEL_31;
          v24 = -1;
          do
            ++v24;
          while ( v62[v24] );
          if ( (int)StringCchCopyW(v62, v24 + 1, L"SYSTEM INFO") >= 0 )
          {
LABEL_31:
            if ( (int)StringCchPrintfExW(v15, 0x1000u, 0, &v54, 0, L"<EXE NAME=\"") >= 0 )
            {
              if ( (unsigned int)_CmiSanitizeXML(&v15[4096 - (int)v54], v54, v23) )
              {
                v25 = -1;
                do
                  ++v25;
                while ( v15[v25] );
                if ( (int)StringCchPrintfExW(
                            &v15[(int)v25],
                            (unsigned int)(4096 - v25),
                            0,
                            &v54,
                            0,
                            L"\" FILTER=\"%s\">\r\n",
                            (&g_szFilterDesc)[v12]) >= 0 )
                {
                  v20 = v15;
                  v63 = v15;
                  v26 = -1;
                  do
                    ++v26;
                  while ( v15[v26] );
                  WriteFile(v21, v15, 2 * v26, &NumberOfBytesWritten, 0);
LABEL_36:
                  v56 = 0;
                  if ( (_DWORD)v12 == 1 || (unsigned int)(v12 - 4) <= 1 )
                    v56 = 10;
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
                        if ( a7 < 3 && v58 >= 0 )
                        {
                          v44 = v67;
                          v45 = v65;
                          if ( (int)StringCchCopyW(v65, v67, L"*") >= 0 )
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
                                  v51 = _CmiCollectMatchingInfoDir(
                                          hFile,
                                          v66,
                                          (unsigned int)v58,
                                          v8,
                                          0,
                                          v68,
                                          a7 + 1,
                                          v61);
                                  if ( v51 == -1 )
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
                          && ((v58 & 0x10000000) != 0 || (int)StringCchCatW(v20, v47, L"</DATABASE>\r\n") >= 0) )
                        {
                          v48 = -1;
                          do
                            ++v48;
                          while ( v20[v48] );
                          WriteFile(v21, v20, 2 * v48, &NumberOfBytesWritten, 0);
                          goto LABEL_134;
                        }
                      }
                      goto LABEL_141;
                    }
                  }
                  if ( (int)StringCchCopyW(v65, v67, FindFileData.cFileName) < 0 )
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
                      v8 = v64;
                      LODWORD(v12) = v52;
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
                        v8 = v64;
                        v20 = v63;
                      }
                      v30 = *(_WORD *)(&g_szGrabmiFilterSystem)[v10] == 0;
LABEL_54:
                      if ( !v30 )
                        goto LABEL_64;
LABEL_62:
                      if ( v56 >= 10 )
                      {
                        v10 = 0;
LABEL_108:
                        v21 = hFile;
                        goto LABEL_109;
                      }
                      ++v56;
LABEL_64:
                      if ( (_DWORD)v12 != 2 )
                      {
                        v31 = L"    <MATCHING_FILE NAME=\"";
LABEL_67:
                        if ( (int)StringCchPrintfExW(v15, 0x1000u, 0, &v54, 0, v31) < 0 )
                          goto LABEL_140;
                        if ( !(unsigned int)_CmiSanitizeXML(&v15[4096 - (int)v54], v54, v68) )
                          goto LABEL_140;
                        v32 = -1;
                        do
                          ++v32;
                        while ( v15[v32] );
                        if ( (int)StringCchPrintfExW(&v15[(int)v32], (unsigned int)(4096 - v32), 0, &v54, 0, L"\" ") < 0 )
                          goto LABEL_140;
                        v33 = 4096 - v54;
                        v34 = (unsigned int (__fastcall **)(const WCHAR *, __int64 *, unsigned int *))v61;
                        v35 = &v15[4096 - (int)v54];
                        if ( v60 )
                        {
                          (*(void (**)(void))(v61 + 16))();
                          v60 = 0;
                        }
                        if ( (*v34)(v8, &v60, &v57) )
                        {
                          v36 = 0;
                          if ( v57 )
                          {
                            while ( 1 )
                            {
                              v37 = 4096 - v33;
                              v38 = 16LL * v36;
                              if ( v34[1](
                                     (const WCHAR *)(v38 + v60),
                                     (__int64 *)v35,
                                     (unsigned int *)(unsigned int)(4096 - v33)) )
                              {
                                v39 = -1;
                                do
                                  ++v39;
                                while ( v35[v39] );
                                if ( v52 != 2
                                  || *(_WORD *)(v38 + v60) == 16413
                                  || *(_WORD *)(v38 + v60) == 16414
                                  || *(_WORD *)(v38 + v60) == 20483
                                  || *(_WORD *)(v38 + v60) == 20486 )
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
                                v34 = (unsigned int (__fastcall **)(const WCHAR *, __int64 *, unsigned int *))v61;
                              }
                              if ( ++v36 >= v57 )
                              {
                                v27 = Extension;
                                v8 = v64;
                                break;
                              }
                            }
                          }
                          v13 = FirstFileW;
                        }
                        v10 = 0;
                        if ( v27 && (!wcsicmp(v27, L".exe") || !wcsicmp(v27, L".dll")) )
                        {
                          memset_0(v72, 0, 0x200u);
                          v70[1] = 528;
                          v70[0] = 1;
                          v71 = v8;
                          if ( (int)AeWERQueryFileInfo(v70) >= 0 )
                          {
                            v40 = -1;
                            do
                              ++v40;
                            while ( v15[v40] );
                            StringCchPrintfExW(
                              v35,
                              (unsigned int)(4096 - v40),
                              &Extension,
                              &v54,
                              0,
                              L"FILE_ID=\"%s\" PROGRAM_ID=\"%s\" ",
                              v73,
                              v72);
                          }
                        }
                        if ( (int)StringCchCatW(v15, 0x1000u, L"/>\r\n") >= 0 )
                        {
                          v20 = v15;
                          v63 = v15;
                          v41 = -1;
                          do
                            ++v41;
                          while ( v15[v41] );
                          v21 = hFile;
                          WriteFile(hFile, v15, 2 * v41, &NumberOfBytesWritten, 0);
                          v42 = v66;
                          v43 = v66[4];
                          if ( v43 )
                          {
                            ++v66[5];
                            if ( v42[5] >= v43 )
                              goto LABEL_126;
                          }
                          LODWORD(v12) = v52;
                          goto LABEL_109;
                        }
                        v20 = v63;
                        LODWORD(v12) = v52;
                        goto LABEL_108;
                      }
LABEL_65:
                      v31 = L"    <SYS NAME=\"";
                      goto LABEL_67;
                    case 5:
                      v28 = v62;
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
          }
LABEL_141:
          if ( v60 )
          {
            (*(void (**)(void))(v61 + 16))();
            v60 = 0;
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
0x1800353c0  push    rbp
0x1800353c2  push    rbx
0x1800353c3  push    rsi
0x1800353c4  push    rdi
0x1800353c5  push    r12
0x1800353c7  push    r13
0x1800353c9  push    r14
0x1800353cb  push    r15
0x1800353cd  lea     rbp, [rsp-448h]
0x1800353d5  sub     rsp, 548h
0x1800353dc  mov     rax, cs:__security_cookie
0x1800353e3  xor     rax, rsp
0x1800353e6  mov     [rbp+480h+var_50], rax
0x1800353ed  mov     rax, [rbp+480h+arg_20]
0x1800353f4  mov     r12, r9
0x1800353f7  mov     rsi, [rbp+480h+arg_28]
0x1800353fe  mov     ebx, r8d
0x180035401  mov     r8d, 250h; Size
0x180035407  mov     [rbp+480h+var_4F8], rax
0x18003540b  mov     rax, [rbp+480h+arg_38]
0x180035412  mov     [rbp+480h+var_4D8], rdx
0x180035416  xor     edx, edx; Val
0x180035418  mov     [rsp+580h+hFile], rcx
0x18003541d  lea     rcx, [rbp+480h+FindFileData]; void *
0x180035424  mov     [rbp+480h+var_500], rax
0x180035428  mov     [rbp+480h+var_4E8], r9
0x18003542c  mov     [rsp+580h+var_518], ebx
0x180035430  mov     [rbp+480h+var_4C8], rsi
0x180035434  call    memset_0
0x180035439  xor     ecx, ecx
0x18003543b  mov     [rsp+580h+var_530], rcx
0x180035440  mov     edi, ecx
0x180035442  mov     [rsp+580h+var_508], rcx
0x180035447  mov     [rsp+580h+NumberOfBytesWritten], ecx
0x18003544b  mov     [rsp+580h+var_51C], ecx
0x18003544f  mov     [rsp+580h+var_540], ecx
0x180035453  test    rsi, rsi
0x180035456  jz      loc_180035E6E
0x18003545c  cmp     rsi, r12
0x18003545f  jb      loc_180035E6E
0x180035465  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180035469  mov     rax, rdx
0x18003546c  inc     rax
0x18003546f  cmp     [r12+rax*2], cx
0x180035474  jnz     short loc_18003546C
0x180035476  lea     rax, [r12+rax*2]
0x18003547a  cmp     rax, rsi
0x18003547d  jb      loc_180035E6E
0x180035483  mov     r15d, [rbp+480h+arg_30]
0x18003548a  movzx   r14d, bx
0x18003548e  mov     [rsp+580h+var_53C], r14d
0x180035493  test    r15d, r15d
0x180035496  jz      short loc_1800354A5
0x180035498  lea     eax, [r14-4]
0x18003549c  cmp     eax, 1
0x18003549f  jbe     loc_180035E6E
0x1800354a5  mov     r13, rdx
0x1800354a8  call    cs:__imp_GetProcessHeap
0x1800354af  nop     dword ptr [rax+rax+00h]
0x1800354b4  mov     edx, 8; dwFlags
0x1800354b9  mov     r8d, 2000h; dwBytes
0x1800354bf  mov     rcx, rax; hHeap
0x1800354c2  call    cs:__imp_HeapAlloc
0x1800354c9  nop     dword ptr [rax+rax+00h]
0x1800354ce  xor     r10d, r10d
0x1800354d1  mov     rbx, rax
0x1800354d4  test    rax, rax
0x1800354d7  jz      loc_180035E15
0x1800354dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800354e1  inc     rax
0x1800354e4  cmp     [rsi+rax*2], r10w
0x1800354e9  jnz     short loc_1800354E1
0x1800354eb  mov     r8, [rbp+480h+var_4F8]
0x1800354ef  lea     rcx, [rsi+rax*2]; unsigned __int16 *
0x1800354f3  mov     rax, rcx
0x1800354f6  mov     [rbp+480h+var_4E0], rcx
0x1800354fa  sub     rax, r12
0x1800354fd  mov     edx, 1000h
0x180035502  sar     rax, 1
0x180035505  sub     rdx, rax; unsigned __int64
0x180035508  lea     rax, asc_1800B7AF8; "*"
0x18003550f  cmp     r14d, 5
0x180035513  mov     [rbp+480h+var_4D0], rdx
0x180035517  cmovnz  r8, rax; unsigned __int16 *
0x18003551b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035520  test    eax, eax
0x180035522  js      loc_180035E15
0x180035528  lea     rdx, [rbp+480h+FindFileData]; lpFindFileData
0x18003552f  mov     rcx, r12; lpFileName
0x180035532  call    cs:__imp_FindFirstFileW
0x180035539  nop     dword ptr [rax+rax+00h]
0x18003553e  mov     [rsp+580h+var_510], rax
0x180035543  mov     r13, rax
0x180035546  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003554a  jnz     short loc_18003556E
0x18003554c  call    cs:__imp_GetLastError
0x180035553  nop     dword ptr [rax+rax+00h]
0x180035558  mov     r8, r12
0x18003555b  lea     rcx, aCmicollectmatc; "[_CmiCollectMatchingInfoDir] FindFirstF"...
0x180035562  mov     edx, eax
0x180035564  call    ?_CmiDebugPrintA@@YAXPEBDZZ; _CmiDebugPrintA(char const *,...)
0x180035569  jmp     loc_180035E15
0x18003556e  xor     ecx, ecx
0x180035570  mov     [rbp+480h+var_4F0], rcx
0x180035574  mov     esi, ecx
0x180035576  test    r15d, r15d
0x180035579  jnz     loc_180035720
0x18003557f  mov     rax, [rbp+480h+var_4D8]
0x180035583  cmp     [rax+18h], ecx
0x180035586  jz      short loc_180035607
0x180035588  mov     eax, ecx
0x18003558a  lea     r8, aXmlVersion10En_0; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x180035591  mov     rcx, [rbp+480h+var_4E0]
0x180035595  mov     edx, 1000h; unsigned __int64
0x18003559a  mov     [rcx], ax
0x18003559d  mov     rcx, rbx; unsigned __int16 *
0x1800355a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800355a5  test    eax, eax
0x1800355a7  js      loc_180035E15
0x1800355ad  mov     r15, [rsp+580h+hFile]
0x1800355b2  lea     r9, [rsp+580h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800355b7  mov     rcx, r15; hFile
0x1800355ba  mov     [rsp+580h+lpOverlapped], rsi; lpOverlapped
0x1800355bf  lea     r8d, [rsi+2]; nNumberOfBytesToWrite
0x1800355c3  lea     rdx, byte_1800DE370; lpBuffer
0x1800355ca  call    cs:__imp_WriteFile
0x1800355d1  nop     dword ptr [rax+rax+00h]
0x1800355d6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800355da  inc     r8
0x1800355dd  cmp     [rbx+r8*2], si
0x1800355e2  jnz     short loc_1800355DA
0x1800355e4  add     r8d, r8d; nNumberOfBytesToWrite
0x1800355e7  mov     [rsp+580h+lpOverlapped], rsi; lpOverlapped
0x1800355ec  lea     r9, [rsp+580h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800355f1  mov     rdx, rbx; lpBuffer
0x1800355f4  mov     rcx, r15; hFile
0x1800355f7  call    cs:__imp_WriteFile
0x1800355fe  nop     dword ptr [rax+rax+00h]
0x180035603  xor     ecx, ecx
0x180035605  jmp     short loc_18003560C
0x180035607  mov     r15, [rsp+580h+hFile]
0x18003560c  mov     rsi, [rbp+480h+var_4F8]
0x180035610  cmp     r14d, 4
0x180035614  jnz     short loc_18003563F
0x180035616  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003561a  inc     rdx
0x18003561d  cmp     [rsi+rdx*2], cx
0x180035621  jnz     short loc_18003561A
0x180035623  inc     rdx; unsigned __int64
0x180035626  lea     r8, aSystemInfo; "SYSTEM INFO"
0x18003562d  mov     rcx, rsi; unsigned __int16 *
0x180035630  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035635  xor     ecx, ecx
0x180035637  test    eax, eax
0x180035639  js      loc_180035E15
0x18003563f  lea     rax, aExeName; "<EXE NAME=\""
0x180035646  xor     r8d, r8d; unsigned __int16 **
0x180035649  mov     [rsp+580h+var_558], rax; unsigned __int16 *
0x18003564e  lea     r9, [rsp+580h+var_530]; unsigned __int64 *
0x180035653  mov     [rsp+580h+lpOverlapped], rcx; unsigned int
0x180035658  mov     edx, 1000h; unsigned __int64
0x18003565d  mov     rcx, rbx; Buffer
0x180035660  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180035665  test    eax, eax
0x180035667  js      loc_180035E15
0x18003566d  mov     eax, 1000h
0x180035672  mov     edx, 1000h
0x180035677  sub     eax, dword ptr [rsp+580h+var_530]
0x18003567b  mov     r8, rsi; unsigned __int16 *
0x18003567e  sub     edx, eax; int
0x180035680  cdqe
0x180035682  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x180035686  call    ?_CmiSanitizeXML@@YAHPEAGHPEBG@Z; _CmiSanitizeXML(ushort *,int,ushort const *)
0x18003568b  xor     esi, esi
0x18003568d  test    eax, eax
0x18003568f  jz      loc_180035E15
0x180035695  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180035699  inc     rcx
0x18003569c  cmp     [rbx+rcx*2], si
0x1800356a0  jnz     short loc_180035699
0x1800356a2  movsxd  rax, ecx
0x1800356a5  lea     r9, [rsp+580h+var_530]; unsigned __int64 *
0x1800356aa  mov     edx, 1000h
0x1800356af  xor     r8d, r8d; unsigned __int16 **
0x1800356b2  sub     edx, ecx; unsigned __int64
0x1800356b4  lea     rcx, [rbx+rax*2]; Buffer
0x1800356b8  lea     rax, __ImageBase
0x1800356bf  mov     rax, ds:rva ?g_szFilterDesc@@3PAPEAGA[rax+r14*8]; ushort * near * g_szFilterDesc ...
0x1800356c7  mov     [rsp+580h+var_550], rax
0x1800356cc  lea     rax, aFilterS; "\" FILTER=\"%s\">\r\n"
0x1800356d3  mov     [rsp+580h+var_558], rax; unsigned __int16 *
0x1800356d8  mov     [rsp+580h+lpOverlapped], rsi; unsigned int
0x1800356dd  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800356e2  test    eax, eax
0x1800356e4  js      loc_180035E15
0x1800356ea  mov     rsi, rbx
0x1800356ed  mov     [rbp+480h+var_4F0], rbx
0x1800356f1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800356f5  inc     r8
0x1800356f8  cmp     [rbx+r8*2], di
0x1800356fd  jnz     short loc_1800356F5
0x1800356ff  add     r8d, r8d; nNumberOfBytesToWrite
0x180035702  mov     [rsp+580h+lpOverlapped], rdi; lpOverlapped
0x180035707  lea     r9, [rsp+580h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003570c  mov     rdx, rbx; lpBuffer
0x18003570f  mov     rcx, r15; hFile
0x180035712  call    cs:__imp_WriteFile
0x180035719  nop     dword ptr [rax+rax+00h]
0x18003571e  jmp     short loc_180035725
0x180035720  mov     r15, [rsp+580h+hFile]
0x180035725  mov     eax, r14d
0x180035728  mov     [rsp+580h+var_520], edi
0x18003572c  sub     eax, 1
0x18003572f  jz      short loc_18003573B
0x180035731  sub     eax, 3
0x180035734  jz      short loc_18003573B
0x180035736  cmp     eax, 1
0x180035739  jnz     short loc_180035743
0x18003573b  mov     [rsp+580h+var_520], 0Ah
0x180035743  test    byte ptr [rbp+480h+FindFileData.dwFileAttributes], 10h
0x18003574a  jnz     loc_180035BC7
0x180035750  mov     rdx, [rbp+480h+var_4D0]; unsigned __int64
0x180035754  lea     r8, [rbp+480h+FindFileData.cFileName]; unsigned __int16 *
0x18003575b  mov     rcx, [rbp+480h+var_4E0]; unsigned __int16 *
0x18003575f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035764  test    eax, eax
0x180035766  js      loc_180035E11
0x18003576c  mov     rcx, r12; unsigned __int16 *
0x18003576f  call    ?PathFindExtension@@YAPEAGPEBG@Z; PathFindExtension(ushort const *)
0x180035774  mov     [rbp+480h+var_4C0], rax
0x180035778  mov     r15, rax
0x18003577b  mov     eax, r14d
0x18003577e  test    r14d, r14d
0x180035781  jz      loc_18003583E
0x180035787  sub     eax, 1
0x18003578a  jz      loc_18003583E
0x180035790  sub     eax, 1
0x180035793  jz      loc_18003581E
0x180035799  sub     eax, 2
0x18003579c  jz      short loc_1800357B4
0x18003579e  cmp     eax, 1
0x1800357a1  jnz     loc_1800358B9
0x1800357a7  mov     rdx, [rbp+480h+var_4F8]
0x1800357ab  lea     rcx, [rbp+480h+FindFileData.cFileName]
0x1800357b2  jmp     short loc_180035831
0x1800357b4  mov     rax, cs:?g_szGrabmiFilterSystem@@3PAPEAGA; ushort * near * g_szGrabmiFilterSystem
0x1800357bb  xor     ecx, ecx
0x1800357bd  cmp     [rax], cx
0x1800357c0  jz      short loc_180035800
0x1800357c2  xor     esi, esi
0x1800357c4  lea     r12, __ImageBase
0x1800357cb  movsxd  rdx, edi
0x1800357ce  lea     rcx, [rbp+480h+FindFileData.cFileName]; String1
0x1800357d5  mov     rdx, ds:rva ?g_szGrabmiFilterSystem@@3PAPEAGA[r12+rdx*8]; String2
0x1800357dd  call    _wcsicmp
0x1800357e2  test    eax, eax
0x1800357e4  jz      short loc_1800357F8
0x1800357e6  inc     edi
0x1800357e8  movsxd  rax, edi
0x1800357eb  mov     rax, ds:rva ?g_szGrabmiFilterSystem@@3PAPEAGA[r12+rax*8]; ushort * near * g_szGrabmiFilterSystem ...
0x1800357f3  cmp     [rax], si
0x1800357f6  jnz     short loc_1800357CB
0x1800357f8  mov     r12, [rbp+480h+var_4E8]
0x1800357fc  mov     rsi, [rbp+480h+var_4F0]
0x180035800  movsxd  rax, edi
0x180035803  lea     rcx, __ImageBase
0x18003580a  xor     edi, edi
0x18003580c  mov     rax, ds:rva ?g_szGrabmiFilterSystem@@3PAPEAGA[rcx+rax*8]; ushort * near * g_szGrabmiFilterSystem ...
0x180035814  mov     ecx, edi
0x180035816  cmp     [rax], di
0x180035819  setz    cl
0x18003581c  jmp     short loc_180035838
0x18003581e  test    r15, r15
0x180035821  jz      loc_1800358BF
0x180035827  lea     rdx, String2; ".sys"
0x18003582e  mov     rcx, r15; String1
0x180035831  call    _wcsicmp
0x180035836  mov     ecx, eax
0x180035838  test    ecx, ecx
0x18003583a  jz      short loc_1800358B9
0x18003583c  jmp     short loc_1800358A4
0x18003583e  xor     eax, eax
0x180035840  cmp     word ptr cs:aExe, ax; ".exe"
0x180035847  jz      short loc_18003588B
0x180035849  xor     r12d, r12d
0x18003584c  lea     r14, __ImageBase
0x180035853  test    r15, r15
0x180035856  jz      short loc_18003586F
0x180035858  movsxd  rdx, edi
0x18003585b  mov     rcx, r15; String1
0x18003585e  mov     rdx, ds:rva ?g_szGrabmiFilterNormal@@3PAPEAGA[r14+rdx*8]; String2
0x180035866  call    _wcsicmp
0x18003586b  test    eax, eax
0x18003586d  jz      short loc_180035882
0x18003586f  inc     edi
0x180035871  movsxd  rax, edi
0x180035874  mov     rax, ds:rva ?g_szGrabmiFilterNormal@@3PAPEAGA[r14+rax*8]; ushort * near * g_szGrabmiFilterNormal ...
0x18003587c  cmp     [rax], r12w
0x180035880  jnz     short loc_180035853
0x180035882  mov     r12, [rbp+480h+var_4E8]
  ... truncated ...
```
