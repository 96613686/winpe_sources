# CDataCollection::AddEtwLogs(void)

- ea: `0x18008f2ec`
- end: `0x18008fe02`
- name: `?AddEtwLogs@CDataCollection@@QEAAJXZ`
- size: `2838`
- prototype: `__int64 __fastcall(CDataCollection *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a0f8`

## callees

- `0x180004c64`
- `0x1800062bc`
- `0x180007fd8`
- `0x180008004`
- `0x180008298`
- `0x180008698`
- `0x180009684`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x1800170b0`
- `0x180019138`
- `0x18001c368`
- `0x18001e0a8`
- `0x18001e288`
- `0x180020680`
- `0x180028648`
- `0x18002a52c`
- `0x1800318c8`
- `0x18003f9a0`
- `0x180046150`
- `0x1800479ac`
- `0x180048b34`
- `0x1800497cc`
- `0x18004cc0c`
- `0x180053300`
- `0x180053d3c`
- `0x1800678d4`
- `0x180068e08`
- `0x180073b38`
- `0x18008f2ec`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008f7b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008f7b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fc06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fc06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fccb`
- `ntdll!wcsrchr` at `0x18008f996`
- `ntdll!wcsrchr` at `0x18008f996`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008f54c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008f54c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008fa62`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18008fa62`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008f784`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18008f784`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008f861`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18008f861`

## string_xrefs

