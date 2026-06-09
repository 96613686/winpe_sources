# ArchiveExtractWizard::ExtractProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180028d64`
- end: `0x180029269`
- name: `?ExtractProc@ArchiveExtractWizard@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1285`
- prototype: `__int64 __fastcall(ArchiveExtractWizard *this, HWND hDlg, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180028d20`

## callees

- `0x1800207f8`
- `0x180020cbc`
- `0x180028d64`
- `0x180031258`
- `0x180036f50`
- `0x180048dac`
- `0x180052e7c`
- `0x180062ca8`
- `0x180064800`
- `0x18006644c`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180028e2d`
- `SHELL32!SHGetFolderPathEx` at `0x180028e2d`
- `SHELL32!ShellExecuteW` at `0x1800291e5`
- `SHELL32!ShellExecuteW` at `0x1800291e5`
- `SHELL32!__imp_PathIsTemporaryW` at `0x180028ddc`
- `SHELL32!__imp_PathIsTemporaryW` at `0x180028ddc`
- `SHLWAPI!PathFileExistsW` at `0x180029133`
- `SHLWAPI!PathFileExistsW` at `0x180029133`
- `SHLWAPI!SHAutoComplete` at `0x180028eb5`
- `SHLWAPI!SHAutoComplete` at `0x180028eb5`
- `SHLWAPI!StrTrimW` at `0x18002909e`
- `SHLWAPI!StrTrimW` at `0x18002909e`
- `SHLWAPI!PathIsRelativeW` at `0x180029116`
- `SHLWAPI!PathIsRelativeW` at `0x180029116`
- `SHLWAPI!PathIsDirectoryW` at `0x18002914b`
- `SHLWAPI!PathIsDirectoryW` at `0x18002914b`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800290f4`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800290f4`
- `SHLWAPI!__imp_SKGetValueW` at `0x180028fa6`
- `SHLWAPI!__imp_SKGetValueW` at `0x180028fa6`
- `SHLWAPI!__imp_SKSetValueW` at `0x1800291b6`
- `SHLWAPI!__imp_SKSetValueW` at `0x1800291b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180028f28`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180028f28`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180028e49`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180028e49`
- `USER32!SetDlgItemTextW` at `0x180028e9a`
- `USER32!SetDlgItemTextW` at `0x180028e9a`
- `USER32!GetParent` at `0x180028f33`
- `USER32!GetParent` at `0x180028f33`
- `USER32!SetWindowLongPtrW` at `0x180028ff3`
- `USER32!SetWindowLongPtrW` at `0x180028ff3`
- `USER32!PostMessageW` at `0x180028f08`
- `USER32!PostMessageW` at `0x180028f08`
- `USER32!SendMessageW` at `0x180028f4c`
- `USER32!SendMessageW` at `0x180028fe0`
- `USER32!SendMessageW` at `0x180029235`
- `USER32!SendMessageW` at `0x180028f4c`
- `USER32!SendMessageW` at `0x180028fe0`
- `USER32!SendMessageW` at `0x180029235`
- `USER32!GetWindowTextLengthW` at `0x180029047`
- `USER32!GetWindowTextLengthW` at `0x180029047`
- `USER32!EnableWindow` at `0x180028f6a`
- `USER32!EnableWindow` at `0x180029011`
- `USER32!EnableWindow` at `0x18002902e`
- `USER32!EnableWindow` at `0x180028f6a`
- `USER32!EnableWindow` at `0x180029011`
- `USER32!EnableWindow` at `0x18002902e`
- `USER32!GetDlgItem` at `0x180028ea7`
- `USER32!GetDlgItem` at `0x180028f5c`
- `USER32!GetDlgItem` at `0x180028fcc`
- `USER32!GetDlgItem` at `0x180029006`
- `USER32!GetDlgItem` at `0x180029023`
- `USER32!GetDlgItem` at `0x18002903b`
- `USER32!GetDlgItem` at `0x180028ea7`
- `USER32!GetDlgItem` at `0x180028f5c`
- `USER32!GetDlgItem` at `0x180028fcc`
- `USER32!GetDlgItem` at `0x180029006`
- `USER32!GetDlgItem` at `0x180029023`
- `USER32!GetDlgItem` at `0x18002903b`
- `USER32!GetWindowTextW` at `0x18002907b`
- `USER32!GetWindowTextW` at `0x18002907b`
- `USER32!IsDlgButtonChecked` at `0x180029182`
- `USER32!IsDlgButtonChecked` at `0x180029182`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ArchiveExtractWizard::ExtractProc(
        ArchiveExtractWizard *this,
        HWND hDlg,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v6; // r8d
  int v7; // r8d
  char *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  const char *v11; // r9
  const WCHAR *v12; // rax
  HWND DlgItem; // rax
  int v14; // ecx
  HWND Parent; // rax
  HWND v17; // rax
  WPARAM v18; // rbx
  int v19; // eax
  HWND v20; // rax
  HWND v21; // rax
  HWND v22; // rax
  HWND v23; // r14
  __int64 WindowTextLengthW; // rbx
  char *v25; // rdi
  WCHAR *v26; // rax
  int WindowTextW; // eax
  WCHAR *v28; // rax
  const char *v29; // r9
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  const WCHAR *v33; // rax
  const WCHAR *v34; // rax
  BOOL v35; // r14d
  const WCHAR *v36; // rax
  int v37; // eax
  const WCHAR *v38; // rax
  WPARAM v39; // r8
  _QWORD v40[2]; // [rsp+30h] [rbp-288h] BYREF
  _BYTE v41[16]; // [rsp+40h] [rbp-278h] BYREF
  PCWSTR pszMore; // [rsp+50h] [rbp-268h]
  HWND hDlga; // [rsp+60h] [rbp-258h] BYREF
  UINT v44; // [rsp+68h] [rbp-250h] BYREF
  _QWORD v45[2]; // [rsp+70h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+80h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  hDlga = hDlg;
  v6 = a3 - 78;
  if ( v6 )
  {
    v7 = v6 - 194;
    if ( !v7 )
    {
      v8 = (char *)this + 40;
      v45[0] = (char *)this + 40;
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
      if ( (unsigned int)PathIsTemporaryW(v9) )
      {
        v40[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
        v40[1] = *((_QWORD *)v8 + 2);
        split_filename(v41, v40);
        if ( (int)SHGetFolderPathEx(&FOLDERID_Documents, 0, 0, pszPath, 260) >= 0
          && PathCchAppend(pszPath, 0x104u, pszMore) >= 0 )
        {
          try
          {
            v10 = -1;
            do
              ++v10;
            while ( pszPath[v10] );
            std::wstring::_Assign<unsigned short>(v8, pszPath);
          }
          catch ( ... )
          {
            wil::details::in1diag3::Log_CaughtException(
              retaddr,
              (void *)0x5A8,
              (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
              v11);
            v8 = (char *)v45[0];
          }
        }
      }
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
      SetDlgItemTextW(hDlga, 1045, v12);
      DlgItem = GetDlgItem(hDlga, 1045);
      SHAutoComplete(DlgItem, 0x20u);
      return 1;
    }
    if ( v7 == 1 )
    {
      if ( a4 == 1021 )
        ArchiveExtractWizard::Browse(hDlg);
      return 1;
    }
    return 0;
  }
  v14 = *(_DWORD *)(a5 + 16);
  if ( v14 == -208 )
  {
    v21 = GetDlgItem(hDlg, 1021);
    EnableWindow(v21, 0);
    v22 = GetDlgItem(hDlga, 1045);
    EnableWindow(v22, 0);
    v23 = GetDlgItem(hDlga, 1045);
    WindowTextLengthW = GetWindowTextLengthW(v23);
    v45[0] = &hDlga;
    try
    {
      v25 = (char *)this + 40;
      std::wstring::resize((char *)this + 40, WindowTextLengthW);
      v26 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
      WindowTextW = GetWindowTextW(v23, v26, WindowTextLengthW + 1);
      std::wstring::resize((char *)this + 40, WindowTextW);
      v28 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
      if ( StrTrimW(v28, pszTrimChars) )
      {
        v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)(v30 + 2 * v31) );
        std::wstring::resize((char *)this + 40, v31);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x5EE,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        v29);
      return (int)_lambda_33f94a0a4020c4e31cc6fb78aab6f056_::operator()(v45);
    }
    if ( (int)ArchiveExtractWizard::ValidateDestinationPath(this) >= 0 )
    {
      v33 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
      if ( PathIsRelativeW(v33) )
      {
        v32 = 10425;
      }
      else
      {
        v34 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
        v35 = PathFileExistsW(v34);
        if ( !v35
          || (v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25),
              PathIsDirectoryW(v36)) )
        {
          v37 = ArchiveExtractWizard::ExtractToDestination(this, hDlga, !v35);
          if ( !v37 )
          {
            v44 = IsDlgButtonChecked(hDlga, 1098);
            SKSetValueW(1, L"ExtractionWizard", L"ShowFiles");
            if ( v44 == 1 )
            {
              v38 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
              ShellExecuteW(hDlga, 0, v38, 0, 0, 1);
            }
            return 1;
          }
          *((_DWORD *)this + 18) = v37;
          if ( v37 == -2147023673 )
          {
            v39 = 2;
          }
          else if ( v37 == -2147018894 )
          {
            *((_DWORD *)this + 19) = 10577;
            v39 = 3;
          }
          else
          {
            if ( v37 >= 0 )
              return (int)_lambda_33f94a0a4020c4e31cc6fb78aab6f056_::operator()(v45);
            v39 = 4;
          }
          SendMessageW(hDlga, 0x465u, v39, 0);
          return (int)_lambda_33f94a0a4020c4e31cc6fb78aab6f056_::operator()(v45);
        }
        v32 = 10426;
      }
    }
    else
    {
      v32 = 10424;
    }
    ShellMessageBoxW(&_ImageBase, hDlga, (LPCWSTR)v32, (LPCWSTR)0x2941, 0x10u);
    return (int)_lambda_33f94a0a4020c4e31cc6fb78aab6f056_::operator()(v45);
  }
  if ( ((v14 + 203) & 0xFFFFFFFD) != 0 )
  {
    if ( v14 == -200 )
    {
      PostMessageW(hDlg, 0x470u, 0, 4);
      LoadStringW(&_ImageBase, 0x2910u, pszPath, 260);
      Parent = GetParent(hDlga);
      SendMessageW(Parent, 0x479u, 0, (LPARAM)pszPath);
      v17 = GetDlgItem(hDlga, 1021);
      EnableWindow(v17, 1);
      v18 = 0;
      v44 = 0;
      LODWORD(v45[0]) = 4;
      if ( (int)SKGetValueW(1, L"ExtractionWizard", L"ShowFiles", 0, &v44, v45) >= 0 )
      {
        v19 = v44;
      }
      else
      {
        v19 = 1;
        v44 = 1;
      }
      LOBYTE(v18) = v19 != 0;
      v20 = GetDlgItem(hDlga, 1098);
      SendMessageW(v20, 0xF1u, v18, 0);
      return 1;
    }
    return 0;
  }
  SetWindowLongPtrW(hDlg, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x180028d64  mov     [rsp+arg_10], rbx
0x180028d69  push    rsi
0x180028d6a  push    rdi
0x180028d6b  push    r14
0x180028d6d  sub     rsp, 2A0h
0x180028d74  mov     rax, cs:__security_cookie
0x180028d7b  xor     rax, rsp
0x180028d7e  mov     [rsp+2B8h+var_28], rax
0x180028d86  mov     r10, rdx
0x180028d89  mov     rsi, rcx
0x180028d8c  mov     [rsp+2B8h+hDlg], rdx
0x180028d91  sub     r8d, 4Eh ; 'N'
0x180028d95  jz      loc_180028EC0
0x180028d9b  sub     r8d, 0C2h
0x180028da2  jz      short loc_180028DC8
0x180028da4  cmp     r8d, 1
0x180028da8  jnz     loc_180028EF0
0x180028dae  cmp     r9, 3FDh
0x180028db5  jnz     loc_1800291EB
0x180028dbb  mov     rcx, rdx; hDlg
0x180028dbe  call    ?Browse@ArchiveExtractWizard@@CAJPEAUHWND__@@@Z; ArchiveExtractWizard::Browse(HWND__ *)
0x180028dc3  jmp     loc_1800291EB
0x180028dc8  lea     rdi, [rcx+28h]
0x180028dcc  mov     [rsp+2B8h+var_248], rdi
0x180028dd1  mov     rcx, rdi
0x180028dd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028dd9  mov     rcx, rax
0x180028ddc  call    cs:__imp_PathIsTemporaryW
0x180028de2  xor     ebx, ebx
0x180028de4  test    eax, eax
0x180028de6  jz      loc_180028E83
0x180028dec  mov     rcx, rdi
0x180028def  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028df4  mov     [rsp+2B8h+var_288], rax
0x180028df9  mov     rax, [rdi+10h]
0x180028dfd  mov     [rsp+2B8h+var_280], rax
0x180028e02  lea     rdx, [rsp+2B8h+var_288]
0x180028e07  lea     rcx, [rsp+2B8h+var_278]
0x180028e0c  call    ?split_filename@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_filename(std::basic_string_view<ushort>)
0x180028e11  mov     [rsp+2B8h+fuStyle], 104h
0x180028e19  lea     r9, [rsp+2B8h+pszPath]
0x180028e21  xor     r8d, r8d
0x180028e24  xor     edx, edx
0x180028e26  lea     rcx, FOLDERID_Documents
0x180028e2d  call    cs:__imp_SHGetFolderPathEx
0x180028e33  test    eax, eax
0x180028e35  js      short loc_180028E83
0x180028e37  mov     r8, [rsp+2B8h+pszMore]; pszMore
0x180028e3c  mov     edx, 104h; cchPath
0x180028e41  lea     rcx, [rsp+2B8h+pszPath]; pszPath
0x180028e49  call    cs:__imp_PathCchAppend
0x180028e4f  test    eax, eax
0x180028e51  js      short loc_180028E83
0x180028e53  lea     rax, [rsp+2B8h+pszPath]
0x180028e5b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180028e5f  inc     rdx
0x180028e62  cmp     [rax+rdx*2], bx
0x180028e66  jnz     short loc_180028E5F
0x180028e68  mov     r8, rdx
0x180028e6b  lea     rdx, [rsp+2B8h+pszPath]
0x180028e73  mov     rcx, rdi
0x180028e76  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028e7b  nop
0x180028e7c  jmp     short loc_180028E83
0x180028e7e  mov     rdi, [rsp+2B8h+var_248]
0x180028e83  mov     rcx, rdi
0x180028e86  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028e8b  mov     r8, rax; lpString
0x180028e8e  mov     ebx, 415h
0x180028e93  mov     edx, ebx; nIDDlgItem
0x180028e95  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x180028e9a  call    cs:__imp_SetDlgItemTextW
0x180028ea0  mov     edx, ebx; nIDDlgItem
0x180028ea2  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x180028ea7  call    cs:__imp_GetDlgItem
0x180028ead  mov     rcx, rax; hwndEdit
0x180028eb0  mov     edx, 20h ; ' '; dwFlags
0x180028eb5  call    cs:__imp_SHAutoComplete
0x180028ebb  jmp     loc_1800291EB
0x180028ec0  mov     rax, [rsp+2B8h+arg_20]
0x180028ec8  mov     ecx, [rax+10h]
0x180028ecb  cmp     ecx, 0FFFFFF30h
0x180028ed1  jz      loc_180028FFE
0x180028ed7  lea     eax, [rcx+0CBh]
0x180028edd  test    eax, 0FFFFFFFDh
0x180028ee2  jz      loc_180028FEB
0x180028ee8  cmp     ecx, 0FFFFFF38h
0x180028eee  jz      short loc_180028EF7
0x180028ef0  xor     eax, eax
0x180028ef2  jmp     loc_180029245
0x180028ef7  mov     r9d, 4; lParam
0x180028efd  xor     r8d, r8d; wParam
0x180028f00  mov     edx, 470h; Msg
0x180028f05  mov     rcx, r10; hWnd
0x180028f08  call    cs:__imp_PostMessageW
0x180028f0e  mov     r9d, 104h; cchBufferMax
0x180028f14  lea     r8, [rsp+2B8h+pszPath]; lpBuffer
0x180028f1c  mov     edx, 2910h; uID
0x180028f21  lea     rcx, __ImageBase; hInstance
0x180028f28  call    cs:__imp_LoadStringW
0x180028f2e  mov     rcx, [rsp+2B8h+hDlg]; hWnd
0x180028f33  call    cs:__imp_GetParent
0x180028f39  mov     rcx, rax; hWnd
0x180028f3c  lea     r9, [rsp+2B8h+pszPath]; lParam
0x180028f44  xor     r8d, r8d; wParam
0x180028f47  mov     edx, 479h; Msg
0x180028f4c  call    cs:__imp_SendMessageW
0x180028f52  mov     edx, 3FDh; nIDDlgItem
0x180028f57  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x180028f5c  call    cs:__imp_GetDlgItem
0x180028f62  mov     rcx, rax; hWnd
0x180028f65  mov     edx, 1; bEnable
0x180028f6a  call    cs:__imp_EnableWindow
0x180028f70  xor     ebx, ebx
0x180028f72  mov     [rsp+2B8h+var_250], ebx
0x180028f76  mov     dword ptr [rsp+2B8h+var_248], 4
0x180028f7e  lea     rax, [rsp+2B8h+var_248]
0x180028f83  mov     qword ptr [rsp+2B8h+nShowCmd], rax
0x180028f88  lea     rax, [rsp+2B8h+var_250]
0x180028f8d  mov     qword ptr [rsp+2B8h+fuStyle], rax
0x180028f92  xor     r9d, r9d
0x180028f95  lea     r8, aShowfiles; "ShowFiles"
0x180028f9c  lea     rdx, aExtractionwiza; "ExtractionWizard"
0x180028fa3  lea     ecx, [rbx+1]
0x180028fa6  call    cs:__imp_SKGetValueW
0x180028fac  test    eax, eax
0x180028fae  jns     short loc_180028FB9
0x180028fb0  lea     eax, [rbx+1]
0x180028fb3  mov     [rsp+2B8h+var_250], eax
0x180028fb7  jmp     short loc_180028FBD
0x180028fb9  mov     eax, [rsp+2B8h+var_250]
0x180028fbd  test    eax, eax
0x180028fbf  setnz   bl
0x180028fc2  mov     edx, 44Ah; nIDDlgItem
0x180028fc7  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x180028fcc  call    cs:__imp_GetDlgItem
0x180028fd2  mov     rcx, rax; hWnd
0x180028fd5  xor     r9d, r9d; lParam
0x180028fd8  mov     r8, rbx; wParam
0x180028fdb  mov     edx, 0F1h; Msg
0x180028fe0  call    cs:__imp_SendMessageW
0x180028fe6  jmp     loc_1800291EB
0x180028feb  xor     r8d, r8d; dwNewLong
0x180028fee  xor     edx, edx; nIndex
0x180028ff0  mov     rcx, r10; hWnd
0x180028ff3  call    cs:__imp_SetWindowLongPtrW
0x180028ff9  jmp     loc_1800291EB
0x180028ffe  mov     edx, 3FDh; nIDDlgItem
0x180029003  mov     rcx, r10; hDlg
0x180029006  call    cs:__imp_GetDlgItem
0x18002900c  mov     rcx, rax; hWnd
0x18002900f  xor     edx, edx; bEnable
0x180029011  call    cs:__imp_EnableWindow
0x180029017  mov     ebx, 415h
0x18002901c  mov     edx, ebx; nIDDlgItem
0x18002901e  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x180029023  call    cs:__imp_GetDlgItem
0x180029029  mov     rcx, rax; hWnd
0x18002902c  xor     edx, edx; bEnable
0x18002902e  call    cs:__imp_EnableWindow
0x180029034  mov     edx, ebx; nIDDlgItem
0x180029036  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x18002903b  call    cs:__imp_GetDlgItem
0x180029041  mov     r14, rax
0x180029044  mov     rcx, rax; hWnd
0x180029047  call    cs:__imp_GetWindowTextLengthW
0x18002904d  movsxd  rbx, eax
0x180029050  lea     rax, [rsp+2B8h+hDlg]
0x180029055  mov     [rsp+2B8h+var_248], rax
0x18002905a  lea     rdi, [rsi+28h]
0x18002905e  mov     rdx, rbx
0x180029061  mov     rcx, rdi
0x180029064  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180029069  mov     rcx, rdi
0x18002906c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029071  lea     r8d, [rbx+1]; nMaxCount
0x180029075  mov     rdx, rax; lpString
0x180029078  mov     rcx, r14; hWnd
0x18002907b  call    cs:__imp_GetWindowTextW
0x180029081  movsxd  rdx, eax
0x180029084  mov     rcx, rdi
0x180029087  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002908c  mov     rcx, rdi
0x18002908f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029094  lea     rdx, pszTrimChars; " \t"
0x18002909b  mov     rcx, rax; psz
0x18002909e  call    cs:__imp_StrTrimW
0x1800290a4  xor     ebx, ebx
0x1800290a6  test    eax, eax
0x1800290a8  jz      short loc_1800290C8
0x1800290aa  mov     rcx, rdi
0x1800290ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800290b2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800290b6  inc     rdx
0x1800290b9  cmp     [rax+rdx*2], bx
0x1800290bd  jnz     short loc_1800290B6
0x1800290bf  mov     rcx, rdi
0x1800290c2  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800290c7  nop
0x1800290c8  mov     rcx, rsi; this
0x1800290cb  call    ?ValidateDestinationPath@ArchiveExtractWizard@@AEAAJXZ; ArchiveExtractWizard::ValidateDestinationPath(void)
0x1800290d0  test    eax, eax
0x1800290d2  jns     short loc_18002910B
0x1800290d4  mov     r8d, 28B8h; lpcText
0x1800290da  mov     [rsp+2B8h+fuStyle], 10h; fuStyle
0x1800290e2  mov     r9d, 2941h; lpcTitle
0x1800290e8  mov     rdx, [rsp+2B8h+hDlg]; hWnd
0x1800290ed  lea     rcx, __ImageBase; hAppInst
0x1800290f4  call    cs:__imp_ShellMessageBoxW
0x1800290fa  lea     rcx, [rsp+2B8h+var_248]
0x1800290ff  call    ??R_lambda_33f94a0a4020c4e31cc6fb78aab6f056_@@QEBA@XZ; _lambda_33f94a0a4020c4e31cc6fb78aab6f056_::operator()(void)
0x180029104  cdqe
0x180029106  jmp     loc_180029245
0x18002910b  mov     rcx, rdi
0x18002910e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029113  mov     rcx, rax; pszPath
0x180029116  call    cs:__imp_PathIsRelativeW
0x18002911c  test    eax, eax
0x18002911e  jz      short loc_180029128
0x180029120  mov     r8d, 28B9h
0x180029126  jmp     short loc_1800290DA
0x180029128  mov     rcx, rdi
0x18002912b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029130  mov     rcx, rax; pszPath
0x180029133  call    cs:__imp_PathFileExistsW
0x180029139  mov     r14d, eax
0x18002913c  test    eax, eax
0x18002913e  jz      short loc_180029160
0x180029140  mov     rcx, rdi
0x180029143  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029148  mov     rcx, rax; pszPath
0x18002914b  call    cs:__imp_PathIsDirectoryW
0x180029151  test    eax, eax
0x180029153  jnz     short loc_180029160
0x180029155  mov     r8d, 28BAh
0x18002915b  jmp     loc_1800290DA
0x180029160  test    r14d, r14d
0x180029163  setz    r8b; bool
0x180029167  mov     rdx, [rsp+2B8h+hDlg]; HWND
0x18002916c  mov     rcx, rsi; this
0x18002916f  call    ?ExtractToDestination@ArchiveExtractWizard@@AEAAJPEAUHWND__@@_N@Z; ArchiveExtractWizard::ExtractToDestination(HWND__ *,bool)
0x180029174  test    eax, eax
0x180029176  jnz     short loc_1800291F2
0x180029178  mov     edx, 44Ah; nIDButton
0x18002917d  mov     rcx, [rsp+2B8h+hDlg]; hDlg
0x180029182  call    cs:__imp_IsDlgButtonChecked
0x180029188  mov     [rsp+2B8h+var_250], eax
0x18002918c  mov     [rsp+2B8h+nShowCmd], 4
0x180029194  lea     rax, [rsp+2B8h+var_250]
0x180029199  mov     qword ptr [rsp+2B8h+fuStyle], rax
0x18002919e  mov     r9d, 4
0x1800291a4  lea     r8, aShowfiles; "ShowFiles"
0x1800291ab  lea     rdx, aExtractionwiza; "ExtractionWizard"
0x1800291b2  lea     ecx, [r9-3]
0x1800291b6  call    cs:__imp_SKSetValueW
0x1800291bc  cmp     [rsp+2B8h+var_250], 1
0x1800291c1  jnz     short loc_1800291EB
0x1800291c3  mov     rcx, rdi
0x1800291c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800291cb  mov     [rsp+2B8h+nShowCmd], 1; nShowCmd
0x1800291d3  mov     qword ptr [rsp+2B8h+fuStyle], rbx; lpDirectory
0x1800291d8  xor     r9d, r9d; lpParameters
0x1800291db  mov     r8, rax; lpFile
0x1800291de  xor     edx, edx; lpOperation
0x1800291e0  mov     rcx, [rsp+2B8h+hDlg]; hwnd
0x1800291e5  call    cs:__imp_ShellExecuteW
0x1800291eb  mov     eax, 1
0x1800291f0  jmp     short loc_180029245
0x1800291f2  mov     [rsi+48h], eax
0x1800291f5  cmp     eax, 800704C7h
0x1800291fa  jnz     short loc_180029204
0x1800291fc  mov     r8d, 2
0x180029202  jmp     short loc_180029228
0x180029204  cmp     eax, 80071772h
0x180029209  jnz     short loc_18002921A
0x18002920b  mov     dword ptr [rsi+4Ch], 2951h
0x180029212  mov     r8d, 3
0x180029218  jmp     short loc_180029228
0x18002921a  test    eax, eax
0x18002921c  jns     loc_1800290FA
0x180029222  mov     r8d, 4; wParam
0x180029228  xor     r9d, r9d; lParam
0x18002922b  mov     edx, 465h; Msg
0x180029230  mov     rcx, [rsp+2B8h+hDlg]; hWnd
0x180029235  call    cs:__imp_SendMessageW
0x18002923b  jmp     loc_1800290FA
0x180029240  mov     rax, [rsp+2B8h+hDlg]
0x180029245  mov     rcx, [rsp+2B8h+var_28]
0x18002924d  xor     rcx, rsp; StackCookie
0x180029250  call    __security_check_cookie
0x180029255  mov     rbx, [rsp+2B8h+arg_10]
0x18002925d  add     rsp, 2A0h
0x180029264  pop     r14
0x180029266  pop     rdi
0x180029267  pop     rsi
0x180029268  retn
```
