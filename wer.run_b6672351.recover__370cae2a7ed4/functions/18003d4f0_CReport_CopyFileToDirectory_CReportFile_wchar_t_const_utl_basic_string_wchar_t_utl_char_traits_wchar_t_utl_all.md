# CReport::CopyFileToDirectory(CReportFile *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18003d4f0`
- end: `0x18003de57`
- name: `?CopyFileToDirectory@CReport@@IEAAJPEAVCReportFile@@PEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `2407`
- prototype: ``
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c96c`
- `0x180075fcc`

## callees

- `0x180004c64`
- `0x180007f74`
- `0x180007fa0`
- `0x180007fd8`
- `0x180009684`
- `0x18000ad98`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000db80`
- `0x18000e31c`
- `0x180010280`
- `0x180018000`
- `0x18001c368`
- `0x18001e658`
- `0x180020680`
- `0x18002219c`
- `0x18002d75c`
- `0x18003be90`
- `0x18003d4f0`
- `0x18003de9c`
- `0x18003fb94`
- `0x18004373c`
- `0x18004c6a0`
- `0x180053300`
- `0x180078910`
- `0x180078c54`
- `0x180098c0c`
- `0x18009b81c`
- `0x18009c010`
- `0x18009d104`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003da74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dcfb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003dd79`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003dd79`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003d83c`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18003d83c`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003da5e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003da5e`

## string_xrefs

- `0x18003d9f1`: `onecore\windows\feedback\core\werdll\lib\report.cpp`
- `0x18003da27`: `onecore\windows\feedback\core\werdll\lib\report.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CReport::CopyFileToDirectory(CReport *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v6; // r8
  char v7; // r10
  LPCWSTR *v8; // r13
  __int64 v9; // rcx
  __int64 v10; // rdx
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
  CReport *v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  wchar_t *v61[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+D0h] [rbp-30h]
  wchar_t *v65[4]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 FileInformation; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v54 = a4;
  v4 = a3;
  v60 = a3;
  v59 = a1;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpNewFileName);
  v55 = &CFileByteStream::`vftable';
  hFile = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  FileInformation = 0;
  if ( !a2 || !v4 )
  {
    v14 = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
    goto LABEL_155;
  }
  v7 = *(_BYTE *)(a2 + 48);
  v8 = (LPCWSTR *)(a2 + 112);
  v9 = *(_QWORD *)(a2 + 120);
  v10 = *(_QWORD *)(a2 + 112);
  if ( v7 )
  {
    if ( v10 == v9 )
    {
      v6 = *(_QWORD *)(a2 + 56);
      if ( !v6 && !*(_QWORD *)(a2 + 72) )
        goto LABEL_7;
    }
LABEL_22:
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v10, v6);
    goto LABEL_23;
  }
  if ( v10 != v9 )
  {
    if ( !*(_QWORD *)(a2 + 56) && !*(_QWORD *)(a2 + 72) )
      goto LABEL_23;
    goto LABEL_22;
  }
  v6 = *(_QWORD *)(a2 + 56);
  if ( !v6 )
    goto LABEL_22;
  if ( *(_QWORD *)(a2 + 72) )
  {
    if ( v10 == v9 )
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
  if ( *(_QWORD *)(a2 + 80) == *(_QWORD *)(a2 + 88) || !v7 && v10 == v9 && !v6 || v11 && !v6 )
    goto LABEL_22;
LABEL_23:
  if ( *(_QWORD *)(a2 + 56) )
  {
    if ( !*(_QWORD *)(a2 + 72) && (*(_DWORD *)(a2 + 4) & 0x10000000) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_30;
      v13 = 200;
LABEL_29:
      WPP_SF_(*((_QWORD *)v12 + 2), v13, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
LABEL_30:
      v14 = -2147467259;
      goto LABEL_155;
    }
    if ( *(_QWORD *)(a2 + 80) == *(_QWORD *)(a2 + 88) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9, v10, v6);
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
          v20 = 201;
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
          v20 = 202;
          goto LABEL_45;
        }
        goto LABEL_155;
      }
      v15 = v57;
      v4 = v60;
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
          v25 = 203;
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
          MicrosoftTelemetryAssertTriggeredNoArgs(0, v10, v6);
          v29 = hFile;
        }
        v63 = 0;
        v64 = 0;
        *(_QWORD *)&v62 = &v55;
        *((_QWORD *)&v62 + 1) = v54;
        LODWORD(v63) = *((_DWORD *)v59 + 1489);
        if ( !GetFileInformationByHandleEx(v29, FileCompressionInfo, &FileInformation, 0x10u)
          || (v30 = 1, !WORD4(FileInformation)) )
        {
          v30 = 0;
        }
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, __int64, __int64 (__fastcall *)(void *, union _LARGE_INTEGER, union _LARGE_INTEGER *, unsigned int, void *), __int64 (__fastcall *)(void *, const void *, unsigned int, void *), void (__fastcall *)(void *, unsigned int, const wchar_t *, char *)))(a2 + 56))(
                *(_QWORD *)(a2 + 64),
                &v62,
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
              204,
              WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
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
  v32 = *v8;
  if ( *(_QWORD *)(a2 + 112) == *(_QWORD *)(a2 + 120) )
  {
    if ( (*(_DWORD *)(a2 + 4) & 0x80000) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v32, v10, v6);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
      goto LABEL_30;
    v13 = 211;
    goto LABEL_29;
  }
  v33 = UtilPathTail(v32);
  v57 = v33;
  if ( !v33 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_30;
    v13 = 205;
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
    v20 = 206;
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
    v20 = 207;
    v21 = 2147942414LL;
LABEL_49:
    WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v21);
    goto LABEL_155;
  }
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v65);
  ParentDirectory = UtilGetParentDirectory(*v8, v65);
  v14 = ParentDirectory;
  if ( ParentDirectory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B4,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\report.cpp",
      (const char *)(unsigned int)ParentDirectory,
      v53);
    goto LABEL_101;
  }
  v54 = 0;
  v37 = UtilVerifyAndLockDirectory(v65[0], (__int64)&v54);
  v14 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B7,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\report.cpp",
      (const char *)(unsigned int)v37,
      v53);
    goto LABEL_100;
  }
  v38 = 0;
  while ( v38 < 0xC8 && !CopyFileW(*v8, lpNewFileName, 1) )
  {
    if ( GetLastError() != 80 )
    {
      LastError = GetLastError();
      v39 = ERROR_HR_FROM_WIN32(LastError);
      v14 = v39;
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v41 = 208;
LABEL_99:
        WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, (unsigned int)v39);
      }