- `0x18008fd32`: `onecore\windows\feedback\core\werdll\lib\datacollection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CDataCollection::AddEtwLogs(CReport **this)
{
  wchar_t *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r9
  int PathOfWERTempDirectory; // eax
  DWORD LastError; // eax
  int v8; // eax
  const wchar_t *v9; // rcx
  int v10; // eax
  HANDLE FirstFileW; // rax
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  int TempFile; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  wchar_t *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  DWORD v21; // eax
  unsigned int v22; // eax
  DWORD v23; // eax
  int v24; // eax
  wchar_t *v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  wchar_t *v28; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFindFile; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpPathName[4]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v33[2]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v34[5]; // [rsp+A8h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v36; // [rsp+E8h] [rbp-18h]
  __int128 v37; // [rsp+F8h] [rbp-8h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  __int128 v39; // [rsp+110h] [rbp+10h]
  wchar_t *v40[4]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t *v41[4]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v42[4]; // [rsp+160h] [rbp+60h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+180h] [rbp+80h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp+A0h] BYREF
  _DWORD v45[12]; // [rsp+3F0h] [rbp+2F0h] BYREF
  wchar_t v46[680]; // [rsp+420h] [rbp+320h] BYREF
  __int16 v47; // [rsp+970h] [rbp+870h] BYREF
  _BYTE v48[38]; // [rsp+972h] [rbp+872h] BYREF
  int v49; // [rsp+998h] [rbp+898h]
  int v50; // [rsp+99Ch] [rbp+89Ch]
  int v51; // [rsp+BA8h] [rbp+AA8h]
  WCHAR NewFileName[264]; // [rsp+EF0h] [rbp+DF0h] BYREF
  WCHAR v53[264]; // [rsp+1100h] [rbp+1000h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1348h] [rbp+1248h]

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpPathName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpExistingFileName);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v42);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
  LOWORD(v45[0]) = 0;
  memset_0((char *)v45 + 2, 0, 0x576u);
  v47 = 0;
  memset_0(v48, 0, 0x576u);
  hFindFile = (HANDLE)-1LL;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
  v30 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  SecurityAttributes.nLength = 24;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !*this )
  {
    v3 = -2147024809;
    if ( v2 == (wchar_t *)&WPP_GLOBAL_Control || (v2[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 66;
LABEL_8:
    v5 = v3;
    goto LABEL_135;
  }
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v53, 260);
  v3 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 67;
LABEL_134:
    v5 = (unsigned int)PathOfWERTempDirectory;
    goto LABEL_135;
  }
  PathOfWERTempDirectory = CReport::GetUniqueIdentifier(*this, v34);
  v3 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 68;
    goto LABEL_134;
  }
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpPathName,
                             L"%ws\\%ws",
                             v53,
                             v34[0]);
  v3 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 69;
    goto LABEL_134;
  }
  PathOfWERTempDirectory = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                             (struct CSecurityAttributes *)&SecurityAttributes,
                             0);
  v3 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 70;
    goto LABEL_134;
  }
  if ( !CreateDirectoryW(lpPathName[0], &SecurityAttributes) )
  {
    LastError = GetLastError();
    PathOfWERTempDirectory = ERROR_HR_FROM_WIN32(LastError);
    v3 = PathOfWERTempDirectory;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 71;
    goto LABEL_134;
  }
  v8 = UtilAddAccessToPath(lpPathName[0], 0x10000000u);
  if ( v8 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, (unsigned int)v8);
  v45[0] = 91751760;
  v45[10] = -268369918;
  if ( (int)StringCchCopyW(v46, 0x104u, v34[0]) < 0 )
  {
    v5 = 2147942606LL;
    v3 = -2147024690;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 73;
LABEL_135:
    WPP_SF_d(*((_QWORD *)v2 + 2), v4, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v5);
    goto LABEL_136;
  }
  PathOfWERTempDirectory = UtilSendMessageToWersvc(v9, (struct _WERSVC_MSG *)v45, (struct _WERSVC_MSG *)&v47, 0xEA60u);
  v3 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 74;
    goto LABEL_134;
  }
  if ( v49 != -268369920 )
  {
    if ( v51 )
    {
      v3 = -2147467259;
      v2 = WPP_GLOBAL_Control;
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          v50 | 0x10000000u);
        v2 = WPP_GLOBAL_Control;
      }
      v3 = 1;
    }
    if ( v2 == (wchar_t *)&WPP_GLOBAL_Control || (v2[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 76;
    goto LABEL_8;
  }
  v10 = UtilVerifyAndLockDirectory((wchar_t *)lpPathName[0], (__int64)&v30);
  v3 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        lpPathName[0],
        v10);
    goto LABEL_136;
  }
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpFileName,
                             L"%s\\*etl",
                             lpPathName[0]);
  v3 = PathOfWERTempDirectory;
  if ( PathOfWERTempDirectory < 0 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 78;
    goto LABEL_134;
  }
  FirstFileW = FindFirstFileW(lpFileName[0], &FindFileData);
  tlx::unique_any<tlx::find_handle_traits>::reset(&hFindFile, FirstFileW);
  if ( hFindFile == (HANDLE)-1LL )
  {
    v23 = GetLastError();
    PathOfWERTempDirectory = ERROR_HR_FROM_WIN32(v23);
    v3 = PathOfWERTempDirectory;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_136;
    v4 = 79;
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
    v28 = v13;
    if ( !v13 )
    {
      v20 = 2147942414LL;
      v3 = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 80;
LABEL_129:
      WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v20);
      goto LABEL_130;
    }
    TempFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 lpExistingFileName,
                 L"%ls\\%ls",
                 lpPathName[0],
                 FindFileData.cFileName);
    v3 = TempFile;
    if ( TempFile < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 81;
      goto LABEL_125;
    }
    TempFile = UtilGetTempFile(0, v53, (const size_t *)L".etl", NewFileName, (__int64)v26, &SecurityAttributes, 0, 0);
    v3 = TempFile;
    if ( TempFile < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 82;
      goto LABEL_125;
    }
    if ( !MoveFileExW(lpExistingFileName[0], NewFileName, 1u) )
      break;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             lpExistingFileName,
                             NewFileName) )
    {
      v20 = 2147942414LL;
      v3 = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 84;
      goto LABEL_129;
    }
    v33[0] = FindFileData.cFileName;
    v15 = -1;
    do
      ++v15;
    while ( FindFileData.cFileName[v15] );
    v33[1] = v15;
    if ( (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                            v33,
                            L"HostTrace_")
      || (unsigned __int8)utl::basic_string_view<wchar_t,tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::starts_with(
                            v33,
                            L"GuestTrace_") )
    {
      goto LABEL_86;
    }
    v16 = lpExistingFileName[1] - lpExistingFileName[0];
    v17 = v16 - 1;
    if ( !v16 )
    {
LABEL_75:
      v3 = -2147024773;
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
      v3 = -2147418113;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
          lpExistingFileName[0]);
      goto LABEL_130;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v40,
                             (void *)&lpExistingFileName[0][v17 + 1]) )
    {
      v20 = 2147942414LL;
      v3 = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 87;
      goto LABEL_129;
    }
    if ( (int)StringCchCopyW(v13, 0x104u, v40[0]) < 0 )
    {
      v20 = 2147942606LL;
      v3 = -2147024690;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 88;
      goto LABEL_129;
    }
    if ( !wcsrchr(FindFileData.cFileName, 0x2Eu) )
    {
      TempFile = -2147024773;
      v3 = -2147024773;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 89;
      goto LABEL_125;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v41,
                             FindFileData.cFileName) )
    {
      v20 = 2147942414LL;
      v3 = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 90;
      goto LABEL_129;
    }
    TempFile = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                 v42,
                 L"%s_inject.etl",
                 v41[0]);
    v3 = TempFile;
    if ( TempFile < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 91;
      goto LABEL_125;
    }
    TempFile = CReport::AddFileCallback(
                 *this,
                 WerFileTypeEtlTrace,
                 0,
                 (int (*)(void *, void *, void *, unsigned int, int (*)(void *, union _LARGE_INTEGER, union _LARGE_INTEGER *, unsigned int, void *), int (*)(void *, const void *, unsigned int, void *), void (*)(void *, unsigned int, const wchar_t *, char *)))CDataCollection::MergeEtlRoutine,
                 v13,
                 v42[0],
                 0);
    v3 = TempFile;
    if ( TempFile < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 92;
      goto LABEL_125;
    }
    v28 = 0;
LABEL_86:
    TempFile = CReport::AddFile(*this, WerFileTypeEtlTrace, 1u, lpExistingFileName[0], FindFileData.cFileName, 0);
    v3 = TempFile;
    if ( TempFile < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_130;
      v19 = 93;
LABEL_125:
      v20 = (unsigned int)TempFile;
      goto LABEL_129;
    }
    if ( !FindNextFileW(hFindFile, &FindFileData) )
      goto LABEL_130;
    utl::unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>::~unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>(&v28);
  }
  v21 = GetLastError();
  v22 = ERROR_HR_FROM_WIN32(v21);
  v3 = v22;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      83,
      (unsigned int)WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
      lpExistingFileName[0],
      (__int64)NewFileName,
      v22);
LABEL_130:
  utl::unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>::~unique_ptr<_MERGE_ETL_CONTEXT,utl::default_delete<_MERGE_ETL_CONTEXT>>(&v28);
LABEL_136:
  tlx::unique_any<tlx::file_handle_traits>::reset(&v30, 0);
  v24 = UtilRecursiveRemoveDirectory(lpPathName[0], 0, 0, 0, (int)v26);
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8C0,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\datacollection.cpp",
      (const char *)(unsigned int)v24,
      v27);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v3);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v40);
  CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityAttributes);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v30);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
  tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(&hFindFile);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v41);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpPathName);
  return v3;
}

```

