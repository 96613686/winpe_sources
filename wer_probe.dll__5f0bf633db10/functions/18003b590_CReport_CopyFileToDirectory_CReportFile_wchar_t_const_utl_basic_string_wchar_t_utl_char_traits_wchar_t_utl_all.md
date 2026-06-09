# CReport::CopyFileToDirectory(CReportFile *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18003b590`
- end: `0x18003bed2`
- name: `?CopyFileToDirectory@CReport@@IEAAJPEAVCReportFile@@PEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `2370`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003aa28`
- `0x180072c2c`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007db4`
- `0x180007de0`
- `0x180007e10`
- `0x180008568`
- `0x180009ad4`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000e7fc`
- `0x180014720`
- `0x18001dfac`
- `0x18001fe24`
- `0x180021634`
- `0x18002be60`
- `0x180039f70`
- `0x18003b590`
- `0x18003bf14`
- `0x18003db78`
- `0x1800426b4`
- `0x18004a370`
- `0x180050db0`
- `0x180075484`
- `0x1800757a8`
- `0x1800949e4`
- `0x1800974a0`
- `0x180097c3c`
- `0x180098b88`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd83`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003bdfb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003bdfb`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003b8dc`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003b8dc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003baf8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003baf8`

## string_xrefs

- `0x18003ba8b`: `onecore\windows\feedback\core\werdll\lib\report.cpp`
- `0x18003bac1`: `onecore\windows\feedback\core\werdll\lib\report.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CReport::CopyFileToDirectory(CReport *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  char v6; // r10
  LPCWSTR *v7; // r13
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // edi
  const wchar_t *v15; // rax
  unsigned int i; // r12d
  int v17; // eax
  int v18; // eax
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rcx
  unsigned int v23; // edx
  wchar_t *v24; // rcx
  int v25; // edx
  __int64 v26; // r9
  __int64 v27; // rdx
  unsigned int *v28; // r12
  HANDLE v29; // rcx
  __int64 v30; // r9
  unsigned int v31; // edx
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  int ParentDirectory; // eax
  int v37; // eax
  unsigned int v38; // r12d
  int v39; // eax
  wchar_t *v40; // rcx
  __int64 v41; // rdx
  DWORD LastError; // eax
  wchar_t **v43; // rcx
  int v44; // eax
  wchar_t *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r9
  unsigned int v48; // ebx
  int SqsFromFile; // eax
  signed int v50; // eax
  char v51; // bl
  int v53; // [rsp+20h] [rbp-E0h]
  __int64 v54; // [rsp+40h] [rbp-C0h] BYREF
  void **v55; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h]
  const wchar_t *v57; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpNewFileName; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v59; // [rsp+68h] [rbp-98h]
  CReport *v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  wchar_t *v62[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v63; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+D0h] [rbp-30h]
  wchar_t *v66[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 FileInformation; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v54 = a4;
  v4 = a3;
  v61 = a3;
  v60 = a1;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpNewFileName);
  v55 = &CFileByteStream::`vftable';
  hFile = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  FileInformation = 0;
  if ( !a2 || !v4 )
  {
    v14 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_6898268820d636d20e115db2eaa75970_Traceguids);
    goto LABEL_155;
  }
  v6 = *(_BYTE *)(a2 + 48);
  v7 = (LPCWSTR *)(a2 + 112);
  v8 = *(_QWORD *)(a2 + 120);
  v9 = *(_QWORD *)(a2 + 112);
  if ( v6 )
  {
    if ( v9 == v8 )
    {
      v10 = *(_QWORD *)(a2 + 56);
      if ( !v10 && !*(_QWORD *)(a2 + 72) )
        goto LABEL_7;
    }
LABEL_22:
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v9);
    goto LABEL_23;
  }
  if ( v9 != v8 )
  {
    if ( !*(_QWORD *)(a2 + 56) && !*(_QWORD *)(a2 + 72) )
      goto LABEL_23;
    goto LABEL_22;
  }
  v10 = *(_QWORD *)(a2 + 56);
  if ( !v10 )
    goto LABEL_22;
  if ( *(_QWORD *)(a2 + 72) )
  {
    if ( v9 == v8 )
    {
      v11 = *(_QWORD *)(a2 + 72);
      if ( v11 )
        goto LABEL_16;
    }
    goto LABEL_22;
  }
LABEL_7:
  v11 = 0;
