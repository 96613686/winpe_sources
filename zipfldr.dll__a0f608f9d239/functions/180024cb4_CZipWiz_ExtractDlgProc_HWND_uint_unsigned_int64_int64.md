# CZipWiz::_ExtractDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180024cb4`
- end: `0x180025183`
- name: `?_ExtractDlgProc@CZipWiz@@AEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1231`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *this@<rcx>, HWND hWnd@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180024c70`

## callees

- `0x180010c30`
- `0x18002270c`
- `0x180024cb4`
- `0x180036f50`
- `0x18003ef3c`
- `0x180041fbc`
- `0x180042718`
- `0x180042974`
- `0x1800429f0`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180024d6f`
- `SHELL32!SHGetFolderPathEx` at `0x180024d6f`
- `SHELL32!ShellExecuteW` at `0x1800250a9`
- `SHELL32!ShellExecuteW` at `0x1800250a9`
- `SHELL32!__imp_PathIsTemporaryW` at `0x180024d2a`
- `SHELL32!__imp_PathIsTemporaryW` at `0x180024d2a`
- `SHLWAPI!PathAppendW` at `0x180024d81`
- `SHLWAPI!PathAppendW` at `0x180024d81`
- `SHLWAPI!PathFindFileNameW` at `0x180024d37`
- `SHLWAPI!PathFindFileNameW` at `0x180024d37`
- `SHLWAPI!PathFileExistsW` at `0x180024fc9`
- `SHLWAPI!PathFileExistsW` at `0x180024fc9`
- `SHLWAPI!SHAutoComplete` at `0x180024dae`
- `SHLWAPI!SHAutoComplete` at `0x180024dae`
- `SHLWAPI!StrTrimW` at `0x180024f56`
- `SHLWAPI!StrTrimW` at `0x180024f56`
- `SHLWAPI!PathIsRelativeW` at `0x180024f89`
- `SHLWAPI!PathIsRelativeW` at `0x180024f89`
- `SHLWAPI!PathIsDirectoryW` at `0x180024fd9`
- `SHLWAPI!PathIsDirectoryW` at `0x180024fd9`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800250f8`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800250f8`
- `SHLWAPI!__imp_SKGetValueW` at `0x180024e9e`
- `SHLWAPI!__imp_SKGetValueW` at `0x180024e9e`
- `SHLWAPI!__imp_SKSetValueW` at `0x180025085`
- `SHLWAPI!__imp_SKSetValueW` at `0x180025085`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180024e26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180024e26`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180025040`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180025040`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x18002502a`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180025037`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x18002502a`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x180025037`
- `USER32!SetDlgItemTextW` at `0x180024d92`
- `USER32!SetDlgItemTextW` at `0x180024d92`
- `USER32!GetParent` at `0x180024df2`
- `USER32!GetParent` at `0x180024e2f`
- `USER32!GetParent` at `0x1800250b7`
- `USER32!GetParent` at `0x180024df2`
- `USER32!GetParent` at `0x180024e2f`
- `USER32!GetParent` at `0x1800250b7`
- `USER32!SetWindowLongPtrW` at `0x180024ee3`
- `USER32!SetWindowLongPtrW` at `0x18002514f`
- `USER32!SetWindowLongPtrW` at `0x180024ee3`
- `USER32!SetWindowLongPtrW` at `0x18002514f`
- `USER32!PostMessageW` at `0x180024e09`
- `USER32!PostMessageW` at `0x180024e09`
- `USER32!SendMessageW` at `0x180024e45`
- `USER32!SendMessageW` at `0x180024ed0`
- `USER32!SendMessageW` at `0x1800250cc`
- `USER32!SendMessageW` at `0x180024e45`
- `USER32!SendMessageW` at `0x180024ed0`
- `USER32!SendMessageW` at `0x1800250cc`
- `USER32!EnableWindow` at `0x180024e63`
- `USER32!EnableWindow` at `0x180024f06`
- `USER32!EnableWindow` at `0x180024f1f`
- `USER32!EnableWindow` at `0x180025111`
- `USER32!EnableWindow` at `0x18002512a`
- `USER32!EnableWindow` at `0x180024e63`
- `USER32!EnableWindow` at `0x180024f06`
- `USER32!EnableWindow` at `0x180024f1f`
- `USER32!EnableWindow` at `0x180025111`
- `USER32!EnableWindow` at `0x18002512a`
- `USER32!GetDlgItem` at `0x180024da0`
- `USER32!GetDlgItem` at `0x180024e53`
- `USER32!GetDlgItem` at `0x180024ebc`
- `USER32!GetDlgItem` at `0x180024efb`
- `USER32!GetDlgItem` at `0x180024f14`
- `USER32!GetDlgItem` at `0x180024f34`
- `USER32!GetDlgItem` at `0x180025106`
- `USER32!GetDlgItem` at `0x18002511f`
- `USER32!GetDlgItem` at `0x180025138`
- `USER32!GetDlgItem` at `0x180024da0`
- `USER32!GetDlgItem` at `0x180024e53`
- `USER32!GetDlgItem` at `0x180024ebc`
- `USER32!GetDlgItem` at `0x180024efb`
- `USER32!GetDlgItem` at `0x180024f14`
- `USER32!GetDlgItem` at `0x180024f34`
- `USER32!GetDlgItem` at `0x180025106`
- `USER32!GetDlgItem` at `0x18002511f`
- `USER32!GetDlgItem` at `0x180025138`
- `USER32!GetWindowTextW` at `0x180024f46`
- `USER32!GetWindowTextW` at `0x180024f46`
- `USER32!IsDlgButtonChecked` at `0x180025053`
- `USER32!IsDlgButtonChecked` at `0x180025053`
- `USER32!SetFocus` at `0x180025141`
- `USER32!SetFocus` at `0x180025141`

## pseudocode

```c
__int64 __fastcall CZipWiz::_ExtractDlgProc(struct IUnknown *this, HWND hWnd, int a3, __int64 a4, __int64 a5)
{
  int v7; // r8d
  int v8; // r8d
  WCHAR *v9; // rdi
  const unsigned __int16 *FileNameW; // rax
  HWND DlgItem; // rax
  int v12; // ecx
  HWND v14; // rax
  HWND v15; // rax
  HWND v16; // rax
  WPARAM v17; // rbx
  HWND v18; // rax
  HWND v19; // rax
  HWND v20; // rax
  HWND v21; // rax
  CZipWiz *v22; // rcx
  unsigned __int64 v23; // r8
  CZipWiz *v24; // rcx
  char IsEnabled; // al
  __int64 v26; // rcx
  __int64 v27; // r8
  struct IUnknownVtbl *lpVtbl; // rdx
  BOOL v29; // r13d
  int v30; // eax
  HWND Parent; // rax
  HWND v32; // rax
  HWND v33; // rax
  HWND v34; // rax
  UINT v35; // [rsp+30h] [rbp-D0h] BYREF
  int v36[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR pszMore[264]; // [rsp+40h] [rbp-C0h] BYREF

  v7 = a3 - 78;
  if ( v7 )
  {
    v8 = v7 - 194;
    if ( !v8 )
    {
      v9 = (WCHAR *)&this[66].lpVtbl + 2;
      if ( (unsigned int)PathIsTemporaryW((char *)&this[66].lpVtbl + 4) )
      {
        FileNameW = PathFindFileNameW(v9);
        if ( FileNameW != v9
          && (int)StringCchCopyW(pszMore, 0x104u, FileNameW) >= 0
          && (int)SHGetFolderPathEx(&FOLDERID_Documents, 0, 0, v9, 260) >= 0 )
        {
          PathAppendW(v9, pszMore);
        }
      }
      SetDlgItemTextW(hWnd, 1045, v9);
      DlgItem = GetDlgItem(hWnd, 1045);
      SHAutoComplete(DlgItem, 0x20u);
      return 1;
    }
    if ( v8 == 1 && a4 == 1021 )
    {
      CZipWiz::_Browse((CZipWiz *)this, hWnd);
      return 1;
    }
    return 0;
  }
  v12 = *(_DWORD *)(a5 + 16);
  if ( v12 == -208 )
  {
    v19 = GetDlgItem(hWnd, 1021);
    EnableWindow(v19, 0);
    v20 = GetDlgItem(hWnd, 1045);
    EnableWindow(v20, 0);
    v21 = GetDlgItem(hWnd, 1045);
    GetWindowTextW(v21, (LPWSTR)&this[66].lpVtbl + 2, 260);
    StrTrimW((PWSTR)&this[66].lpVtbl + 2, pszTrimChars);
    if ( CZipWiz::_ValidatePath(
           v22,
           (const unsigned __int16 *)&this[66].lpVtbl + 2,
           v23,
           (unsigned __int16 *)&this[66].lpVtbl + 2) < 0
      || CZipWiz::_PathEndsWithDot(v24, (const unsigned __int16 *)&this[66].lpVtbl + 2) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
      v27 = 10424;
    }
    else if ( PathIsRelativeW((LPCWSTR)&this[66].lpVtbl + 2) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
      v27 = 10425;
    }
    else
    {
      v29 = PathFileExistsW((LPCWSTR)&this[66].lpVtbl + 2);
      if ( !v29 || PathIsDirectoryW((LPCWSTR)&this[66].lpVtbl + 2) )
      {
        v30 = CZipWiz::_PerformExtraction(this, !v29);
        if ( v30 == 1 || v30 == -2147023673 )
        {
          Parent = GetParent(hWnd);
          SendMessageW(Parent, 0x465u, 3u, 0);
        }
        else
        {
          if ( v30 >= 0 )
          {
            v35 = IsDlgButtonChecked(hWnd, 1098);
            SKSetValueW(1, L"ExtractionWizard", L"ShowFiles", 4, &v35, 4);
            if ( v35 == 1 )
              ShellExecuteW(hWnd, 0, (LPCWSTR)&this[66].lpVtbl + 2, 0, 0, 1);
            return 1;
          }
          if ( !v29 )
          {
            SetCurrentDirectoryW((LPCWSTR)&this[66].lpVtbl + 2);
            SetCurrentDirectoryW(L"..");
            RemoveDirectoryW((LPCWSTR)&this[66].lpVtbl + 2);
          }
        }
        goto LABEL_41;
      }
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl);
      v27 = 10426;
    }
    lpVtbl = this[133].lpVtbl;
    if ( IsEnabled )
      MessageBoxHelper::ShellMessageBoxTextScaled___2(v26, lpVtbl, v27);
    else
      ShellMessageBoxW(g_hmodThisDll, (HWND)lpVtbl, (LPCWSTR)v27, (LPCWSTR)0x2747, 0x10u);
LABEL_41:
    v32 = GetDlgItem(hWnd, 1021);
    EnableWindow(v32, 1);
    v33 = GetDlgItem(hWnd, 1045);
    EnableWindow(v33, 1);
    v34 = GetDlgItem(hWnd, 1045);
    SetFocus(v34);
    SetWindowLongPtrW(hWnd, 0, 1);
    return 1;
  }
  if ( ((v12 + 203) & 0xFFFFFFFD) == 0 )
  {
    SetWindowLongPtrW(hWnd, 0, 0);
    return 1;
  }
  if ( v12 != -200 )
    return 0;
  v14 = GetParent(hWnd);
  PostMessageW(v14, 0x470u, 0, 4);
  LoadStringW(g_hmodThisDll, 0x2910u, pszMore, 260);
  v15 = GetParent(hWnd);
  SendMessageW(v15, 0x479u, 0, (LPARAM)pszMore);
  v16 = GetDlgItem(hWnd, 1021);
  EnableWindow(v16, 1);
  v36[0] = 4;
  v17 = 0;
  v35 = 0;
  if ( (int)SKGetValueW(1, L"ExtractionWizard", L"ShowFiles", 0, &v35, v36) < 0 )
    v17 = 1;
  else
    LOBYTE(v17) = v35 != 0;
  v18 = GetDlgItem(hWnd, 1098);
  SendMessageW(v18, 0xF1u, v17, 0);
  return 1;
}

