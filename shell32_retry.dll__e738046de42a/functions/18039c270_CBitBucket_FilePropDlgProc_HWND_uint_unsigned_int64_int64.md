# CBitBucket::_FilePropDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18039c270`
- end: `0x18039c6ff`
- name: `?_FilePropDlgProc@CBitBucket@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1167`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18001bf10`
- `0x1801d76e0`
- `0x180233280`
- `0x18023378c`
- `0x1802342fc`
- `0x180251788`
- `0x1802a25d0`
- `0x1802a5410`
- `0x1802e8b3c`
- `0x18036bcec`
- `0x18039c270`
- `0x18039d35c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18039c4c7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18039c4c7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18039c499`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18039c499`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18039c53a`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18039c53a`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18039c4fa`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18039c4fa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18039c3f8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18039c3f8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18039c4ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18039c4ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18039c3da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18039c405`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18039c3da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18039c405`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18039c3cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x18039c3cd`
- `USER32!EnableWindow` at `0x18039c337`
- `USER32!EnableWindow` at `0x18039c337`
- `USER32!CheckDlgButton` at `0x18039c570`
- `USER32!CheckDlgButton` at `0x18039c5b7`
- `USER32!CheckDlgButton` at `0x18039c5ed`
- `USER32!CheckDlgButton` at `0x18039c608`
- `USER32!CheckDlgButton` at `0x18039c623`
- `USER32!CheckDlgButton` at `0x18039c570`
- `USER32!CheckDlgButton` at `0x18039c5b7`
- `USER32!CheckDlgButton` at `0x18039c5ed`
- `USER32!CheckDlgButton` at `0x18039c608`
- `USER32!CheckDlgButton` at `0x18039c623`
- `USER32!GetWindowLongPtrW` at `0x18039c2aa`
- `USER32!GetWindowLongPtrW` at `0x18039c2aa`
- `USER32!SetWindowLongPtrW` at `0x18039c34d`
- `USER32!SetWindowLongPtrW` at `0x18039c34d`
- `USER32!ShowWindow` at `0x18039c58a`
- `USER32!ShowWindow` at `0x18039c5d1`
- `USER32!ShowWindow` at `0x18039c58a`
- `USER32!ShowWindow` at `0x18039c5d1`
- `USER32!GetDlgItem` at `0x18039c32c`
- `USER32!GetDlgItem` at `0x18039c57c`
- `USER32!GetDlgItem` at `0x18039c5c3`
- `USER32!GetDlgItem` at `0x18039c32c`
- `USER32!GetDlgItem` at `0x18039c57c`
- `USER32!GetDlgItem` at `0x18039c5c3`
- `USER32!SetDlgItemTextW` at `0x18039c3a4`
- `USER32!SetDlgItemTextW` at `0x18039c3eb`
- `USER32!SetDlgItemTextW` at `0x18039c416`
- `USER32!SetDlgItemTextW` at `0x18039c456`
- `USER32!SetDlgItemTextW` at `0x18039c3a4`
- `USER32!SetDlgItemTextW` at `0x18039c3eb`
- `USER32!SetDlgItemTextW` at `0x18039c416`
- `USER32!SetDlgItemTextW` at `0x18039c456`
- `SHLWAPI!StrFormatByteSizeW` at `0x18039c441`
- `SHLWAPI!StrFormatByteSizeW` at `0x18039c441`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFileInfoW` at `0x18039c37d`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFileInfoW` at `0x18039c37d`
- `Windows.Storage!SHGetPathFromIDListW` at `0x18039c467`
- `Windows.Storage!SHGetPathFromIDListW` at `0x18039c467`

## string_xrefs

- `0x18039c308`: `undelete`

## pseudocode