LABEL_100:
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v54);
LABEL_101:
      v43 = v65;
LABEL_102:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v43);
      goto LABEL_155;
    }
    v39 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            &lpNewFileName,
            L"%ls\\%i_%ls",
            v60,
            ++v38,
            v57);
    v14 = v39;
    if ( v39 < 0 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v41 = 209;
        goto LABEL_99;
      }
      goto LABEL_100;
    }
  }
  v28 = (unsigned int *)(a2 + 4);
  if ( (*(_BYTE *)(a2 + 4) & 1) != 0 )
  {
    v44 = CReport::SafeDeleteFile(v59, *v8, *v28);
    if ( v44 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        210,
        (unsigned int)WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
        (unsigned int)*v8,
        v44);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v54);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v65);
LABEL_109:
  *v28 &= ~1u;
  if ( CRegSetting::GetDwordData((CReport *)((char *)v59 + 50848))
    && (*(_DWORD *)a2 == 3 || (unsigned int)(*(_DWORD *)a2 - 7) <= 3) )
  {
    CFileByteStream::Close((CFileByteStream *)&v55);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v61);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            v61,
                            (void *)lpNewFileName) )
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
                          v60,
                          ++v48,
                          v57);
          v14 = SqsFromFile;
          if ( SqsFromFile < 0 )
          {
            v45 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v46 = 214;
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
          if ( (int)UtilDeleteFilePath(v61[0]) >= 0 )
          {
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v61);
            goto LABEL_142;
          }
          v50 = GetLastError();
          v14 = v50;
          if ( v50 > 0 )
            v14 = (unsigned __int16)v50 | 0x80070000;
          v45 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v46 = 216;
            v47 = (unsigned int)v14;
            goto LABEL_117;
          }
        }
        else
        {
          v45 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v46 = 215;
            goto LABEL_130;
          }
        }
        goto LABEL_118;
      }
      v14 = -2147024882;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v46 = 213;
LABEL_116:
        v47 = 2147942414LL;