LABEL_16:
  if ( *(_QWORD *)(a2 + 80) == *(_QWORD *)(a2 + 88) || !v6 && v9 == v8 && !v10 || v11 && !v10 )
    goto LABEL_22;
LABEL_23:
  if ( *(_QWORD *)(a2 + 56) )
  {
    if ( !*(_QWORD *)(a2 + 72) && (*(_DWORD *)(a2 + 4) & 0x10000000) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_30;
      v13 = 199;
LABEL_29:
      WPP_SF_(*((_QWORD *)v12 + 2), v13, &WPP_6898268820d636d20e115db2eaa75970_Traceguids);
LABEL_30:
      v14 = -2147467259;
      goto LABEL_155;
    }
    if ( *(_QWORD *)(a2 + 80) == *(_QWORD *)(a2 + 88) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v8, v9);
    v15 = *(const wchar_t **)(a2 + 80);
    v57 = v15;
    for ( i = 0; i < 0xC8; ++i )
    {
      if ( i )
        v17 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                &lpNewFileName,
                L"%ls\\%i_%ls",
                v4,
                i,
                v15);
      else
        v17 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                &lpNewFileName,
                L"%ls\\%ls",
                v4,
                v15);
      v14 = v17;
      if ( v17 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v20 = 200;
          v21 = (unsigned int)v17;
          goto LABEL_49;
        }
        goto LABEL_155;
      }
      v18 = CFileByteStream::OpenFile((CFileByteStream *)&v55, lpNewFileName, 0x40010000u, 1u, 0, 1u, 0, 0);
      v14 = v18;
      if ( v18 >= 0 )
        break;
      if ( v18 != -2147024816 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v20 = 201;
          goto LABEL_45;
        }
        goto LABEL_155;
      }
      v15 = v57;
      v4 = v61;
    }
    v22 = *(_QWORD *)(a2 + 72);
    if ( v22 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, &v55, 0);
      if ( v14 < 0 )
      {
        UtilMarkFileForDelete(hFile, v23);
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v25 = 202;
          v26 = *(_QWORD *)(a2 + 80);
          goto LABEL_55;
        }
        goto LABEL_155;
      }
      v27 = *(_QWORD *)(a2 + 72);
      *(_QWORD *)(a2 + 72) = 0;
      if ( v27 )
        utl::default_delete<CReportCabStream>::operator()();
      v28 = (unsigned int *)(a2 + 4);
    }
    else
    {
      v28 = (unsigned int *)(a2 + 4);
      if ( (*(_DWORD *)(a2 + 4) & 0x10000000) == 0 )
      {
        v29 = hFile;
        if ( !hFile )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(0, v9);
          v29 = hFile;
        }
        v64 = 0;
        v65 = 0;
        *(_QWORD *)&v63 = &v55;
        *((_QWORD *)&v63 + 1) = v54;
        LODWORD(v64) = *((_DWORD *)v60 + 1489);
        if ( !GetFileInformationByHandleEx(v29, FileCompressionInfo, &FileInformation, 0x10u)
          || (v30 = 1, !WORD4(FileInformation)) )
        {
          v30 = 0;
        }
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, __int64, __int64 (__fastcall *)(void *, union _LARGE_INTEGER, union _LARGE_INTEGER *, unsigned int, void *), __int64 (__fastcall *)(void *, const void *, unsigned int, void *), void (__fastcall *)(void *, unsigned int, const wchar_t *, char *)))(a2 + 56))(
                *(_QWORD *)(a2 + 64),
                &v63,
                0,
                v30,
                WerpcbSeekByteStream,
                WerpcbWriteByteStream,
                WerpcbLogger);
        *v28 |= 0x10000000u;
        if ( v14 < 0 )
        {
          UtilMarkFileForDelete(hFile, v31);
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              203,
              &WPP_6898268820d636d20e115db2eaa75970_Traceguids,
              *(_QWORD *)(a2 + 56),
              v14);
          goto LABEL_155;
        }
      }
    }
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
    goto LABEL_109;
  }
  v32 = *v7;
  if ( *(_QWORD *)(a2 + 112) == *(_QWORD *)(a2 + 120) )
  {
    if ( (*(_DWORD *)(a2 + 4) & 0x80000) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v32, v9);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
      goto LABEL_30;
    v13 = 210;
    goto LABEL_29;
  }
  v33 = UtilPathTail(v32);
  v57 = v33;
  if ( !v33 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v13 = 204;
    goto LABEL_29;
  }
  v18 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
          &lpNewFileName,
          L"%ls\\%ls",
          v4,
          v33);
  v14 = v18;
  if ( v18 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_155;
    v20 = 205;
LABEL_45:
    v21 = (unsigned int)v18;
    goto LABEL_49;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(&lpNewFileName)
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(
                           &lpNewFileName,
                           v34,
                           v35,
                           4) )
  {
    v14 = -2147024882;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_155;
    v20 = 206;
    v21 = 2147942414LL;
LABEL_49:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, v21);
    goto LABEL_155;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v66);
  ParentDirectory = UtilGetParentDirectory(*v7, v66);
  v14 = ParentDirectory;
  if ( ParentDirectory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1795,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\report.cpp",
      (const char *)(unsigned int)ParentDirectory,
      v53);
    goto LABEL_101;
  }
  v54 = 0;
  v37 = UtilVerifyAndLockDirectory(v66[0], (__int64)&v54);
  v14 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1798,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\report.cpp",
      (const char *)(unsigned int)v37,
      v53);
    goto LABEL_100;
  }
  v38 = 0;
  while ( v38 < 0xC8 && !CopyFileW(*v7, lpNewFileName, 1) )
  {
    if ( GetLastError() != 80 )
    {
      LastError = GetLastError();
      v39 = ERROR_HR_FROM_WIN32(LastError);
      v14 = v39;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v41 = 207;
LABEL_99:
        WPP_SF_d(*((_QWORD *)v40 + 2), v41, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, (unsigned int)v39);
      }
LABEL_100:
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v54);
LABEL_101:
      v43 = v66;