```c
_BOOL8 __fastcall CBitBucket::_FilePropDlgProc(HWND a1, unsigned int a2, __int64 a3, LONG_PTR a4)
{
  LONG_PTR WindowLongPtrW; // rax
  unsigned int v9; // r9d
  LONG_PTR v10; // rsi
  HWND v11; // rax
  const WCHAR *FileNameW; // rax
  const WCHAR *v13; // rax
  HANDLE FirstFileW; // rsi
  DWORD v15; // eax
  HWND DlgItem; // rax
  HWND v17; // rax
  char dwFileAttributes; // al
  PropSheetAccAnnotation *v19; // rax
  int v20; // ecx
  PropSheetAccAnnotation *v22; // rcx
  unsigned int v23; // edx
  PropSheetAccAnnotation *v24; // rcx
  SHFILEINFOW psfi; // [rsp+40h] [rbp-C0h] BYREF
  DWORD FileSystemFlags[4]; // [rsp+300h] [rbp+200h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+310h] [rbp+210h] BYREF
  WCHAR FileSystemNameBuffer[16]; // [rsp+560h] [rbp+460h] BYREF
  WCHAR pszPath[264]; // [rsp+580h] [rbp+480h] BYREF
  WCHAR RootPathName[264]; // [rsp+790h] [rbp+690h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v10 = WindowLongPtrW;
  if ( a2 == 2 )
  {
    ReplaceDlgIcon(a1, 0x3301u, 0);
    v22 = *(PropSheetAccAnnotation **)(v10 + 136);
    if ( v22 )
    {
      PropSheetAccAnnotation::ClearAllHwndAccProperties(v22);
      v24 = *(PropSheetAccAnnotation **)(v10 + 136);
      if ( v24 )
        PropSheetAccAnnotation::`scalar deleting destructor'(v24, v23);
      *(_QWORD *)(v10 + 136) = 0;
    }
    return 0;
  }
  if ( a2 == 21 || a2 == 26 )
    goto LABEL_36;
  if ( a2 != 78 )
  {
    if ( a2 != 126 )
    {
      if ( a2 == 272 )
      {
        SetWindowLongPtrW(a1, 16, a4);
        memset_0(&psfi, 0, sizeof(psfi));
        SHGetFileInfoW(*(LPCWSTR *)(a4 + 104), 0, &psfi, 0x2B8u, 0x728u);
        ReplaceDlgIcon(a1, 0x3301u, psfi.hIcon);
        SetDlgItemTextW(a1, 13059, psfi.szTypeName);
        StringCchCopyW(pszPath, 0x104u, *(const unsigned __int16 **)(a4 + 128));
        PathRemoveExtensionW(pszPath);
        FileNameW = PathFindFileNameW(pszPath);
        SetDlgItemTextW(a1, 102, FileNameW);
        PathRemoveFileSpecW(pszPath);
        v13 = PathFindFileNameW(pszPath);
        SetDlgItemTextW(a1, 13065, v13);
        SetDateTimeTextEx(a1, 13079, (FILETIME *)(a4 + 112));
        StrFormatByteSizeW(*(_QWORD *)(a4 + 120), pszPath, 0x104u);
        SetDlgItemTextW(a1, 13064, pszPath);
        if ( SHGetPathFromIDListW(*(LPCITEMIDLIST *)(a4 + 104), pszPath) )
        {
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          FirstFileW = FindFirstFileW(pszPath, &FindFileData);
          if ( FirstFileW != (HANDLE)-1LL )
          {
            SetDateTimeTextEx(a1, 13072, &FindFileData.ftCreationTime);
            FindClose(FirstFileW);
            StringCchCopyW(RootPathName, 0x104u, pszPath);
            PathStripToRootW(RootPathName);
            PathCchAddBackslash(RootPathName, 0x104u);
            FileSystemFlags[0] = 0;
            if ( GetVolumeInformationW(RootPathName, 0, 0, 0, 0, FileSystemFlags, FileSystemNameBuffer, 0xCu) )
            {
              v15 = FileSystemFlags[0];
              if ( (FileSystemFlags[0] & 0x10) != 0 )
              {
                if ( (FindFileData.dwFileAttributes & 0x800) != 0 )
                  CheckDlgButton(a1, 13105, 1u);
                DlgItem = GetDlgItem(a1, 13105);
                ShowWindow(DlgItem, 5);
                v15 = FileSystemFlags[0];
              }
              if ( (v15 & 0x20000) != 0 )
              {
                if ( (FindFileData.dwFileAttributes & 0x4000) != 0 )
                  CheckDlgButton(a1, 13159, 1u);
                v17 = GetDlgItem(a1, 13159);
                ShowWindow(v17, 5);
              }
            }
            dwFileAttributes = FindFileData.dwFileAttributes;
            if ( (FindFileData.dwFileAttributes & 1) != 0 )
            {
              CheckDlgButton(a1, 13075, 1u);
              dwFileAttributes = FindFileData.dwFileAttributes;
            }
            if ( (dwFileAttributes & 0x20) != 0 )
            {
              CheckDlgButton(a1, 13077, 1u);
              dwFileAttributes = FindFileData.dwFileAttributes;
            }
            if ( (dwFileAttributes & 2) != 0 )
              CheckDlgButton(a1, 13076, 1u);
          }
        }
        v19 = (PropSheetAccAnnotation *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v19 )
        {
          *(_QWORD *)v19 = 0;
          *((_QWORD *)v19 + 1) = 0;
        }
        else
        {
          v19 = 0;
        }
        *(_QWORD *)(a4 + 136) = v19;
        if ( v19 )
          PropSheetAccAnnotation::MakeAllLinesAndIconsInvisibleToNarrator(v19, a1);
      }
      else if ( a2 == 273
             && (_WORD)a3 == 12323
             && !(unsigned int)SHInvokeCommandOnPidl(a1, 0, *(LPCITEMIDLIST *)(WindowLongPtrW + 104), v9, "undelete") )
      {
        v11 = GetDlgItem(a1, 12323);
        EnableWindow(v11, 0);
      }
      return 0;
    }
LABEL_36:
    RelayMessageToChildren(a1, a2, a3, a4);
    return 0;
  }
  v20 = *(_DWORD *)(a4 + 16);
  return (unsigned int)(v20 + 202) <= 1 || v20 == -200;
}

