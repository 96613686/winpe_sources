# CDataCollection::AddEtwLogs(void)

- ea: `0x18008b42c`
- end: `0x18008bef9`
- name: `?AddEtwLogs@CDataCollection@@QEAAJXZ`
- size: `2765`
- prototype: `__int64 __fastcall(CReport **this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008fec`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x180008568`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000c390`
- `0x18000cc74`
- `0x18000dad0`
- `0x180013730`
- `0x1800157c4`
- `0x18001abd8`
- `0x18001b678`
- `0x18001bbc4`
- `0x18001da80`
- `0x18001dc24`
- `0x18001fe24`
- `0x18002ffc4`
- `0x18003d990`
- `0x180044230`
- `0x180045bdc`
- `0x180046d74`
- `0x1800475e4`
- `0x18004ac98`
- `0x180050db0`
- `0x1800517cc`
- `0x18006498c`
- `0x180065d54`
- `0x1800707bc`
- `0x18008b42c`
- `0x1800aa000`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b8d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008b8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bdcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008b690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bd0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bdcc`
- `ntdll!wcsrchr` at `0x18008baab`
- `ntdll!wcsrchr` at `0x18008baab`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18008be97`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18008be97`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b686`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008b686`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008bb6f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008bb6f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008b8b2`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008b8b2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008b97b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008b97b`

## string_xrefs

- `0x18008be2d`: `onecore\windows\feedback\core\werdll\lib\datacollection.cpp`

## pseudocode

```c
__int64 __fastcall CDataCollection::AddEtwLogs(CReport **this)
{
  __int64 FirstFileW; // r14
  wchar_t *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  int PathOfWERTempDirectory; // eax
  DWORD LastError; // eax
  int v9; // eax
  const wchar_t *v10; // rcx
  int v11; // eax
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  int TempFile; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  wchar_t *v18; // rax
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD v22; // eax
  unsigned int v23; // eax
  DWORD v24; // eax
  int v25; // eax
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  wchar_t *v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpPathName[4]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+90h] [rbp-70h]
  _QWORD v34[2]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v35[5]; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v37; // [rsp+E8h] [rbp-18h]
  __int128 v38; // [rsp+F8h] [rbp-8h]
  __int64 v39; // [rsp+108h] [rbp+8h]
  __int128 v40; // [rsp+110h] [rbp+10h]
  wchar_t *v41[4]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v42[4]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v43[4]; // [rsp+160h] [rbp+60h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+180h] [rbp+80h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp+A0h] BYREF
  _DWORD v46[12]; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t v47[680]; // [rsp+420h] [rbp+320h] BYREF
  __int16 v48; // [rsp+970h] [rbp+870h] BYREF
  _BYTE v49[38]; // [rsp+972h] [rbp+872h] BYREF
  int v50; // [rsp+998h] [rbp+898h]
  int v51; // [rsp+99Ch] [rbp+89Ch]
  int v52; // [rsp+BA8h] [rbp+AA8h]
  WCHAR NewFileName[264]; // [rsp+EF0h] [rbp+DF0h] BYREF
  _BYTE v54[528]; // [rsp+1100h] [rbp+1000h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1368h] [rbp+1268h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpPathName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v43);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v42);
  LOWORD(v46[0]) = 0;
  memset_0((char *)v46 + 2, 0, 0x576u);
  v48 = 0;
  memset_0(v49, 0, 0x576u);
  FirstFileW = -1;
  v33 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  v30 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  SecurityAttributes.nLength = 24;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !*this )
  {
    v4 = -2147024809;
    if ( v3 == (wchar_t *)&WPP_GLOBAL_Control || (v3[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 66;
LABEL_8:
    v6 = v4;
    goto LABEL_135;
  }
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v54, 260);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 67;
LABEL_134:
    v6 = (unsigned int)PathOfWERTempDirectory;
    goto LABEL_135;
  }
  PathOfWERTempDirectory = CReport::GetUniqueIdentifier(*this, v35);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 68;
    goto LABEL_134;
  }
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpPathName,
                             L"%ws\\%ws",
                             v54,
                             v35[0]);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 69;
    goto LABEL_134;
  }
  PathOfWERTempDirectory = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                             (struct CSecurityAttributes *)&SecurityAttributes,
                             0);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 70;
    goto LABEL_134;
  }
  if ( !CreateDirectoryW(lpPathName[0], &SecurityAttributes) )
  {
    LastError = GetLastError();
    PathOfWERTempDirectory = ERROR_HR_FROM_WIN32(LastError);
    v4 = PathOfWERTempDirectory;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 71;
    goto LABEL_134;
  }
  v9 = UtilAddAccessToPath(lpPathName[0], 0x10000000u);
  if ( v9 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)v9);
  v46[0] = 91751760;
  v46[10] = -268369918;
  if ( (int)StringCchCopyW(v47, 0x104u, v35[0]) < 0 )
  {
    v6 = 2147942606LL;
    v4 = -2147024690;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 73;
LABEL_135:
    WPP_SF_d(*((_QWORD *)v3 + 2), v5, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v6);
    goto LABEL_136;
  }
  PathOfWERTempDirectory = UtilSendMessageToWersvc(v10, (struct _WERSVC_MSG *)v46, (struct _WERSVC_MSG *)&v48, 0xEA60u);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 74;
    goto LABEL_134;
  }
  if ( v50 != -268369920 )
  {
    if ( v52 )
    {
      v4 = -2147467259;
      v3 = WPP_GLOBAL_Control;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          v51 | 0x10000000u);
        v3 = WPP_GLOBAL_Control;
      }
      v4 = 1;
    }
    if ( v3 == (wchar_t *)&WPP_GLOBAL_Control || (v3[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 76;
    goto LABEL_8;
  }
  v11 = UtilVerifyAndLockDirectory((wchar_t *)lpPathName[0]);
  v4 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        lpPathName[0],
        v11);
    goto LABEL_136;
  }
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpFileName,
                             L"%s\\*etl",
                             lpPathName[0]);
  v4 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 78;
    goto LABEL_134;
  }
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  v33 = FirstFileW;
  if ( FirstFileW == -1 )
  {
    v24 = GetLastError();
    PathOfWERTempDirectory = ERROR_HR_FROM_WIN32(v24);
    v4 = PathOfWERTempDirectory;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v5 = 79;
    goto LABEL_134;
  }
  while ( 1 )
  {
    v12 = (wchar_t *)HeapAlloc(g_hWerheap, 0, 0x208u);
    v13 = v12;
    if ( v12 )
      memset_0(v12, 0, 0x208u);
    else
      v13 = 0;
    v29 = v13;
    if ( !v13 )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 80;
LABEL_129:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v21);
      goto LABEL_130;
    }
    TempFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 lpExistingFileName,
                 L"%ls\\%ls",
                 lpPathName[0],
                 FindFileData.cFileName);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 81;
      goto LABEL_125;
    }
    TempFile = UtilGetTempFile(0, v54, L".etl", NewFileName);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 82;
      goto LABEL_125;
    }
    if ( !MoveFileExW(lpExistingFileName[0], NewFileName, 1u) )
      break;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             lpExistingFileName,
                             NewFileName) )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 84;
      goto LABEL_129;
    }
    v34[0] = FindFileData.cFileName;
    v15 = -1;
    do
      ++v15;
    while ( FindFileData.cFileName[v15] );
    v34[1] = v15;
    if ( (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                            v34,
                            L"HostTrace_")
      || (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                            v34,
                            L"GuestTrace_") )
    {
      goto LABEL_86;
    }
    v16 = lpExistingFileName[1] - lpExistingFileName[0];
    v17 = v16 - 1;
    if ( !v16 )
    {
LABEL_75:
      v4 = -2147024773;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          lpExistingFileName[0],
          123);
      goto LABEL_130;
    }
    while ( lpExistingFileName[0][v17] != 92 )
    {
      if ( --v17 == -1 )
        goto LABEL_75;
    }
    if ( v16 <= v17 + 1 )
    {
      v4 = -2147418113;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          lpExistingFileName[0]);
      goto LABEL_130;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v41,
                             &lpExistingFileName[0][v17 + 1]) )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 87;
      goto LABEL_129;
    }
    if ( (int)StringCchCopyW(v13, 0x104u, v41[0]) < 0 )
    {
      v21 = 2147942606LL;
      v4 = -2147024690;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 88;
      goto LABEL_129;
    }
    v18 = wcsrchr(FindFileData.cFileName, 0x2Eu);
    if ( !v18 )
    {
      TempFile = -2147024773;
      v4 = -2147024773;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 89;
      goto LABEL_125;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v42,
                             FindFileData.cFileName,
                             v18 - FindFileData.cFileName) )
    {
      v21 = 2147942414LL;
      v4 = -2147024882;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 90;
      goto LABEL_129;
    }
    TempFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 v43,
                 L"%s_inject.etl",
                 v42[0]);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 91;
      goto LABEL_125;
    }
    TempFile = CReport::AddFileCallback(
                 *this,
                 9,
                 0,
                 (int (*)(void *, void *, void *, unsigned int, int (*)(void *, union _LARGE_INTEGER, union _LARGE_INTEGER *, unsigned int, void *), int (*)(void *, const void *, unsigned int, void *), void (*)(void *, unsigned int, const wchar_t *, char *)))CDataCollection::MergeEtlRoutine,
                 v13,
                 v43[0],
                 0);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 92;
      goto LABEL_125;
    }
    v29 = 0;