LABEL_102:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v43);
      goto LABEL_155;
    }
    v39 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            &lpNewFileName,
            L"%ls\\%i_%ls",
            v61,
            ++v38,
            v57);
    v14 = v39;
    if ( v39 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v41 = 208;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
  }
  v28 = (unsigned int *)(a2 + 4);
  if ( (*(_BYTE *)(a2 + 4) & 1) != 0 )
  {
    v44 = CReport::SafeDeleteFile(v60, *v7, *v28);
    if ( v44 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        209,
        (unsigned int)&WPP_6898268820d636d20e115db2eaa75970_Traceguids,
        (unsigned int)*v7,
        v44);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v54);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v66);
LABEL_109:
  *v28 &= ~1u;
  if ( CRegSetting::GetDwordData((CReport *)((char *)v60 + 50848))
    && (*(_DWORD *)a2 == 3 || (unsigned int)(*(_DWORD *)a2 - 7) <= 3) )
  {
    CFileByteStream::Close((CFileByteStream *)&v55);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v62);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            v62,
                            lpNewFileName,
                            (v59 - (__int64)lpNewFileName) >> 1) )
    {
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                              &lpNewFileName,
                              L".sqs") )
      {
        v48 = 0;
        while ( v48 < 0xC8 && UtilFileExists(lpNewFileName) )
        {
          SqsFromFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                          &lpNewFileName,
                          L"%ls\\%i_%ls.sqs",
                          v61,
                          ++v48,
                          v57);
          v14 = SqsFromFile;
          if ( SqsFromFile < 0 )
          {
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v46 = 213;
LABEL_130:
              v47 = (unsigned int)SqsFromFile;
              goto LABEL_117;
            }
            goto LABEL_118;
          }
        }
        SqsFromFile = CreateSqsFromFile(lpNewFileName);
        v14 = SqsFromFile;
        if ( SqsFromFile >= 0 )
        {
          *v28 |= 4u;
          if ( (int)UtilDeleteFilePath(v62[0]) >= 0 )
          {
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v62);
            goto LABEL_142;
          }
          v50 = GetLastError();
          v14 = v50;
          if ( v50 > 0 )
            v14 = (unsigned __int16)v50 | 0x80070000;
          v45 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v46 = 215;
            v47 = (unsigned int)v14;
            goto LABEL_117;
          }
        }
        else
        {
          v45 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v46 = 214;
            goto LABEL_130;
          }
        }
        goto LABEL_118;
      }
      v14 = -2147024882;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v46 = 212;
LABEL_116:
        v47 = 2147942414LL;
LABEL_117:
        WPP_SF_d(*((_QWORD *)v45 + 2), v46, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, v47);
      }
    }
    else
    {
      v14 = -2147024882;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v46 = 211;
        goto LABEL_116;
      }
    }