## disassembly

```asm
0x18008f2ec  mov     [rsp-8+arg_8], rbx
0x18008f2f1  mov     [rsp-8+arg_10], rsi
0x18008f2f6  push    rbp
0x18008f2f7  push    rdi
0x18008f2f8  push    r12
0x18008f2fa  push    r14
0x18008f2fc  push    r15
0x18008f2fe  lea     rbp, [rsp-1220h]
0x18008f306  mov     eax, 1320h
0x18008f30b  call    _alloca_probe
0x18008f310  sub     rsp, rax
0x18008f313  mov     rax, cs:__security_cookie
0x18008f31a  xor     rax, rsp
0x18008f31d  mov     [rbp+1240h+var_30], rax
0x18008f324  mov     rsi, rcx
0x18008f327  lea     rcx, [rsp+1340h+lpPathName]; void *
0x18008f32c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f331  nop
0x18008f332  lea     rcx, [rbp+1240h+lpFileName]; void *
0x18008f339  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f33e  nop
0x18008f33f  lea     rcx, [rsp+1340h+lpExistingFileName]; void *
0x18008f344  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f349  nop
0x18008f34a  lea     rcx, [rbp+1240h+var_11E0]; void *
0x18008f34e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f353  nop
0x18008f354  lea     rcx, [rbp+1240h+var_1200]; void *
0x18008f358  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f35d  nop
0x18008f35e  xor     r15d, r15d
0x18008f361  mov     word ptr [rbp+1240h+var_F50], r15w
0x18008f369  mov     ebx, 576h
0x18008f36e  mov     r8d, ebx; Size
0x18008f371  xor     edx, edx; Val
0x18008f373  lea     rcx, [rbp+1240h+var_F50+2]; void *
0x18008f37a  call    memset_0
0x18008f37f  mov     [rbp+1240h+var_9D0], r15w
0x18008f387  mov     r8d, ebx; Size
0x18008f38a  xor     edx, edx; Val
0x18008f38c  lea     rcx, [rbp+1240h+var_9CE]; void *
0x18008f393  call    memset_0
0x18008f398  mov     [rsp+1340h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18008f3a1  xor     edx, edx; Val
0x18008f3a3  mov     r8d, 250h; Size
0x18008f3a9  lea     rcx, [rbp+1240h+FindFileData]; void *
0x18008f3b0  call    memset_0
0x18008f3b5  lea     rcx, [rbp+1240h+var_1298]; void *
0x18008f3b9  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f3be  nop
0x18008f3bf  mov     [rsp+1340h+var_12F0], r15
0x18008f3c4  xorps   xmm0, xmm0
0x18008f3c7  xor     eax, eax
0x18008f3c9  movups  xmmword ptr [rbp+1240h+SecurityAttributes.nLength], xmm0
0x18008f3cd  mov     qword ptr [rbp+1240h+SecurityAttributes.bInheritHandle], rax
0x18008f3d1  xorps   xmm1, xmm1
0x18008f3d4  movups  [rbp+1240h+var_1258], xmm1
0x18008f3d8  movups  [rbp+1240h+var_1248], xmm1
0x18008f3dc  mov     [rbp+1240h+var_1238], rax
0x18008f3e0  movdqa  [rbp+1240h+var_1230], xmm0
0x18008f3e5  mov     [rbp+1240h+SecurityAttributes.nLength], 18h
0x18008f3ec  lea     rcx, [rbp+1240h+var_1220]; void *
0x18008f3f0  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008f3f5  nop
0x18008f3f6  lea     r14, WPP_GLOBAL_Control
0x18008f3fd  lea     r12, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008f404  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f40b  cmp     rcx, r14
0x18008f40e  jz      short loc_18008F42D
0x18008f410  test    byte ptr [rcx+1Ch], 4
0x18008f414  jz      short loc_18008F42D
0x18008f416  lea     edx, [r15+41h]
0x18008f41a  mov     r8, r12
0x18008f41d  mov     rcx, [rcx+10h]
0x18008f421  call    WPP_SF_
0x18008f426  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f42d  cmp     [rsi], r15
0x18008f430  jnz     short loc_18008F457
0x18008f432  mov     ebx, 80070057h
0x18008f437  cmp     rcx, r14
0x18008f43a  jz      loc_18008FD06
0x18008f440  test    byte ptr [rcx+1Ch], 1
0x18008f444  jz      loc_18008FD06
0x18008f44a  mov     edx, 42h ; 'B'
0x18008f44f  mov     r9d, ebx
0x18008f452  jmp     loc_18008FCFA
0x18008f457  mov     edx, 104h
0x18008f45c  lea     rcx, [rbp+1240h+var_240]
0x18008f463  call    WerpGetPathOfWERTempDirectory
0x18008f468  mov     ebx, eax
0x18008f46a  test    eax, eax
0x18008f46c  jns     short loc_18008F492
0x18008f46e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f475  cmp     rcx, r14
0x18008f478  jz      loc_18008FD06
0x18008f47e  test    byte ptr [rcx+1Ch], 1
0x18008f482  jz      loc_18008FD06
0x18008f488  mov     edx, 43h ; 'C'
0x18008f48d  jmp     loc_18008FCF7
0x18008f492  lea     rdx, [rbp+1240h+var_1298]
0x18008f496  mov     rcx, [rsi]
0x18008f499  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18008f49e  mov     ebx, eax
0x18008f4a0  test    eax, eax
0x18008f4a2  jns     short loc_18008F4C8
0x18008f4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f4ab  cmp     rcx, r14
0x18008f4ae  jz      loc_18008FD06
0x18008f4b4  test    byte ptr [rcx+1Ch], 1
0x18008f4b8  jz      loc_18008FD06
0x18008f4be  mov     edx, 44h ; 'D'
0x18008f4c3  jmp     loc_18008FCF7
0x18008f4c8  mov     r9, [rbp+1240h+var_1298]
0x18008f4cc  lea     r8, [rbp+1240h+var_240]
0x18008f4d3  lea     rdx, aWsWs_0; "%ws\\%ws"
0x18008f4da  lea     rcx, [rsp+1340h+lpPathName]
0x18008f4df  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008f4e4  mov     ebx, eax
0x18008f4e6  test    eax, eax
0x18008f4e8  jns     short loc_18008F50E
0x18008f4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f4f1  cmp     rcx, r14
0x18008f4f4  jz      loc_18008FD06
0x18008f4fa  test    byte ptr [rcx+1Ch], 1
0x18008f4fe  jz      loc_18008FD06
0x18008f504  mov     edx, 45h ; 'E'
0x18008f509  jmp     loc_18008FCF7
0x18008f50e  xor     edx, edx; bool
0x18008f510  lea     rcx, [rbp+1240h+SecurityAttributes]; this
0x18008f514  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x18008f519  mov     ebx, eax
0x18008f51b  test    eax, eax
0x18008f51d  jns     short loc_18008F543
0x18008f51f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f526  cmp     rcx, r14
0x18008f529  jz      loc_18008FD06
0x18008f52f  test    byte ptr [rcx+1Ch], 1
0x18008f533  jz      loc_18008FD06
0x18008f539  mov     edx, 46h ; 'F'
0x18008f53e  jmp     loc_18008FCF7
0x18008f543  lea     rdx, [rbp+1240h+SecurityAttributes]; lpSecurityAttributes
0x18008f547  mov     rcx, [rsp+1340h+lpPathName]; lpPathName
0x18008f54c  call    cs:__imp_CreateDirectoryW
0x18008f553  nop     dword ptr [rax+rax+00h]
0x18008f558  test    eax, eax
0x18008f55a  jnz     short loc_18008F595
0x18008f55c  call    cs:__imp_GetLastError
0x18008f563  nop     dword ptr [rax+rax+00h]
0x18008f568  mov     ecx, eax; unsigned int
0x18008f56a  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008f56f  mov     ebx, eax
0x18008f571  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f578  cmp     rcx, r14
0x18008f57b  jz      loc_18008FD06
0x18008f581  test    byte ptr [rcx+1Ch], 1
0x18008f585  jz      loc_18008FD06
0x18008f58b  mov     edx, 47h ; 'G'
0x18008f590  jmp     loc_18008FCF7
0x18008f595  mov     edi, 10000000h
0x18008f59a  mov     edx, edi; unsigned int
0x18008f59c  mov     rcx, [rsp+1340h+lpPathName]; wchar_t *
0x18008f5a1  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x18008f5a6  test    eax, eax
0x18008f5a8  jns     short loc_18008F5D0
0x18008f5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f5b1  cmp     rcx, r14
0x18008f5b4  jz      short loc_18008F5D0
0x18008f5b6  test    byte ptr [rcx+1Ch], 2
0x18008f5ba  jz      short loc_18008F5D0
0x18008f5bc  mov     edx, 48h ; 'H'
0x18008f5c1  mov     r9d, eax
0x18008f5c4  mov     r8, r12
0x18008f5c7  mov     rcx, [rcx+10h]
0x18008f5cb  call    WPP_SF_d
0x18008f5d0  mov     [rbp+1240h+var_F50], 5780550h
0x18008f5da  mov     [rbp+1240h+var_F28], 0F0010002h
0x18008f5e4  mov     r8, [rbp+1240h+var_1298]; wchar_t *
0x18008f5e8  mov     edx, 104h; unsigned __int64
0x18008f5ed  lea     rcx, [rbp+1240h+var_F20]; wchar_t *
0x18008f5f4  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18008f5f9  test    eax, eax
0x18008f5fb  jns     short loc_18008F62A
0x18008f5fd  mov     r9d, 800700CEh
0x18008f603  mov     ebx, r9d
0x18008f606  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f60d  cmp     rcx, r14
0x18008f610  jz      loc_18008FD06
0x18008f616  test    byte ptr [rcx+1Ch], 1
0x18008f61a  jz      loc_18008FD06
0x18008f620  mov     edx, 49h ; 'I'
0x18008f625  jmp     loc_18008FCFA
0x18008f62a  mov     r9d, 0EA60h; unsigned int
0x18008f630  lea     r8, [rbp+1240h+var_9D0]; struct _WERSVC_MSG *
0x18008f637  lea     rdx, [rbp+1240h+var_F50]; struct _WERSVC_MSG *
0x18008f63e  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x18008f643  mov     ebx, eax
0x18008f645  test    eax, eax
0x18008f647  jns     short loc_18008F66D
0x18008f649  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f650  cmp     rcx, r14
0x18008f653  jz      loc_18008FD06
0x18008f659  test    byte ptr [rcx+1Ch], 1
0x18008f65d  jz      loc_18008FD06
0x18008f663  mov     edx, 4Ah ; 'J'
0x18008f668  jmp     loc_18008FCF7
0x18008f66d  cmp     [rbp+1240h+var_9A8], 0F0010000h
0x18008f677  jz      short loc_18008F6E6
0x18008f679  cmp     [rbp+1240h+var_798], r15d
0x18008f680  jnz     short loc_18008F6BD
0x18008f682  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f689  cmp     rcx, r14
0x18008f68c  jz      short loc_18008F6B6
0x18008f68e  test    byte ptr [rcx+1Ch], 2
0x18008f692  jz      short loc_18008F6B6
0x18008f694  mov     r9d, [rbp+1240h+var_9A4]
0x18008f69b  or      r9d, edi
0x18008f69e  mov     edx, 4Bh ; 'K'
0x18008f6a3  mov     r8, r12
0x18008f6a6  mov     rcx, [rcx+10h]
0x18008f6aa  call    WPP_SF_d
0x18008f6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f6b6  mov     ebx, 1
0x18008f6bb  jmp     short loc_18008F6C9
0x18008f6bd  mov     ebx, 80004005h
0x18008f6c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f6c9  cmp     rcx, r14
0x18008f6cc  jz      loc_18008FD06
0x18008f6d2  test    byte ptr [rcx+1Ch], 1
0x18008f6d6  jz      loc_18008FD06
0x18008f6dc  mov     edx, 4Ch ; 'L'
0x18008f6e1  jmp     loc_18008F44F
0x18008f6e6  lea     rdx, [rsp+1340h+var_12F0]
0x18008f6eb  mov     rcx, [rsp+1340h+lpPathName]; wchar_t *
0x18008f6f0  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x18008f6f5  mov     ebx, eax
0x18008f6f7  test    eax, eax
0x18008f6f9  jns     short loc_18008F734
0x18008f6fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f702  cmp     rcx, r14
0x18008f705  jz      loc_18008FD06
0x18008f70b  test    byte ptr [rcx+1Ch], 1
0x18008f70f  jz      loc_18008FD06
0x18008f715  mov     edx, 4Dh ; 'M'
0x18008f71a  mov     dword ptr [rsp+1340h+var_1320], eax
0x18008f71e  mov     r9, [rsp+1340h+lpPathName]
0x18008f723  mov     r8, r12
0x18008f726  mov     rcx, [rcx+10h]
0x18008f72a  call    WPP_SF_Sd
0x18008f72f  jmp     loc_18008FD06
0x18008f734  mov     r8, [rsp+1340h+lpPathName]
0x18008f739  lea     rdx, aSEtl; "%s\\*etl"
0x18008f740  lea     rcx, [rbp+1240h+lpFileName]
0x18008f747  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008f74c  mov     ebx, eax
0x18008f74e  test    eax, eax
0x18008f750  jns     short loc_18008F776
0x18008f752  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f759  cmp     rcx, r14
0x18008f75c  jz      loc_18008FD06
0x18008f762  test    byte ptr [rcx+1Ch], 1
0x18008f766  jz      loc_18008FD06
0x18008f76c  mov     edx, 4Eh ; 'N'
0x18008f771  jmp     loc_18008FCF7
0x18008f776  lea     rdx, [rbp+1240h+FindFileData]; lpFindFileData
0x18008f77d  mov     rcx, [rbp+1240h+lpFileName]; lpFileName
0x18008f784  call    cs:__imp_FindFirstFileW
0x18008f78b  nop     dword ptr [rax+rax+00h]
0x18008f790  mov     rdx, rax
0x18008f793  lea     rcx, [rsp+1340h+hFindFile]
0x18008f798  call    ?reset@?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::find_handle_traits>::reset(void *)
0x18008f79d  cmp     [rsp+1340h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18008f7a3  jz      loc_18008FCCB
0x18008f7a9  xor     edx, edx; dwFlags
0x18008f7ab  mov     r8d, 208h; dwBytes
0x18008f7b1  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18008f7b8  call    cs:__imp_HeapAlloc
0x18008f7bf  nop     dword ptr [rax+rax+00h]
0x18008f7c4  mov     rdi, rax
0x18008f7c7  test    rax, rax
0x18008f7ca  jz      short loc_18008F7DE
0x18008f7cc  xor     edx, edx; Val
0x18008f7ce  mov     r8d, 208h; Size
0x18008f7d4  mov     rcx, rax; void *
0x18008f7d7  call    memset_0
0x18008f7dc  jmp     short loc_18008F7E1
0x18008f7de  mov     rdi, r15
0x18008f7e1  mov     [rsp+1340h+var_1300], rdi
0x18008f7e6  test    rdi, rdi
0x18008f7e9  jz      loc_18008FC92
0x18008f7ef  lea     r9, [rbp+1240h+FindFileData.cFileName]
0x18008f7f6  mov     r8, [rsp+1340h+lpPathName]
0x18008f7fb  lea     rdx, aLsLs_1; "%ls\\%ls"
0x18008f802  lea     rcx, [rsp+1340h+lpExistingFileName]
0x18008f807  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18008f80c  mov     ebx, eax
0x18008f80e  test    eax, eax
0x18008f810  js      loc_18008FC76
0x18008f816  mov     [rsp+1340h+var_1308], r15d
0x18008f81b  mov     dword ptr [rsp+1340h+var_1310], r15d
0x18008f820  lea     rax, [rbp+1240h+SecurityAttributes]
  ... truncated ...
```