LABEL_117:
        WPP_SF_d(*((_QWORD *)v45 + 2), v46, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v47);
      }
    }
    else
    {
      v14 = -2147024882;
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v46 = 212;
        goto LABEL_116;
      }
    }
LABEL_118:
    v43 = v61;
    goto LABEL_102;
  }
LABEL_142:
  v51 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v8, (void *)lpNewFileName);
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
      v25 = 217;
      LODWORD(v26) = (_DWORD)lpNewFileName;
LABEL_55:
      WPP_SF_SD(*((_QWORD *)v24 + 2), v25, (unsigned int)WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v26, v14);
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
0x18003d4f0  push    rbp
0x18003d4f2  push    rbx
0x18003d4f3  push    rsi
0x18003d4f4  push    rdi
0x18003d4f5  push    r12
0x18003d4f7  push    r13
0x18003d4f9  push    r14
0x18003d4fb  push    r15
0x18003d4fd  lea     rbp, [rsp-18h]
0x18003d502  sub     rsp, 118h
0x18003d509  mov     rax, cs:__security_cookie
0x18003d510  xor     rax, rsp
0x18003d513  mov     [rbp+50h+var_48], rax
0x18003d517  mov     [rsp+150h+var_110], r9
0x18003d51c  mov     rdi, r8
0x18003d51f  mov     [rbp+50h+var_C8], r8
0x18003d523  mov     rbx, rdx
0x18003d526  mov     [rbp+50h+var_D0], rcx
0x18003d52a  lea     rcx, [rsp+150h+lpNewFileName]; void *
0x18003d52f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18003d534  nop
0x18003d535  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18003d53c  mov     [rsp+150h+var_108], rax
0x18003d541  xor     esi, esi
0x18003d543  mov     [rsp+150h+hFile], rsi
0x18003d548  xorps   xmm0, xmm0
0x18003d54b  xor     eax, eax
0x18003d54d  movups  [rbp+50h+var_A0], xmm0
0x18003d551  movups  [rbp+50h+var_90], xmm0
0x18003d555  mov     [rbp+50h+var_80], rax
0x18003d559  movups  [rbp+50h+FileInformation], xmm0
0x18003d55d  test    rbx, rbx
0x18003d560  jz      loc_18003DDE6
0x18003d566  test    rdi, rdi
0x18003d569  jz      loc_18003DDE6
0x18003d56f  mov     r10b, [rbx+30h]
0x18003d573  lea     r13, [rbx+70h]
0x18003d577  mov     rcx, [r13+8]
0x18003d57b  mov     rdx, [r13+0]
0x18003d57f  test    r10b, r10b
0x18003d582  jz      short loc_18003D59D
0x18003d584  cmp     rdx, rcx
0x18003d587  jnz     short loc_18003D5F5
0x18003d589  mov     r8, [rbx+38h]
0x18003d58d  test    r8, r8
0x18003d590  jnz     short loc_18003D5F5
0x18003d592  cmp     [rbx+48h], rsi
0x18003d596  jnz     short loc_18003D5F5
0x18003d598  mov     r9, rsi
0x18003d59b  jmp     short loc_18003D5D2
0x18003d59d  cmp     rdx, rcx
0x18003d5a0  jz      short loc_18003D5B0
0x18003d5a2  cmp     [rbx+38h], rsi
0x18003d5a6  jnz     short loc_18003D5F5
0x18003d5a8  cmp     [rbx+48h], rsi
0x18003d5ac  jnz     short loc_18003D5F5
0x18003d5ae  jmp     short loc_18003D5FA
0x18003d5b0  mov     r8, [rbx+38h]
0x18003d5b4  test    r8, r8
0x18003d5b7  jz      short loc_18003D5F5
0x18003d5b9  cmp     [rbx+48h], rsi
0x18003d5bd  jz      short loc_18003D598
0x18003d5bf  cmp     rdx, rcx
0x18003d5c2  jnz     short loc_18003D5F5
0x18003d5c4  test    r8, r8
0x18003d5c7  jz      short loc_18003D5F5
0x18003d5c9  mov     r9, [rbx+48h]
0x18003d5cd  test    r9, r9
0x18003d5d0  jz      short loc_18003D5F5
0x18003d5d2  mov     rax, [rbx+58h]
0x18003d5d6  cmp     [rbx+50h], rax
0x18003d5da  jz      short loc_18003D5F5
0x18003d5dc  test    r10b, r10b
0x18003d5df  jnz     short loc_18003D5EB
0x18003d5e1  cmp     rdx, rcx
0x18003d5e4  jnz     short loc_18003D5EB
0x18003d5e6  test    r8, r8
0x18003d5e9  jz      short loc_18003D5F5
0x18003d5eb  test    r9, r9
0x18003d5ee  jz      short loc_18003D5FA
0x18003d5f0  test    r8, r8
0x18003d5f3  jnz     short loc_18003D5FA
0x18003d5f5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d5fa  lea     r14, WPP_GLOBAL_Control
0x18003d601  lea     r15, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18003d608  cmp     [rbx+38h], rsi
0x18003d60c  jz      loc_18003D8ED
0x18003d612  cmp     [rbx+48h], rsi
0x18003d616  jnz     short loc_18003D64E
0x18003d618  test    dword ptr [rbx+4], 10000000h
0x18003d61f  jz      short loc_18003D64E
0x18003d621  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d628  cmp     rcx, r14
0x18003d62b  jz      short loc_18003D644
0x18003d62d  test    byte ptr [rcx+1Ch], 2
0x18003d631  jz      short loc_18003D644
0x18003d633  mov     edx, 0C8h
0x18003d638  mov     r8, r15
0x18003d63b  mov     rcx, [rcx+10h]
0x18003d63f  call    WPP_SF_
0x18003d644  mov     edi, 80004005h
0x18003d649  jmp     loc_18003DE1F
0x18003d64e  mov     rax, [rbx+58h]
0x18003d652  cmp     [rbx+50h], rax
0x18003d656  jnz     short loc_18003D65D
0x18003d658  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d65d  mov     rax, [rbx+50h]
0x18003d661  mov     [rsp+150h+var_F8], rax
0x18003d666  mov     r12d, esi
0x18003d669  mov     esi, 1
0x18003d66e  cmp     r12d, 0C8h
0x18003d675  jnb     loc_18003D754
0x18003d67b  mov     r8, rdi
0x18003d67e  lea     rcx, [rsp+150h+lpNewFileName]
0x18003d683  test    r12d, r12d
0x18003d686  jnz     short loc_18003D699
0x18003d688  mov     r9, rax
0x18003d68b  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18003d692  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003d697  jmp     short loc_18003D6AD
0x18003d699  mov     [rsp+150h+var_130], rax
0x18003d69e  mov     r9d, r12d
0x18003d6a1  lea     rdx, aLsILs; "%ls\\%i_%ls"
0x18003d6a8  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003d6ad  mov     edi, eax
0x18003d6af  xor     eax, eax
0x18003d6b1  test    edi, edi
0x18003d6b3  js      short loc_18003D721
0x18003d6b5  mov     [rsp+150h+var_118], rax; void *
0x18003d6ba  mov     [rsp+150h+var_120], eax; unsigned int
0x18003d6be  mov     [rsp+150h+var_128], esi; unsigned int
0x18003d6c2  mov     [rsp+150h+var_130], rax; struct _SECURITY_ATTRIBUTES *
0x18003d6c7  mov     r9d, esi; unsigned int
0x18003d6ca  mov     r8d, 40010000h; unsigned int
0x18003d6d0  mov     rdx, [rsp+150h+lpNewFileName]; wchar_t *
0x18003d6d5  lea     rcx, [rsp+150h+var_108]; this
0x18003d6da  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18003d6df  mov     edi, eax
0x18003d6e1  test    eax, eax
0x18003d6e3  jns     short loc_18003D754
0x18003d6e5  cmp     eax, 80070050h
0x18003d6ea  jnz     short loc_18003D6FD
0x18003d6ec  add     r12d, esi
0x18003d6ef  mov     rax, [rsp+150h+var_F8]
0x18003d6f4  mov     rdi, [rbp+50h+var_C8]
0x18003d6f8  jmp     loc_18003D66E
0x18003d6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d704  cmp     rcx, r14
0x18003d707  jz      loc_18003DE1F
0x18003d70d  test    [rcx+1Ch], sil
0x18003d711  jz      loc_18003DE1F
0x18003d717  mov     edx, 0CAh
0x18003d71c  mov     r9d, eax
0x18003d71f  jmp     short loc_18003D743
0x18003d721  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d728  cmp     rcx, r14
0x18003d72b  jz      loc_18003DE1F
0x18003d731  test    [rcx+1Ch], sil
0x18003d735  jz      loc_18003DE1F
0x18003d73b  mov     edx, 0C9h
0x18003d740  mov     r9d, edi
0x18003d743  mov     r8, r15
0x18003d746  mov     rcx, [rcx+10h]
0x18003d74a  call    WPP_SF_d
0x18003d74f  jmp     loc_18003DE1F
0x18003d754  mov     rcx, [rbx+48h]
0x18003d758  xor     edi, edi
0x18003d75a  test    rcx, rcx
0x18003d75d  jz      short loc_18003D7D8
0x18003d75f  mov     rax, [rcx]
0x18003d762  xor     r8d, r8d
0x18003d765  lea     rdx, [rsp+150h+var_108]
0x18003d76a  mov     rax, [rax+18h]
0x18003d76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d773  mov     edi, eax
0x18003d775  test    eax, eax
0x18003d777  jns     short loc_18003D7BB
0x18003d779  mov     rcx, [rsp+150h+hFile]; FileHandle
0x18003d77e  call    ?UtilMarkFileForDelete@@YAXPEAXK@Z; UtilMarkFileForDelete(void *,ulong)
0x18003d783  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d78a  cmp     rcx, r14
0x18003d78d  jz      loc_18003DE1F
0x18003d793  test    [rcx+1Ch], sil
0x18003d797  jz      loc_18003DE1F
0x18003d79d  mov     edx, 0CBh
0x18003d7a2  mov     r9, [rbx+50h]
0x18003d7a6  mov     dword ptr [rsp+150h+var_130], edi
0x18003d7aa  mov     r8, r15
0x18003d7ad  mov     rcx, [rcx+10h]
0x18003d7b1  call    WPP_SF_SD
0x18003d7b6  jmp     loc_18003DE1F
0x18003d7bb  mov     rdx, [rbx+48h]
0x18003d7bf  xor     edi, edi
0x18003d7c1  mov     [rbx+48h], rdi
0x18003d7c5  test    rdx, rdx
0x18003d7c8  jz      short loc_18003D7CF
0x18003d7ca  call    ??R?$default_delete@VCReportCabStream@@@utl@@QEBAXPEAVCReportCabStream@@@Z; utl::default_delete<CReportCabStream>::operator()(CReportCabStream *)
0x18003d7cf  lea     r12, [rbx+4]
0x18003d7d3  jmp     loc_18003D8E0
0x18003d7d8  lea     r12, [rbx+4]
0x18003d7dc  test    dword ptr [r12], 10000000h
0x18003d7e4  jnz     loc_18003D8E0
0x18003d7ea  mov     rcx, [rsp+150h+hFile]
0x18003d7ef  test    rcx, rcx
0x18003d7f2  jnz     short loc_18003D7FE
0x18003d7f4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003d7f9  mov     rcx, [rsp+150h+hFile]; hFile
0x18003d7fe  xorps   xmm0, xmm0
0x18003d801  xor     eax, eax
0x18003d803  movups  [rbp+50h+var_A0], xmm0
0x18003d807  movups  [rbp+50h+var_90], xmm0
0x18003d80b  mov     [rbp+50h+var_80], rax
0x18003d80f  lea     rax, [rsp+150h+var_108]
0x18003d814  mov     qword ptr [rbp+50h+var_A0], rax
0x18003d818  mov     rax, [rsp+150h+var_110]
0x18003d81d  mov     qword ptr [rbp+50h+var_A0+8], rax
0x18003d821  mov     rax, [rbp+50h+var_D0]
0x18003d825  mov     eax, [rax+1744h]
0x18003d82b  mov     dword ptr [rbp+50h+var_90], eax
0x18003d82e  mov     r9d, 10h; dwBufferSize
0x18003d834  lea     r8, [rbp+50h+FileInformation]; lpFileInformation
0x18003d838  lea     edx, [r9-8]; FileInformationClass
0x18003d83c  call    cs:__imp_GetFileInformationByHandleEx
0x18003d843  nop     dword ptr [rax+rax+00h]
0x18003d848  test    eax, eax
0x18003d84a  jz      short loc_18003D855
0x18003d84c  cmp     word ptr [rbp+50h+FileInformation+8], di
0x18003d850  mov     r9d, esi
0x18003d853  jnz     short loc_18003D858
0x18003d855  mov     r9d, edi
0x18003d858  lea     rax, ?WerpcbLogger@@YAXPEAXKPEB_WPEAD@Z; WerpcbLogger(void *,ulong,wchar_t const *,char *)
0x18003d85f  mov     qword ptr [rsp+150h+var_120], rax
0x18003d864  lea     rax, ?WerpcbWriteByteStream@@YAJPEAXPEBXK0@Z; WerpcbWriteByteStream(void *,void const *,ulong,void *)
0x18003d86b  mov     qword ptr [rsp+150h+var_128], rax
0x18003d870  lea     rax, ?WerpcbSeekByteStream@@YAJPEAXT_LARGE_INTEGER@@PEAT1@K0@Z; WerpcbSeekByteStream(void *,_LARGE_INTEGER,_LARGE_INTEGER *,ulong,void *)
0x18003d877  mov     [rsp+150h+var_130], rax
0x18003d87c  xor     r8d, r8d
0x18003d87f  lea     rdx, [rbp+50h+var_A0]
0x18003d883  mov     rcx, [rbx+40h]
0x18003d887  mov     rax, [rbx+38h]
0x18003d88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d890  mov     edi, eax
0x18003d892  bts     dword ptr [r12], 1Ch
0x18003d898  test    eax, eax
0x18003d89a  jns     short loc_18003D8DE
0x18003d89c  mov     rcx, [rsp+150h+hFile]; FileHandle
0x18003d8a1  call    ?UtilMarkFileForDelete@@YAXPEAXK@Z; UtilMarkFileForDelete(void *,ulong)
0x18003d8a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d8ad  cmp     rcx, r14
0x18003d8b0  jz      loc_18003DE1F
0x18003d8b6  test    [rcx+1Ch], sil
0x18003d8ba  jz      loc_18003DE1F
0x18003d8c0  mov     edx, 0CCh
0x18003d8c5  mov     dword ptr [rsp+150h+var_130], edi
0x18003d8c9  mov     r9, [rbx+38h]
0x18003d8cd  mov     r8, r15
0x18003d8d0  mov     rcx, [rcx+10h]
0x18003d8d4  call    WPP_SF_qD
0x18003d8d9  jmp     loc_18003DE1F
0x18003d8de  xor     edi, edi
0x18003d8e0  mov     [rbx+38h], rdi
0x18003d8e4  mov     [rbx+40h], rdi
0x18003d8e8  jmp     loc_18003DB7F
0x18003d8ed  mov     rcx, [r13+0]; wchar_t *
0x18003d8f1  cmp     rcx, [r13+8]
0x18003d8f5  jz      loc_18003DDB4
0x18003d8fb  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x18003d900  mov     [rsp+150h+var_F8], rax
0x18003d905  test    rax, rax
0x18003d908  jnz     short loc_18003D931
0x18003d90a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d911  cmp     rcx, r14
0x18003d914  jz      loc_18003D644
0x18003d91a  lea     esi, [rax+1]
0x18003d91d  test    [rcx+1Ch], sil
0x18003d921  jz      loc_18003D644
0x18003d927  mov     edx, 0CDh
0x18003d92c  jmp     loc_18003D638
0x18003d931  mov     r9, rax
0x18003d934  mov     r8, rdi
0x18003d937  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18003d93e  lea     rcx, [rsp+150h+lpNewFileName]
0x18003d943  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18003d948  mov     edi, eax
0x18003d94a  test    eax, eax
0x18003d94c  jns     short loc_18003D977
0x18003d94e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d955  cmp     rcx, r14
0x18003d958  jz      loc_18003DE1F
0x18003d95e  mov     esi, 1
0x18003d963  test    [rcx+1Ch], sil
0x18003d967  jz      loc_18003DE1F
0x18003d96d  mov     edx, 0CEh
0x18003d972  jmp     loc_18003D71C
0x18003d977  lea     rcx, [rsp+150h+lpNewFileName]
0x18003d97c  call    ?starts_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::starts_with(wchar_t const *)
0x18003d981  test    al, al
0x18003d983  jnz     short loc_18003D9CD
0x18003d985  mov     r9d, 4
0x18003d98b  lea     rcx, [rsp+150h+lpNewFileName]
  ... truncated ...
```