```

## disassembly

```asm
0x18039c270  push    rbp
0x18039c272  push    rbx
0x18039c273  push    rsi
0x18039c274  push    rdi
0x18039c275  push    r14
0x18039c277  push    r15
0x18039c279  lea     rbp, [rsp-8B8h]
0x18039c281  sub     rsp, 9B8h
0x18039c288  mov     rax, cs:__security_cookie
0x18039c28f  xor     rax, rsp
0x18039c292  mov     [rbp+8E0h+var_40], rax
0x18039c299  mov     r15d, edx
0x18039c29c  mov     r14, r9
0x18039c29f  mov     edx, 10h; nIndex
0x18039c2a4  mov     rbx, r8
0x18039c2a7  mov     rdi, rcx
0x18039c2aa  call    cs:__imp_GetWindowLongPtrW
0x18039c2b0  mov     ecx, r15d
0x18039c2b3  mov     rsi, rax
0x18039c2b6  sub     ecx, 2
0x18039c2b9  jz      loc_18039C6A3
0x18039c2bf  sub     ecx, 13h
0x18039c2c2  jz      loc_18039C690
0x18039c2c8  sub     ecx, 5
0x18039c2cb  jz      loc_18039C690
0x18039c2d1  sub     ecx, 34h ; '4'
0x18039c2d4  jz      loc_18039C668
0x18039c2da  sub     ecx, 30h ; '0'
0x18039c2dd  jz      loc_18039C690
0x18039c2e3  sub     ecx, 92h
0x18039c2e9  jz      short loc_18039C342
0x18039c2eb  cmp     ecx, 1
0x18039c2ee  jnz     loc_18039C6DE
0x18039c2f4  mov     r14d, 3023h
0x18039c2fa  cmp     bx, r14w
0x18039c2fe  jnz     loc_18039C6DE
0x18039c304  mov     r8, [rsi+68h]; pidl
0x18039c308  lea     rax, aUndelete_0; "undelete"
0x18039c30f  xor     edx, edx; dwAttrb
0x18039c311  mov     qword ptr [rsp+9E0h+uFlags], rax; char *
0x18039c316  mov     rcx, rdi; pszPath
0x18039c319  call    ?SHInvokeCommandOnPidl@@YAJPEAUHWND__@@PEAUIUnknown@@PEBU_ITEMIDLIST_ABSOLUTE@@IPEBD@Z; SHInvokeCommandOnPidl(HWND__ *,IUnknown *,_ITEMIDLIST_ABSOLUTE const *,uint,char const *)
0x18039c31e  test    eax, eax
0x18039c320  jnz     loc_18039C6DE
0x18039c326  mov     edx, r14d; nIDDlgItem
0x18039c329  mov     rcx, rdi; hDlg
0x18039c32c  call    cs:__imp_GetDlgItem
0x18039c332  mov     rcx, rax; hWnd
0x18039c335  xor     edx, edx; bEnable
0x18039c337  call    cs:__imp_EnableWindow
0x18039c33d  jmp     loc_18039C6DE
0x18039c342  mov     r8, r14; dwNewLong
0x18039c345  mov     edx, 10h; nIndex
0x18039c34a  mov     rcx, rdi; hWnd
0x18039c34d  call    cs:__imp_SetWindowLongPtrW
0x18039c353  mov     ebx, 2B8h
0x18039c358  lea     rcx, [rsp+9E0h+psfi]; void *
0x18039c35d  mov     r8d, ebx; Size
0x18039c360  xor     edx, edx; Val
0x18039c362  call    memset_0
0x18039c367  mov     rcx, [r14+68h]; pszPath
0x18039c36b  lea     r8, [rsp+9E0h+psfi]; psfi
0x18039c370  mov     r9d, ebx; cbFileInfo
0x18039c373  mov     [rsp+9E0h+uFlags], 728h; uFlags
0x18039c37b  xor     edx, edx; dwFileAttributes
0x18039c37d  call    cs:__imp_SHGetFileInfoW
0x18039c383  mov     r8, [rsp+9E0h+psfi.hIcon]; HICON
0x18039c388  mov     edx, 3301h; unsigned int
0x18039c38d  mov     rcx, rdi; HWND
0x18039c390  call    ?ReplaceDlgIcon@@YAXPEAUHWND__@@IPEAUHICON__@@@Z; ReplaceDlgIcon(HWND__ *,uint,HICON__ *)
0x18039c395  lea     r8, [rbp+8E0h+psfi.szTypeName]; lpString
0x18039c39c  mov     edx, 3303h; nIDDlgItem
0x18039c3a1  mov     rcx, rdi; hDlg
0x18039c3a4  call    cs:__imp_SetDlgItemTextW
0x18039c3aa  mov     r8, [r14+80h]; unsigned __int16 *
0x18039c3b1  lea     rcx, [rbp+8E0h+pszPath]; unsigned __int16 *
0x18039c3b8  mov     r15d, 104h
0x18039c3be  mov     edx, r15d; unsigned __int64
0x18039c3c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18039c3c6  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x18039c3cd  call    cs:__imp_PathRemoveExtensionW
0x18039c3d3  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x18039c3da  call    cs:__imp_PathFindFileNameW
0x18039c3e0  mov     edx, 66h ; 'f'; nIDDlgItem
0x18039c3e5  mov     rcx, rdi; hDlg
0x18039c3e8  mov     r8, rax; lpString
0x18039c3eb  call    cs:__imp_SetDlgItemTextW
0x18039c3f1  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x18039c3f8  call    cs:__imp_PathRemoveFileSpecW
0x18039c3fe  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x18039c405  call    cs:__imp_PathFindFileNameW
0x18039c40b  mov     edx, 3309h; nIDDlgItem
0x18039c410  mov     rcx, rdi; hDlg
0x18039c413  mov     r8, rax; lpString
0x18039c416  call    cs:__imp_SetDlgItemTextW
0x18039c41c  lea     r8, [r14+70h]; pft
0x18039c420  mov     edx, 3317h; nIDDlgItem
0x18039c425  mov     r9d, 0Ch
0x18039c42b  mov     rcx, rdi; hDlg
0x18039c42e  call    SetDateTimeTextEx
0x18039c433  mov     rcx, [r14+78h]; qdw
0x18039c437  lea     rdx, [rbp+8E0h+pszPath]; pszBuf
0x18039c43e  mov     r8d, r15d; cchBuf
0x18039c441  call    cs:__imp_StrFormatByteSizeW
0x18039c447  lea     r8, [rbp+8E0h+pszPath]; lpString
0x18039c44e  mov     edx, 3308h; nIDDlgItem
0x18039c453  mov     rcx, rdi; hDlg
0x18039c456  call    cs:__imp_SetDlgItemTextW
0x18039c45c  mov     rcx, [r14+68h]; pidl
0x18039c460  lea     rdx, [rbp+8E0h+pszPath]; pszPath
0x18039c467  call    cs:__imp_SHGetPathFromIDListW
0x18039c46d  xor     ebx, ebx
0x18039c46f  test    eax, eax
0x18039c471  jz      loc_18039C629
0x18039c477  xor     edx, edx; Val
0x18039c479  lea     rcx, [rbp+8E0h+FindFileData]; void *
0x18039c480  mov     r8d, 250h; Size
0x18039c486  call    memset_0
0x18039c48b  lea     rdx, [rbp+8E0h+FindFileData]; lpFindFileData
0x18039c492  lea     rcx, [rbp+8E0h+pszPath]; lpFileName
0x18039c499  call    cs:__imp_FindFirstFileW
0x18039c49f  mov     rsi, rax
0x18039c4a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18039c4a6  jz      loc_18039C629
0x18039c4ac  lea     r9d, [rbx+0Ch]
0x18039c4b0  mov     edx, 3310h; nIDDlgItem
0x18039c4b5  lea     r8, [rbp+8E0h+FindFileData.ftCreationTime]; pft
0x18039c4bc  mov     rcx, rdi; hDlg
0x18039c4bf  call    SetDateTimeTextEx
0x18039c4c4  mov     rcx, rsi; hFindFile
0x18039c4c7  call    cs:__imp_FindClose
0x18039c4cd  lea     r8, [rbp+8E0h+pszPath]; unsigned __int16 *
0x18039c4d4  mov     edx, r15d; unsigned __int64
0x18039c4d7  lea     rcx, [rbp+8E0h+RootPathName]; unsigned __int16 *
0x18039c4de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18039c4e3  lea     rcx, [rbp+8E0h+RootPathName]; pszPath
0x18039c4ea  call    cs:__imp_PathStripToRootW
0x18039c4f0  mov     edx, r15d; cchPath
0x18039c4f3  lea     rcx, [rbp+8E0h+RootPathName]; pszPath
0x18039c4fa  call    cs:__imp_PathCchAddBackslash
0x18039c500  mov     [rsp+9E0h+nFileSystemNameSize], 0Ch; nFileSystemNameSize
0x18039c508  lea     rax, [rbp+8E0h+FileSystemNameBuffer]
0x18039c50f  mov     [rsp+9E0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18039c514  lea     rcx, [rbp+8E0h+RootPathName]; lpRootPathName
0x18039c51b  lea     rax, [rbp+8E0h+FileSystemFlags]
0x18039c522  mov     [rbp+8E0h+FileSystemFlags], ebx
0x18039c528  mov     [rsp+9E0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18039c52d  xor     r9d, r9d; lpVolumeSerialNumber
0x18039c530  xor     r8d, r8d; nVolumeNameSize
0x18039c533  mov     qword ptr [rsp+9E0h+uFlags], rbx; lpMaximumComponentLength
0x18039c538  xor     edx, edx; lpVolumeNameBuffer
0x18039c53a  call    cs:__imp_GetVolumeInformationW
0x18039c540  lea     esi, [rbx+1]
0x18039c543  test    eax, eax
0x18039c545  jz      loc_18039C5D7
0x18039c54b  mov     eax, [rbp+8E0h+FileSystemFlags]
0x18039c551  test    al, 10h
0x18039c553  jz      short loc_18039C596
0x18039c555  test    [rbp+8E0h+FindFileData.dwFileAttributes], 800h
0x18039c55f  mov     r15d, 3331h
0x18039c565  jz      short loc_18039C576
0x18039c567  mov     r8d, esi; uCheck
0x18039c56a  mov     edx, r15d; nIDButton
0x18039c56d  mov     rcx, rdi; hDlg
0x18039c570  call    cs:__imp_CheckDlgButton
0x18039c576  mov     edx, r15d; nIDDlgItem
0x18039c579  mov     rcx, rdi; hDlg
0x18039c57c  call    cs:__imp_GetDlgItem
0x18039c582  mov     rcx, rax; hWnd
0x18039c585  mov     edx, 5; nCmdShow
0x18039c58a  call    cs:__imp_ShowWindow
0x18039c590  mov     eax, [rbp+8E0h+FileSystemFlags]
0x18039c596  bt      eax, 11h
0x18039c59a  jnb     short loc_18039C5D7
0x18039c59c  test    [rbp+8E0h+FindFileData.dwFileAttributes], 4000h
0x18039c5a6  mov     r15d, 3367h
0x18039c5ac  jz      short loc_18039C5BD
0x18039c5ae  mov     r8d, esi; uCheck
0x18039c5b1  mov     edx, r15d; nIDButton
0x18039c5b4  mov     rcx, rdi; hDlg
0x18039c5b7  call    cs:__imp_CheckDlgButton
0x18039c5bd  mov     edx, r15d; nIDDlgItem
0x18039c5c0  mov     rcx, rdi; hDlg
0x18039c5c3  call    cs:__imp_GetDlgItem
0x18039c5c9  mov     rcx, rax; hWnd
0x18039c5cc  mov     edx, 5; nCmdShow
0x18039c5d1  call    cs:__imp_ShowWindow
0x18039c5d7  mov     eax, [rbp+8E0h+FindFileData.dwFileAttributes]
0x18039c5dd  test    sil, al
0x18039c5e0  jz      short loc_18039C5F9
0x18039c5e2  mov     r8d, esi; uCheck
0x18039c5e5  mov     edx, 3313h; nIDButton
0x18039c5ea  mov     rcx, rdi; hDlg
0x18039c5ed  call    cs:__imp_CheckDlgButton
0x18039c5f3  mov     eax, [rbp+8E0h+FindFileData.dwFileAttributes]
0x18039c5f9  test    al, 20h
0x18039c5fb  jz      short loc_18039C614
0x18039c5fd  mov     r8d, esi; uCheck
0x18039c600  mov     edx, 3315h; nIDButton
0x18039c605  mov     rcx, rdi; hDlg
0x18039c608  call    cs:__imp_CheckDlgButton
0x18039c60e  mov     eax, [rbp+8E0h+FindFileData.dwFileAttributes]
0x18039c614  test    al, 2
0x18039c616  jz      short loc_18039C629
0x18039c618  mov     r8d, esi; uCheck
0x18039c61b  mov     edx, 3314h; nIDButton
0x18039c620  mov     rcx, rdi; hDlg
0x18039c623  call    cs:__imp_CheckDlgButton
0x18039c629  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18039c630  mov     ecx, 10h; unsigned __int64
0x18039c635  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18039c63a  test    rax, rax
0x18039c63d  jz      short loc_18039C648
0x18039c63f  mov     [rax], rbx
0x18039c642  mov     [rax+8], rbx
0x18039c646  jmp     short loc_18039C64B
0x18039c648  mov     rax, rbx
0x18039c64b  mov     [r14+88h], rax
0x18039c652  test    rax, rax
0x18039c655  jz      loc_18039C6DE
0x18039c65b  mov     rdx, rdi; HWND
0x18039c65e  mov     rcx, rax; this
0x18039c661  call    ?MakeAllLinesAndIconsInvisibleToNarrator@PropSheetAccAnnotation@@QEAAXPEAUHWND__@@@Z; PropSheetAccAnnotation::MakeAllLinesAndIconsInvisibleToNarrator(HWND__ *)
0x18039c666  jmp     short loc_18039C6DE
0x18039c668  mov     ecx, [r14+10h]
0x18039c66c  mov     esi, 1
0x18039c671  lea     eax, [rcx+0CAh]
0x18039c677  cmp     eax, esi
0x18039c679  jbe     short loc_18039C68B
0x18039c67b  xor     ebx, ebx
0x18039c67d  cmp     ecx, 0FFFFFF38h
0x18039c683  setz    bl
0x18039c686  mov     rax, rbx
0x18039c689  jmp     short loc_18039C6E0
0x18039c68b  mov     rax, rsi
0x18039c68e  jmp     short loc_18039C6E0
0x18039c690  mov     r9, r14
0x18039c693  mov     r8, rbx
0x18039c696  mov     edx, r15d
0x18039c699  mov     rcx, rdi
0x18039c69c  call    RelayMessageToChildren
0x18039c6a1  jmp     short loc_18039C6DE
0x18039c6a3  xor     r8d, r8d; HICON
0x18039c6a6  mov     edx, 3301h; unsigned int
0x18039c6ab  mov     rcx, rdi; HWND
0x18039c6ae  call    ?ReplaceDlgIcon@@YAXPEAUHWND__@@IPEAUHICON__@@@Z; ReplaceDlgIcon(HWND__ *,uint,HICON__ *)
0x18039c6b3  mov     rcx, [rsi+88h]; this
0x18039c6ba  xor     ebx, ebx
0x18039c6bc  test    rcx, rcx
0x18039c6bf  jz      short loc_18039C6DE
0x18039c6c1  call    ?ClearAllHwndAccProperties@PropSheetAccAnnotation@@QEAAXXZ; PropSheetAccAnnotation::ClearAllHwndAccProperties(void)
0x18039c6c6  mov     rcx, [rsi+88h]; this
0x18039c6cd  test    rcx, rcx
0x18039c6d0  jz      short loc_18039C6D7
0x18039c6d2  call    ??_GPropSheetAccAnnotation@@QEAAPEAXI@Z; PropSheetAccAnnotation::`scalar deleting destructor'(uint)
0x18039c6d7  mov     [rsi+88h], rbx
0x18039c6de  xor     eax, eax
0x18039c6e0  mov     rcx, [rbp+8E0h+var_40]
0x18039c6e7  xor     rcx, rsp; StackCookie
0x18039c6ea  call    __security_check_cookie
0x18039c6ef  add     rsp, 9B8h
0x18039c6f6  pop     r15
0x18039c6f8  pop     r14
0x18039c6fa  pop     rdi
0x18039c6fb  pop     rsi
0x18039c6fc  pop     rbx
0x18039c6fd  pop     rbp
0x18039c6fe  retn
```