```

## disassembly

```asm
0x180024cb4  mov     [rsp-8+arg_10], rbx
0x180024cb9  mov     [rsp-8+arg_18], rsi
0x180024cbe  push    rbp
0x180024cbf  push    rdi
0x180024cc0  push    r13
0x180024cc2  push    r14
0x180024cc4  push    r15
0x180024cc6  lea     rbp, [rsp-160h]
0x180024cce  sub     rsp, 260h
0x180024cd5  mov     rax, cs:__security_cookie
0x180024cdc  xor     rax, rsp
0x180024cdf  mov     [rbp+180h+var_30], rax
0x180024ce6  mov     rsi, rdx
0x180024ce9  mov     r15, rcx
0x180024cec  sub     r8d, 4Eh ; 'N'
0x180024cf0  jz      loc_180024DB9
0x180024cf6  sub     r8d, 0C2h
0x180024cfd  jz      short loc_180024D20
0x180024cff  cmp     r8d, 1
0x180024d03  jnz     loc_180024DE8
0x180024d09  cmp     r9, 3FDh
0x180024d10  jnz     loc_180024DE8
0x180024d16  call    ?_Browse@CZipWiz@@AEAAJPEAUHWND__@@@Z; CZipWiz::_Browse(HWND__ *)
0x180024d1b  jmp     loc_180024EE9
0x180024d20  lea     rdi, [rcx+214h]
0x180024d27  mov     rcx, rdi
0x180024d2a  call    cs:__imp_PathIsTemporaryW
0x180024d30  test    eax, eax
0x180024d32  jz      short loc_180024D87
0x180024d34  mov     rcx, rdi; pszPath
0x180024d37  call    cs:__imp_PathFindFileNameW
0x180024d3d  cmp     rax, rdi
0x180024d40  jz      short loc_180024D87
0x180024d42  mov     r8, rax; unsigned __int16 *
0x180024d45  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x180024d4a  mov     edx, 104h; unsigned __int64
0x180024d4f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024d54  test    eax, eax
0x180024d56  js      short loc_180024D87
0x180024d58  mov     r9, rdi
0x180024d5b  mov     dword ptr [rsp+280h+lpDirectory], 104h
0x180024d63  xor     r8d, r8d
0x180024d66  lea     rcx, FOLDERID_Documents
0x180024d6d  xor     edx, edx
0x180024d6f  call    cs:__imp_SHGetFolderPathEx
0x180024d75  test    eax, eax
0x180024d77  js      short loc_180024D87
0x180024d79  lea     rdx, [rsp+280h+pszMore]; pszMore
0x180024d7e  mov     rcx, rdi; pszPath
0x180024d81  call    cs:__imp_PathAppendW
0x180024d87  mov     r8, rdi; lpString
0x180024d8a  mov     edx, 415h; nIDDlgItem
0x180024d8f  mov     rcx, rsi; hDlg
0x180024d92  call    cs:__imp_SetDlgItemTextW
0x180024d98  mov     edx, 415h; nIDDlgItem
0x180024d9d  mov     rcx, rsi; hDlg
0x180024da0  call    cs:__imp_GetDlgItem
0x180024da6  mov     rcx, rax; hwndEdit
0x180024da9  mov     edx, 20h ; ' '; dwFlags
0x180024dae  call    cs:__imp_SHAutoComplete
0x180024db4  jmp     loc_180024EE9
0x180024db9  mov     rax, [rbp+180h+arg_20]
0x180024dc0  mov     ecx, [rax+10h]
0x180024dc3  cmp     ecx, 0FFFFFF30h
0x180024dc9  jz      loc_180024EF3
0x180024dcf  lea     eax, [rcx+0CBh]
0x180024dd5  test    eax, 0FFFFFFFDh
0x180024dda  jz      loc_180024EDB
0x180024de0  cmp     ecx, 0FFFFFF38h
0x180024de6  jz      short loc_180024DEF
0x180024de8  xor     eax, eax
0x180024dea  jmp     loc_180025158
0x180024def  mov     rcx, rsi; hWnd
0x180024df2  call    cs:__imp_GetParent
0x180024df8  mov     r9d, 4; lParam
0x180024dfe  xor     r8d, r8d; wParam
0x180024e01  mov     rcx, rax; hWnd
0x180024e04  mov     edx, 470h; Msg
0x180024e09  call    cs:__imp_PostMessageW
0x180024e0f  mov     rcx, cs:g_hmodThisDll; hInstance
0x180024e16  lea     r8, [rsp+280h+pszMore]; lpBuffer
0x180024e1b  mov     r9d, 104h; cchBufferMax
0x180024e21  mov     edx, 2910h; uID
0x180024e26  call    cs:__imp_LoadStringW
0x180024e2c  mov     rcx, rsi; hWnd
0x180024e2f  call    cs:__imp_GetParent
0x180024e35  lea     r9, [rsp+280h+pszMore]; lParam
0x180024e3a  xor     r8d, r8d; wParam
0x180024e3d  mov     rcx, rax; hWnd
0x180024e40  mov     edx, 479h; Msg
0x180024e45  call    cs:__imp_SendMessageW
0x180024e4b  mov     edx, 3FDh; nIDDlgItem
0x180024e50  mov     rcx, rsi; hDlg
0x180024e53  call    cs:__imp_GetDlgItem
0x180024e59  mov     edi, 1
0x180024e5e  mov     rcx, rax; hWnd
0x180024e61  mov     edx, edi; bEnable
0x180024e63  call    cs:__imp_EnableWindow
0x180024e69  lea     rax, [rsp+280h+var_24C]
0x180024e6e  mov     [rsp+280h+var_24C], 4
0x180024e76  mov     qword ptr [rsp+280h+nShowCmd], rax
0x180024e7b  lea     r8, aShowfiles; "ShowFiles"
0x180024e82  lea     rax, [rsp+280h+var_250]
0x180024e87  xor     ebx, ebx
0x180024e89  xor     r9d, r9d
0x180024e8c  mov     [rsp+280h+lpDirectory], rax
0x180024e91  lea     rdx, aExtractionwiza; "ExtractionWizard"
0x180024e98  mov     [rsp+280h+var_250], ebx
0x180024e9c  mov     ecx, edi
0x180024e9e  call    cs:__imp_SKGetValueW
0x180024ea4  test    eax, eax
0x180024ea6  js      short loc_180024EB1
0x180024ea8  cmp     [rsp+280h+var_250], ebx
0x180024eac  setnz   bl
0x180024eaf  jmp     short loc_180024EB4
0x180024eb1  mov     rbx, rdi
0x180024eb4  mov     edx, 44Ah; nIDDlgItem
0x180024eb9  mov     rcx, rsi; hDlg
0x180024ebc  call    cs:__imp_GetDlgItem
0x180024ec2  xor     r9d, r9d; lParam
0x180024ec5  mov     r8, rbx; wParam
0x180024ec8  mov     rcx, rax; hWnd
0x180024ecb  mov     edx, 0F1h; Msg
0x180024ed0  call    cs:__imp_SendMessageW
0x180024ed6  jmp     loc_180025155
0x180024edb  xor     r8d, r8d; dwNewLong
0x180024ede  xor     edx, edx; nIndex
0x180024ee0  mov     rcx, rsi; hWnd
0x180024ee3  call    cs:__imp_SetWindowLongPtrW
0x180024ee9  mov     eax, 1
0x180024eee  jmp     loc_180025158
0x180024ef3  mov     edx, 3FDh; nIDDlgItem
0x180024ef8  mov     rcx, rsi; hDlg
0x180024efb  call    cs:__imp_GetDlgItem
0x180024f01  mov     rcx, rax; hWnd
0x180024f04  xor     edx, edx; bEnable
0x180024f06  call    cs:__imp_EnableWindow
0x180024f0c  mov     edx, 415h; nIDDlgItem
0x180024f11  mov     rcx, rsi; hDlg
0x180024f14  call    cs:__imp_GetDlgItem
0x180024f1a  mov     rcx, rax; hWnd
0x180024f1d  xor     edx, edx; bEnable
0x180024f1f  call    cs:__imp_EnableWindow
0x180024f25  mov     edx, 415h; nIDDlgItem
0x180024f2a  lea     r14, [r15+214h]
0x180024f31  mov     rcx, rsi; hDlg
0x180024f34  call    cs:__imp_GetDlgItem
0x180024f3a  mov     r8d, 104h; nMaxCount
0x180024f40  mov     rdx, r14; lpString
0x180024f43  mov     rcx, rax; hWnd
0x180024f46  call    cs:__imp_GetWindowTextW
0x180024f4c  lea     rdx, pszTrimChars; " \t"
0x180024f53  mov     rcx, r14; psz
0x180024f56  call    cs:__imp_StrTrimW
0x180024f5c  mov     r9, r14; unsigned __int16 *
0x180024f5f  mov     rdx, r14; unsigned __int16 *
0x180024f62  call    ?_ValidatePath@CZipWiz@@AEAAJPEBG_KPEAG@Z; CZipWiz::_ValidatePath(ushort const *,unsigned __int64,ushort *)
0x180024f67  xor     ebx, ebx
0x180024f69  mov     edi, 1
0x180024f6e  test    eax, eax
0x180024f70  js      loc_1800250D4
0x180024f76  mov     rdx, r14; unsigned __int16 *
0x180024f79  call    ?_PathEndsWithDot@CZipWiz@@AEAAHPEBG@Z; CZipWiz::_PathEndsWithDot(ushort const *)
0x180024f7e  test    eax, eax
0x180024f80  jnz     loc_1800250D4
0x180024f86  mov     rcx, r14; pszPath
0x180024f89  call    cs:__imp_PathIsRelativeW
0x180024f8f  test    eax, eax
0x180024f91  jz      short loc_180024FC6
0x180024f93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180024f9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180024f9f  mov     r8d, 28B9h; lpcText
0x180024fa5  mov     rdx, [r15+428h]; hWnd
0x180024fac  mov     dword ptr [rsp+280h+lpDirectory], 10h; fuStyle
0x180024fb4  test    al, al
0x180024fb6  jz      loc_1800250EB
0x180024fbc  call    MessageBoxHelper__ShellMessageBoxTextScaled___2
0x180024fc1  jmp     loc_1800250FE
0x180024fc6  mov     rcx, r14; pszPath
0x180024fc9  call    cs:__imp_PathFileExistsW
0x180024fcf  mov     r13d, eax
0x180024fd2  test    eax, eax
0x180024fd4  jz      short loc_180024FF7
0x180024fd6  mov     rcx, r14; pszPath
0x180024fd9  call    cs:__imp_PathIsDirectoryW
0x180024fdf  test    eax, eax
0x180024fe1  jnz     short loc_180024FF7
0x180024fe3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x180024fea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x180024fef  mov     r8d, 28BAh
0x180024ff5  jmp     short loc_180024FA5
0x180024ff7  mov     edx, ebx
0x180024ff9  test    r13d, r13d
0x180024ffc  mov     rcx, r15; this
0x180024fff  setz    dl; int
0x180025002  call    ?_PerformExtraction@CZipWiz@@AEAAJH@Z; CZipWiz::_PerformExtraction(int)
0x180025007  cmp     eax, edi
0x180025009  jz      loc_1800250B4
0x18002500f  cmp     eax, 800704C7h
0x180025014  jz      loc_1800250B4
0x18002501a  test    eax, eax
0x18002501c  jns     short loc_18002504B
0x18002501e  test    r13d, r13d
0x180025021  jnz     loc_1800250FE
0x180025027  mov     rcx, r14; lpPathName
0x18002502a  call    cs:__imp_SetCurrentDirectoryW
0x180025030  lea     rcx, PathName; ".."
0x180025037  call    cs:__imp_SetCurrentDirectoryW
0x18002503d  mov     rcx, r14; lpPathName
0x180025040  call    cs:__imp_RemoveDirectoryW
0x180025046  jmp     loc_1800250FE
0x18002504b  mov     edx, 44Ah; nIDButton
0x180025050  mov     rcx, rsi; hDlg
0x180025053  call    cs:__imp_IsDlgButtonChecked
0x180025059  mov     [rsp+280h+nShowCmd], 4
0x180025061  lea     r8, aShowfiles; "ShowFiles"
0x180025068  mov     [rsp+280h+var_250], eax
0x18002506c  lea     rdx, aExtractionwiza; "ExtractionWizard"
0x180025073  lea     rax, [rsp+280h+var_250]
0x180025078  mov     r9d, 4
0x18002507e  mov     ecx, edi
0x180025080  mov     [rsp+280h+lpDirectory], rax
0x180025085  call    cs:__imp_SKSetValueW
0x18002508b  cmp     [rsp+280h+var_250], edi
0x18002508f  jnz     loc_180025155
0x180025095  mov     [rsp+280h+nShowCmd], edi; nShowCmd
0x180025099  xor     r9d, r9d; lpParameters
0x18002509c  mov     r8, r14; lpFile
0x18002509f  mov     [rsp+280h+lpDirectory], rbx; lpDirectory
0x1800250a4  xor     edx, edx; lpOperation
0x1800250a6  mov     rcx, rsi; hwnd
0x1800250a9  call    cs:__imp_ShellExecuteW
0x1800250af  jmp     loc_180025155
0x1800250b4  mov     rcx, rsi; hWnd
0x1800250b7  call    cs:__imp_GetParent
0x1800250bd  xor     r9d, r9d; lParam
0x1800250c0  mov     edx, 465h; Msg
0x1800250c5  mov     rcx, rax; hWnd
0x1800250c8  lea     r8d, [r9+3]; wParam
0x1800250cc  call    cs:__imp_SendMessageW
0x1800250d2  jmp     short loc_1800250FE
0x1800250d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID53375151@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151> `wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl(void)'::`2'::impl
0x1800250db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID53375151@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(void)
0x1800250e0  mov     r8d, 28B8h
0x1800250e6  jmp     loc_180024FA5
0x1800250eb  mov     rcx, cs:g_hmodThisDll; hAppInst
0x1800250f2  mov     r9d, 2747h; lpcTitle
0x1800250f8  call    cs:__imp_ShellMessageBoxW
0x1800250fe  mov     edx, 3FDh; nIDDlgItem
0x180025103  mov     rcx, rsi; hDlg
0x180025106  call    cs:__imp_GetDlgItem
0x18002510c  mov     rcx, rax; hWnd
0x18002510f  mov     edx, edi; bEnable
0x180025111  call    cs:__imp_EnableWindow
0x180025117  mov     edx, 415h; nIDDlgItem
0x18002511c  mov     rcx, rsi; hDlg
0x18002511f  call    cs:__imp_GetDlgItem
0x180025125  mov     rcx, rax; hWnd
0x180025128  mov     edx, edi; bEnable
0x18002512a  call    cs:__imp_EnableWindow
0x180025130  mov     edx, 415h; nIDDlgItem
0x180025135  mov     rcx, rsi; hDlg
0x180025138  call    cs:__imp_GetDlgItem
0x18002513e  mov     rcx, rax; hWnd
0x180025141  call    cs:__imp_SetFocus
0x180025147  mov     r8, rdi; dwNewLong
0x18002514a  xor     edx, edx; nIndex
0x18002514c  mov     rcx, rsi; hWnd
0x18002514f  call    cs:__imp_SetWindowLongPtrW
0x180025155  mov     rax, rdi
0x180025158  mov     rcx, [rbp+180h+var_30]
0x18002515f  xor     rcx, rsp; StackCookie
0x180025162  call    __security_check_cookie
0x180025167  lea     r11, [rsp+280h+var_20]
0x18002516f  mov     rbx, [r11+40h]
0x180025173  mov     rsi, [r11+48h]
0x180025177  mov     rsp, r11
0x18002517a  pop     r15
0x18002517c  pop     r14
0x18002517e  pop     r13
0x180025180  pop     rdi
0x180025181  pop     rbp
0x180025182  retn
```