LABEL_118:
    v43 = v62;
    goto LABEL_102;
  }
LABEL_142:
  v51 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          v7,
          lpNewFileName,
          (v59 - (__int64)lpNewFileName) >> 1);
  v14 = v51 == 0 ? 0x8007000E : 0;
  SetFileAttributesW(lpNewFileName, 0x2080u);
  if ( v51 )
  {
    v14 = 0;
  }
  else
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v25 = 216;
      LODWORD(v26) = (_DWORD)lpNewFileName;
LABEL_55:
      WPP_SF_SD(*((_QWORD *)v24 + 2), v25, (unsigned int)&WPP_6898268820d636d20e115db2eaa75970_Traceguids, v26, v14);
    }
  }
LABEL_155:
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v55);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpNewFileName);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003b590  push    rbp
0x18003b592  push    rbx
0x18003b593  push    rsi
0x18003b594  push    rdi
0x18003b595  push    r12
0x18003b597  push    r13
0x18003b599  push    r14
0x18003b59b  push    r15
0x18003b59d  lea     rbp, [rsp-18h]
0x18003b5a2  sub     rsp, 118h
0x18003b5a9  mov     rax, cs:__security_cookie
0x18003b5b0  xor     rax, rsp
0x18003b5b3  mov     [rbp+50h+var_48], rax
0x18003b5b7  mov     [rsp+150h+var_110], r9
0x18003b5bc  mov     rdi, r8
0x18003b5bf  mov     [rbp+50h+var_C8], r8
0x18003b5c3  mov     rbx, rdx
0x18003b5c6  mov     [rbp+50h+var_D0], rcx
0x18003b5ca  lea     rcx, [rsp+150h+lpNewFileName]; void *
0x18003b5cf  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003b5d4  nop
0x18003b5d5  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18003b5dc  mov     [rsp+150h+var_108], rax
0x18003b5e1  xor     esi, esi
0x18003b5e3  mov     [rsp+150h+hFile], rsi
0x18003b5e8  xorps   xmm0, xmm0
0x18003b5eb  xor     eax, eax
0x18003b5ed  movups  [rbp+50h+var_A0], xmm0
0x18003b5f1  movups  [rbp+50h+var_90], xmm0
0x18003b5f5  mov     [rbp+50h+var_80], rax
0x18003b5f9  movups  [rbp+50h+FileInformation], xmm0
0x18003b5fd  test    rbx, rbx
0x18003b600  jz      loc_18003BE62
0x18003b606  test    rdi, rdi
0x18003b609  jz      loc_18003BE62
0x18003b60f  mov     r10b, [rbx+30h]
0x18003b613  lea     r13, [rbx+70h]
0x18003b617  mov     rcx, [r13+8]
0x18003b61b  mov     rdx, [r13+0]
0x18003b61f  test    r10b, r10b
0x18003b622  jz      short loc_18003B63D
0x18003b624  cmp     rdx, rcx
0x18003b627  jnz     short loc_18003B695
0x18003b629  mov     r8, [rbx+38h]
0x18003b62d  test    r8, r8
0x18003b630  jnz     short loc_18003B695
0x18003b632  cmp     [rbx+48h], rsi
0x18003b636  jnz     short loc_18003B695
0x18003b638  mov     r9, rsi
0x18003b63b  jmp     short loc_18003B672
0x18003b63d  cmp     rdx, rcx
0x18003b640  jz      short loc_18003B650
0x18003b642  cmp     [rbx+38h], rsi
0x18003b646  jnz     short loc_18003B695
0x18003b648  cmp     [rbx+48h], rsi
0x18003b64c  jnz     short loc_18003B695
0x18003b64e  jmp     short loc_18003B69A
0x18003b650  mov     r8, [rbx+38h]
0x18003b654  test    r8, r8
0x18003b657  jz      short loc_18003B695
0x18003b659  cmp     [rbx+48h], rsi
0x18003b65d  jz      short loc_18003B638
0x18003b65f  cmp     rdx, rcx
0x18003b662  jnz     short loc_18003B695
0x18003b664  test    r8, r8
0x18003b667  jz      short loc_18003B695
0x18003b669  mov     r9, [rbx+48h]
0x18003b66d  test    r9, r9
0x18003b670  jz      short loc_18003B695
0x18003b672  mov     rax, [rbx+58h]
0x18003b676  cmp     [rbx+50h], rax
0x18003b67a  jz      short loc_18003B695
0x18003b67c  test    r10b, r10b
0x18003b67f  jnz     short loc_18003B68B
0x18003b681  cmp     rdx, rcx
0x18003b684  jnz     short loc_18003B68B
0x18003b686  test    r8, r8
0x18003b689  jz      short loc_18003B695
0x18003b68b  test    r9, r9
0x18003b68e  jz      short loc_18003B69A
0x18003b690  test    r8, r8
0x18003b693  jnz     short loc_18003B69A
0x18003b695  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b69a  lea     r14, WPP_GLOBAL_Control
0x18003b6a1  lea     r15, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18003b6a8  cmp     [rbx+38h], rsi
0x18003b6ac  jz      loc_18003B987
0x18003b6b2  cmp     [rbx+48h], rsi
0x18003b6b6  jnz     short loc_18003B6EE
0x18003b6b8  test    dword ptr [rbx+4], 10000000h
0x18003b6bf  jz      short loc_18003B6EE
0x18003b6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b6c8  cmp     rcx, r14
0x18003b6cb  jz      short loc_18003B6E4
0x18003b6cd  test    byte ptr [rcx+1Ch], 2
0x18003b6d1  jz      short loc_18003B6E4
0x18003b6d3  mov     edx, 0C7h
0x18003b6d8  mov     r8, r15
0x18003b6db  mov     rcx, [rcx+10h]
0x18003b6df  call    WPP_SF_
0x18003b6e4  mov     edi, 80004005h
0x18003b6e9  jmp     loc_18003BE9B
0x18003b6ee  mov     rax, [rbx+58h]
0x18003b6f2  cmp     [rbx+50h], rax
0x18003b6f6  jnz     short loc_18003B6FD
0x18003b6f8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b6fd  mov     rax, [rbx+50h]
0x18003b701  mov     [rsp+150h+var_F8], rax
0x18003b706  mov     r12d, esi
0x18003b709  mov     esi, 1
0x18003b70e  cmp     r12d, 0C8h
0x18003b715  jnb     loc_18003B7F4
0x18003b71b  mov     r8, rdi
0x18003b71e  lea     rcx, [rsp+150h+lpNewFileName]
0x18003b723  test    r12d, r12d
0x18003b726  jnz     short loc_18003B739
0x18003b728  mov     r9, rax
0x18003b72b  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18003b732  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003b737  jmp     short loc_18003B74D
0x18003b739  mov     [rsp+150h+var_130], rax
0x18003b73e  mov     r9d, r12d
0x18003b741  lea     rdx, aLsILs; "%ls\\%i_%ls"
0x18003b748  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003b74d  mov     edi, eax
0x18003b74f  xor     eax, eax
0x18003b751  test    edi, edi
0x18003b753  js      short loc_18003B7C1
0x18003b755  mov     [rsp+150h+var_118], rax; void *
0x18003b75a  mov     [rsp+150h+var_120], eax; unsigned int
0x18003b75e  mov     [rsp+150h+var_128], esi; unsigned int
0x18003b762  mov     [rsp+150h+var_130], rax; struct _SECURITY_ATTRIBUTES *
0x18003b767  mov     r9d, esi; unsigned int
0x18003b76a  mov     r8d, 40010000h; unsigned int
0x18003b770  mov     rdx, [rsp+150h+lpNewFileName]; wchar_t *
0x18003b775  lea     rcx, [rsp+150h+var_108]; this
0x18003b77a  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18003b77f  mov     edi, eax
0x18003b781  test    eax, eax
0x18003b783  jns     short loc_18003B7F4
0x18003b785  cmp     eax, 80070050h
0x18003b78a  jnz     short loc_18003B79D
0x18003b78c  add     r12d, esi
0x18003b78f  mov     rax, [rsp+150h+var_F8]
0x18003b794  mov     rdi, [rbp+50h+var_C8]
0x18003b798  jmp     loc_18003B70E
0x18003b79d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7a4  cmp     rcx, r14
0x18003b7a7  jz      loc_18003BE9B
0x18003b7ad  test    [rcx+1Ch], sil
0x18003b7b1  jz      loc_18003BE9B
0x18003b7b7  mov     edx, 0C9h
0x18003b7bc  mov     r9d, eax
0x18003b7bf  jmp     short loc_18003B7E3
0x18003b7c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b7c8  cmp     rcx, r14
0x18003b7cb  jz      loc_18003BE9B
0x18003b7d1  test    [rcx+1Ch], sil
0x18003b7d5  jz      loc_18003BE9B
0x18003b7db  mov     edx, 0C8h
0x18003b7e0  mov     r9d, edi
0x18003b7e3  mov     r8, r15
0x18003b7e6  mov     rcx, [rcx+10h]
0x18003b7ea  call    WPP_SF_d
0x18003b7ef  jmp     loc_18003BE9B
0x18003b7f4  mov     rcx, [rbx+48h]
0x18003b7f8  xor     edi, edi
0x18003b7fa  test    rcx, rcx
0x18003b7fd  jz      short loc_18003B878
0x18003b7ff  mov     rax, [rcx]
0x18003b802  xor     r8d, r8d
0x18003b805  lea     rdx, [rsp+150h+var_108]
0x18003b80a  mov     rax, [rax+18h]
0x18003b80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b813  mov     edi, eax
0x18003b815  test    eax, eax
0x18003b817  jns     short loc_18003B85B
0x18003b819  mov     rcx, [rsp+150h+hFile]; FileHandle
0x18003b81e  call    ?UtilMarkFileForDelete@@YAXPEAXK@Z; UtilMarkFileForDelete(void *,ulong)
0x18003b823  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b82a  cmp     rcx, r14
0x18003b82d  jz      loc_18003BE9B
0x18003b833  test    [rcx+1Ch], sil
0x18003b837  jz      loc_18003BE9B
0x18003b83d  mov     edx, 0CAh
0x18003b842  mov     r9, [rbx+50h]
0x18003b846  mov     dword ptr [rsp+150h+var_130], edi
0x18003b84a  mov     r8, r15
0x18003b84d  mov     rcx, [rcx+10h]
0x18003b851  call    WPP_SF_SD
0x18003b856  jmp     loc_18003BE9B
0x18003b85b  mov     rdx, [rbx+48h]
0x18003b85f  xor     edi, edi
0x18003b861  mov     [rbx+48h], rdi
0x18003b865  test    rdx, rdx
0x18003b868  jz      short loc_18003B86F
0x18003b86a  call    ??R?$default_delete@VCReportCabStream@@@utl@@QEBAXPEAVCReportCabStream@@@Z; utl::default_delete<CReportCabStream>::operator()(CReportCabStream *)
0x18003b86f  lea     r12, [rbx+4]
0x18003b873  jmp     loc_18003B97A
0x18003b878  lea     r12, [rbx+4]
0x18003b87c  test    dword ptr [r12], 10000000h
0x18003b884  jnz     loc_18003B97A
0x18003b88a  mov     rcx, [rsp+150h+hFile]
0x18003b88f  test    rcx, rcx
0x18003b892  jnz     short loc_18003B89E
0x18003b894  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003b899  mov     rcx, [rsp+150h+hFile]; hFile
0x18003b89e  xorps   xmm0, xmm0
0x18003b8a1  xor     eax, eax
0x18003b8a3  movups  [rbp+50h+var_A0], xmm0
0x18003b8a7  movups  [rbp+50h+var_90], xmm0
0x18003b8ab  mov     [rbp+50h+var_80], rax
0x18003b8af  lea     rax, [rsp+150h+var_108]
0x18003b8b4  mov     qword ptr [rbp+50h+var_A0], rax
0x18003b8b8  mov     rax, [rsp+150h+var_110]
0x18003b8bd  mov     qword ptr [rbp+50h+var_A0+8], rax
0x18003b8c1  mov     rax, [rbp+50h+var_D0]
0x18003b8c5  mov     eax, [rax+1744h]
0x18003b8cb  mov     dword ptr [rbp+50h+var_90], eax
0x18003b8ce  mov     r9d, 10h; dwBufferSize
0x18003b8d4  lea     r8, [rbp+50h+FileInformation]; lpFileInformation
0x18003b8d8  lea     edx, [r9-8]; FileInformationClass
0x18003b8dc  call    cs:__imp_GetFileInformationByHandleEx
0x18003b8e2  test    eax, eax
0x18003b8e4  jz      short loc_18003B8EF
0x18003b8e6  cmp     word ptr [rbp+50h+FileInformation+8], di
0x18003b8ea  mov     r9d, esi
0x18003b8ed  jnz     short loc_18003B8F2
0x18003b8ef  mov     r9d, edi
0x18003b8f2  lea     rax, ?WerpcbLogger@@YAXPEAXKPEB_WPEAD@Z; WerpcbLogger(void *,ulong,wchar_t const *,char *)
0x18003b8f9  mov     qword ptr [rsp+150h+var_120], rax
0x18003b8fe  lea     rax, ?WerpcbWriteByteStream@@YAJPEAXPEBXK0@Z; WerpcbWriteByteStream(void *,void const *,ulong,void *)
0x18003b905  mov     qword ptr [rsp+150h+var_128], rax
0x18003b90a  lea     rax, ?WerpcbSeekByteStream@@YAJPEAXT_LARGE_INTEGER@@PEAT1@K0@Z; WerpcbSeekByteStream(void *,_LARGE_INTEGER,_LARGE_INTEGER *,ulong,void *)
0x18003b911  mov     [rsp+150h+var_130], rax
0x18003b916  xor     r8d, r8d
0x18003b919  lea     rdx, [rbp+50h+var_A0]
0x18003b91d  mov     rcx, [rbx+40h]
0x18003b921  mov     rax, [rbx+38h]
0x18003b925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b92a  mov     edi, eax
0x18003b92c  bts     dword ptr [r12], 1Ch
0x18003b932  test    eax, eax
0x18003b934  jns     short loc_18003B978
0x18003b936  mov     rcx, [rsp+150h+hFile]; FileHandle
0x18003b93b  call    ?UtilMarkFileForDelete@@YAXPEAXK@Z; UtilMarkFileForDelete(void *,ulong)
0x18003b940  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b947  cmp     rcx, r14
0x18003b94a  jz      loc_18003BE9B
0x18003b950  test    [rcx+1Ch], sil
0x18003b954  jz      loc_18003BE9B
0x18003b95a  mov     edx, 0CBh
0x18003b95f  mov     dword ptr [rsp+150h+var_130], edi
0x18003b963  mov     r9, [rbx+38h]
0x18003b967  mov     r8, r15
0x18003b96a  mov     rcx, [rcx+10h]
0x18003b96e  call    WPP_SF_qD
0x18003b973  jmp     loc_18003BE9B
0x18003b978  xor     edi, edi
0x18003b97a  mov     [rbx+38h], rdi
0x18003b97e  mov     [rbx+40h], rdi
0x18003b982  jmp     loc_18003BC07
0x18003b987  mov     rcx, [r13+0]; wchar_t *
0x18003b98b  cmp     rcx, [r13+8]
0x18003b98f  jz      loc_18003BE30
0x18003b995  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18003b99a  mov     [rsp+150h+var_F8], rax
0x18003b99f  test    rax, rax
0x18003b9a2  jnz     short loc_18003B9CB
0x18003b9a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9ab  cmp     rcx, r14
0x18003b9ae  jz      loc_18003B6E4
0x18003b9b4  lea     esi, [rax+1]
0x18003b9b7  test    [rcx+1Ch], sil
0x18003b9bb  jz      loc_18003B6E4
0x18003b9c1  mov     edx, 0CCh
0x18003b9c6  jmp     loc_18003B6D8
0x18003b9cb  mov     r9, rax
0x18003b9ce  mov     r8, rdi
0x18003b9d1  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18003b9d8  lea     rcx, [rsp+150h+lpNewFileName]
0x18003b9dd  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003b9e2  mov     edi, eax
0x18003b9e4  test    eax, eax
0x18003b9e6  jns     short loc_18003BA11
0x18003b9e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b9ef  cmp     rcx, r14
0x18003b9f2  jz      loc_18003BE9B
0x18003b9f8  mov     esi, 1
0x18003b9fd  test    [rcx+1Ch], sil
0x18003ba01  jz      loc_18003BE9B
0x18003ba07  mov     edx, 0CDh
0x18003ba0c  jmp     loc_18003B7BC
0x18003ba11  lea     rcx, [rsp+150h+lpNewFileName]
0x18003ba16  call    ?starts_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(wchar_t const *)
0x18003ba1b  test    al, al
0x18003ba1d  jnz     short loc_18003BA67
0x18003ba1f  mov     r9d, 4
0x18003ba25  lea     rcx, [rsp+150h+lpNewFileName]
0x18003ba2a  call    ?insert@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_KPEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert(unsigned __int64,wchar_t const *,unsigned __int64)
  ... truncated ...
```