LABEL_86:
    TempFile = CReport::AddFile(*this, 9, 1, lpExistingFileName[0], FindFileData.cFileName, 0);
    v4 = TempFile;
    if ( TempFile < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v20 = 93;
LABEL_125:
      v21 = (unsigned int)TempFile;
      goto LABEL_129;
    }
    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
      goto LABEL_130;
    utl::unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>::~unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>(&v29);
  }
  v22 = GetLastError();
  v23 = ERROR_HR_FROM_WIN32(v22);
  v4 = v23;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      83,
      (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      lpExistingFileName[0],
      (__int64)NewFileName,
      v23);
LABEL_130:
  utl::unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>::~unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>(&v29);
LABEL_136:
  tlx::unique_any<tlx::file_handle_traits>::reset(&v30, 0);
  v25 = UtilRecursiveRemoveDirectory(lpPathName[0], 0, 0, 0, v27);
  if ( v25 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8C0,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\datacollection.cpp",
      (const char *)(unsigned int)v25,
      v28);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v4);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v41);
  CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityAttributes);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v30);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v43);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpPathName);
  return v4;
}

```

## disassembly

```asm
0x18008b42c  push    rbp
0x18008b42e  push    rbx
0x18008b42f  push    rsi
0x18008b430  push    rdi
0x18008b431  push    r12
0x18008b433  push    r13
0x18008b435  push    r14
0x18008b437  push    r15
0x18008b439  lea     rbp, [rsp-1228h]
0x18008b441  mov     eax, 1328h
0x18008b446  call    _alloca_probe
0x18008b44b  sub     rsp, rax
0x18008b44e  mov     rax, cs:__security_cookie
0x18008b455  xor     rax, rsp
0x18008b458  mov     [rbp+1260h+var_50], rax
0x18008b45f  mov     rsi, rcx
0x18008b462  lea     rcx, [rsp+1360h+lpPathName]; void *
0x18008b467  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b46c  nop
0x18008b46d  lea     rcx, [rbp+1260h+lpFileName]; void *
0x18008b474  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b479  nop
0x18008b47a  lea     rcx, [rsp+1360h+lpExistingFileName]; void *
0x18008b47f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b484  nop
0x18008b485  lea     rcx, [rbp+1260h+var_1200]; void *
0x18008b489  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b48e  nop
0x18008b48f  lea     rcx, [rbp+1260h+var_1220]; void *
0x18008b493  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b498  nop
0x18008b499  xor     r15d, r15d
0x18008b49c  mov     word ptr [rbp+1260h+var_F70], r15w
0x18008b4a4  mov     ebx, 576h
0x18008b4a9  mov     r8d, ebx; Size
0x18008b4ac  xor     edx, edx; Val
0x18008b4ae  lea     rcx, [rbp+1260h+var_F70+2]; void *
0x18008b4b5  call    memset_0
0x18008b4ba  mov     [rbp+1260h+var_9F0], r15w
0x18008b4c2  mov     r8d, ebx; Size
0x18008b4c5  xor     edx, edx; Val
0x18008b4c7  lea     rcx, [rbp+1260h+var_9EE]; void *
0x18008b4ce  call    memset_0
0x18008b4d3  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008b4d7  mov     [rbp+1260h+var_12D0], r14
0x18008b4db  xor     edx, edx; Val
0x18008b4dd  mov     r8d, 250h; Size
0x18008b4e3  lea     rcx, [rbp+1260h+FindFileData]; void *
0x18008b4ea  call    memset_0
0x18008b4ef  lea     rcx, [rbp+1260h+var_12B8]; void *
0x18008b4f3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b4f8  nop
0x18008b4f9  mov     [rsp+1360h+var_1318], r15
0x18008b4fe  xorps   xmm0, xmm0
0x18008b501  xor     eax, eax
0x18008b503  movups  xmmword ptr [rbp+1260h+SecurityAttributes.nLength], xmm0
0x18008b507  mov     qword ptr [rbp+1260h+SecurityAttributes.bInheritHandle], rax
0x18008b50b  xorps   xmm1, xmm1
0x18008b50e  movups  [rbp+1260h+var_1278], xmm1
0x18008b512  movups  [rbp+1260h+var_1268], xmm1
0x18008b516  mov     [rbp+1260h+var_1258], rax
0x18008b51a  movdqa  [rbp+1260h+var_1250], xmm0
0x18008b51f  mov     [rbp+1260h+SecurityAttributes.nLength], 18h
0x18008b526  lea     rcx, [rbp+1260h+var_1240]; void *
0x18008b52a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008b52f  nop
0x18008b530  lea     r12, WPP_GLOBAL_Control
0x18008b537  lea     r13, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008b53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b545  cmp     rcx, r12
0x18008b548  jz      short loc_18008B567
0x18008b54a  test    byte ptr [rcx+1Ch], 4
0x18008b54e  jz      short loc_18008B567
0x18008b550  lea     edx, [r15+41h]
0x18008b554  mov     r8, r13
0x18008b557  mov     rcx, [rcx+10h]
0x18008b55b  call    WPP_SF_
0x18008b560  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b567  cmp     [rsi], r15
0x18008b56a  jnz     short loc_18008B591
0x18008b56c  mov     ebx, 80070057h
0x18008b571  cmp     rcx, r12
0x18008b574  jz      loc_18008BE01
0x18008b57a  test    byte ptr [rcx+1Ch], 1
0x18008b57e  jz      loc_18008BE01
0x18008b584  mov     edx, 42h ; 'B'
0x18008b589  mov     r9d, ebx
0x18008b58c  jmp     loc_18008BDF5
0x18008b591  mov     edx, 104h
0x18008b596  lea     rcx, [rbp+1260h+var_260]
0x18008b59d  call    WerpGetPathOfWERTempDirectory
0x18008b5a2  mov     ebx, eax
0x18008b5a4  test    eax, eax
0x18008b5a6  jns     short loc_18008B5CC
0x18008b5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5af  cmp     rcx, r12
0x18008b5b2  jz      loc_18008BE01
0x18008b5b8  test    byte ptr [rcx+1Ch], 1
0x18008b5bc  jz      loc_18008BE01
0x18008b5c2  mov     edx, 43h ; 'C'
0x18008b5c7  jmp     loc_18008BDF2
0x18008b5cc  lea     rdx, [rbp+1260h+var_12B8]
0x18008b5d0  mov     rcx, [rsi]
0x18008b5d3  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008b5d8  mov     ebx, eax
0x18008b5da  test    eax, eax
0x18008b5dc  jns     short loc_18008B602
0x18008b5de  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b5e5  cmp     rcx, r12
0x18008b5e8  jz      loc_18008BE01
0x18008b5ee  test    byte ptr [rcx+1Ch], 1
0x18008b5f2  jz      loc_18008BE01
0x18008b5f8  mov     edx, 44h ; 'D'
0x18008b5fd  jmp     loc_18008BDF2
0x18008b602  mov     r9, [rbp+1260h+var_12B8]
0x18008b606  lea     r8, [rbp+1260h+var_260]
0x18008b60d  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18008b614  lea     rcx, [rsp+1360h+lpPathName]
0x18008b619  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b61e  mov     ebx, eax
0x18008b620  test    eax, eax
0x18008b622  jns     short loc_18008B648
0x18008b624  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b62b  cmp     rcx, r12
0x18008b62e  jz      loc_18008BE01
0x18008b634  test    byte ptr [rcx+1Ch], 1
0x18008b638  jz      loc_18008BE01
0x18008b63e  mov     edx, 45h ; 'E'
0x18008b643  jmp     loc_18008BDF2
0x18008b648  xor     edx, edx; bool
0x18008b64a  lea     rcx, [rbp+1260h+SecurityAttributes]; this
0x18008b64e  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x18008b653  mov     ebx, eax
0x18008b655  test    eax, eax
0x18008b657  jns     short loc_18008B67D
0x18008b659  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b660  cmp     rcx, r12
0x18008b663  jz      loc_18008BE01
0x18008b669  test    byte ptr [rcx+1Ch], 1
0x18008b66d  jz      loc_18008BE01
0x18008b673  mov     edx, 46h ; 'F'
0x18008b678  jmp     loc_18008BDF2
0x18008b67d  lea     rdx, [rbp+1260h+SecurityAttributes]; lpSecurityAttributes
0x18008b681  mov     rcx, [rsp+1360h+lpPathName]; lpPathName
0x18008b686  call    cs:__imp_CreateDirectoryW
0x18008b68c  test    eax, eax
0x18008b68e  jnz     short loc_18008B6C3
0x18008b690  call    cs:__imp_GetLastError
0x18008b696  mov     ecx, eax; unsigned int
0x18008b698  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008b69d  mov     ebx, eax
0x18008b69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6a6  cmp     rcx, r12
0x18008b6a9  jz      loc_18008BE01
0x18008b6af  test    byte ptr [rcx+1Ch], 1
0x18008b6b3  jz      loc_18008BE01
0x18008b6b9  mov     edx, 47h ; 'G'
0x18008b6be  jmp     loc_18008BDF2
0x18008b6c3  mov     edi, 10000000h
0x18008b6c8  mov     edx, edi; unsigned int
0x18008b6ca  mov     rcx, [rsp+1360h+lpPathName]; wchar_t *
0x18008b6cf  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x18008b6d4  test    eax, eax
0x18008b6d6  jns     short loc_18008B6FE
0x18008b6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b6df  cmp     rcx, r12
0x18008b6e2  jz      short loc_18008B6FE
0x18008b6e4  test    byte ptr [rcx+1Ch], 2
0x18008b6e8  jz      short loc_18008B6FE
0x18008b6ea  mov     edx, 48h ; 'H'
0x18008b6ef  mov     r9d, eax
0x18008b6f2  mov     r8, r13
0x18008b6f5  mov     rcx, [rcx+10h]
0x18008b6f9  call    WPP_SF_d
0x18008b6fe  mov     [rbp+1260h+var_F70], 5780550h
0x18008b708  mov     [rbp+1260h+var_F48], 0F0010002h
0x18008b712  mov     r8, [rbp+1260h+var_12B8]; wchar_t *
0x18008b716  mov     edx, 104h; unsigned __int64
0x18008b71b  lea     rcx, [rbp+1260h+var_F40]; wchar_t *
0x18008b722  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18008b727  test    eax, eax
0x18008b729  jns     short loc_18008B758
0x18008b72b  mov     r9d, 800700CEh
0x18008b731  mov     ebx, r9d
0x18008b734  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b73b  cmp     rcx, r12
0x18008b73e  jz      loc_18008BE01
0x18008b744  test    byte ptr [rcx+1Ch], 1
0x18008b748  jz      loc_18008BE01
0x18008b74e  mov     edx, 49h ; 'I'
0x18008b753  jmp     loc_18008BDF5
0x18008b758  mov     r9d, 0EA60h; unsigned int
0x18008b75e  lea     r8, [rbp+1260h+var_9F0]; struct _WERSVC_MSG *
0x18008b765  lea     rdx, [rbp+1260h+var_F70]; struct _WERSVC_MSG *
0x18008b76c  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18008b771  mov     ebx, eax
0x18008b773  test    eax, eax
0x18008b775  jns     short loc_18008B79B
0x18008b777  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b77e  cmp     rcx, r12
0x18008b781  jz      loc_18008BE01
0x18008b787  test    byte ptr [rcx+1Ch], 1
0x18008b78b  jz      loc_18008BE01
0x18008b791  mov     edx, 4Ah ; 'J'
0x18008b796  jmp     loc_18008BDF2
0x18008b79b  cmp     [rbp+1260h+var_9C8], 0F0010000h
0x18008b7a5  jz      short loc_18008B814
0x18008b7a7  cmp     [rbp+1260h+var_7B8], r15d
0x18008b7ae  jnz     short loc_18008B7EB
0x18008b7b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7b7  cmp     rcx, r12
0x18008b7ba  jz      short loc_18008B7E4
0x18008b7bc  test    byte ptr [rcx+1Ch], 2
0x18008b7c0  jz      short loc_18008B7E4
0x18008b7c2  mov     r9d, [rbp+1260h+var_9C4]
0x18008b7c9  or      r9d, edi
0x18008b7cc  mov     edx, 4Bh ; 'K'
0x18008b7d1  mov     r8, r13
0x18008b7d4  mov     rcx, [rcx+10h]
0x18008b7d8  call    WPP_SF_d
0x18008b7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7e4  mov     ebx, 1
0x18008b7e9  jmp     short loc_18008B7F7
0x18008b7eb  mov     ebx, 80004005h
0x18008b7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b7f7  cmp     rcx, r12
0x18008b7fa  jz      loc_18008BE01
0x18008b800  test    byte ptr [rcx+1Ch], 1
0x18008b804  jz      loc_18008BE01
0x18008b80a  mov     edx, 4Ch ; 'L'
0x18008b80f  jmp     loc_18008B589
0x18008b814  lea     rdx, [rsp+1360h+var_1318]
0x18008b819  mov     rcx, [rsp+1360h+lpPathName]; wchar_t *
0x18008b81e  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x18008b823  mov     ebx, eax
0x18008b825  test    eax, eax
0x18008b827  jns     short loc_18008B862
0x18008b829  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b830  cmp     rcx, r12
0x18008b833  jz      loc_18008BE01
0x18008b839  test    byte ptr [rcx+1Ch], 1
0x18008b83d  jz      loc_18008BE01
0x18008b843  mov     edx, 4Dh ; 'M'
0x18008b848  mov     dword ptr [rsp+1360h+var_1340], eax
0x18008b84c  mov     r9, [rsp+1360h+lpPathName]
0x18008b851  mov     r8, r13
0x18008b854  mov     rcx, [rcx+10h]
0x18008b858  call    WPP_SF_Sd
0x18008b85d  jmp     loc_18008BE01
0x18008b862  mov     r8, [rsp+1360h+lpPathName]
0x18008b867  lea     rdx, aSEtl; "%s\\*etl"
0x18008b86e  lea     rcx, [rbp+1260h+lpFileName]
0x18008b875  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b87a  mov     ebx, eax
0x18008b87c  test    eax, eax
0x18008b87e  jns     short loc_18008B8A4
0x18008b880  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b887  cmp     rcx, r12
0x18008b88a  jz      loc_18008BE01
0x18008b890  test    byte ptr [rcx+1Ch], 1
0x18008b894  jz      loc_18008BE01
0x18008b89a  mov     edx, 4Eh ; 'N'
0x18008b89f  jmp     loc_18008BDF2
0x18008b8a4  lea     rdx, [rbp+1260h+FindFileData]; lpFindFileData
0x18008b8ab  mov     rcx, [rbp+1260h+lpFileName]; lpFileName
0x18008b8b2  call    cs:__imp_FindFirstFileW
0x18008b8b8  mov     r14, rax
0x18008b8bb  mov     [rbp+1260h+var_12D0], rax
0x18008b8bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008b8c3  jz      loc_18008BDCC
0x18008b8c9  xor     edx, edx; dwFlags
0x18008b8cb  mov     r8d, 208h; dwBytes
0x18008b8d1  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18008b8d8  call    cs:__imp_HeapAlloc
0x18008b8de  mov     rdi, rax
0x18008b8e1  test    rax, rax
0x18008b8e4  jz      short loc_18008B8F8
0x18008b8e6  xor     edx, edx; Val
0x18008b8e8  mov     r8d, 208h; Size
0x18008b8ee  mov     rcx, rax; void *
0x18008b8f1  call    memset_0
0x18008b8f6  jmp     short loc_18008B8FB
0x18008b8f8  mov     rdi, r15
0x18008b8fb  mov     [rsp+1360h+var_1320], rdi
0x18008b900  test    rdi, rdi
0x18008b903  jz      loc_18008BD93
0x18008b909  lea     r9, [rbp+1260h+FindFileData.cFileName]
0x18008b910  mov     r8, [rsp+1360h+lpPathName]
0x18008b915  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18008b91c  lea     rcx, [rsp+1360h+lpExistingFileName]
0x18008b921  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008b926  mov     ebx, eax
0x18008b928  test    eax, eax
0x18008b92a  js      loc_18008BD77
0x18008b930  mov     [rsp+1360h+var_1328], r15d
0x18008b935  mov     dword ptr [rsp+1360h+var_1330], r15d
0x18008b93a  lea     rax, [rbp+1260h+SecurityAttributes]
0x18008b93e  mov     [rsp+1360h+var_1338], rax
0x18008b943  lea     r9, [rbp+1260h+NewFileName]
0x18008b94a  lea     r8, aEtl; ".etl"
  ... truncated ...
```
