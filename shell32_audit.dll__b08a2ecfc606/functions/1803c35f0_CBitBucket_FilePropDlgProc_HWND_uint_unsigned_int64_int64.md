# CBitBucket::_FilePropDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1803c35f0`
- end: `0x1803c3b2e`
- name: `?_FilePropDlgProc@CBitBucket@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1342`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18001aae0`
- `0x1801ee8c4`
- `0x180249490`
- `0x18024999c`
- `0x18024a53c`
- `0x180268584`
- `0x1802bc988`
- `0x1802c011c`
- `0x180307a1c`
- `0x18039071c`
- `0x1803c35f0`
- `0x1803c4894`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1803c392c`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1803c392c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1803c3873`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1803c3873`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1803c38a7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1803c38a7`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1803c38e6`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1803c38e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1803c3784`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1803c37c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1803c3784`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1803c37c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1803c3771`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1803c3771`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1803c38d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1803c38d0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1803c37ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1803c37ae`
- `USER32!EnableWindow` at `0x1803c36c3`
- `USER32!EnableWindow` at `0x1803c36c3`
- `USER32!CheckDlgButton` at `0x1803c3968`
- `USER32!CheckDlgButton` at `0x1803c39c1`
- `USER32!CheckDlgButton` at `0x1803c3a09`
- `USER32!CheckDlgButton` at `0x1803c3a2a`
- `USER32!CheckDlgButton` at `0x1803c3a4b`
- `USER32!CheckDlgButton` at `0x1803c3968`
- `USER32!CheckDlgButton` at `0x1803c39c1`
- `USER32!CheckDlgButton` at `0x1803c3a09`
- `USER32!CheckDlgButton` at `0x1803c3a2a`
- `USER32!CheckDlgButton` at `0x1803c3a4b`
- `USER32!GetWindowLongPtrW` at `0x1803c362a`
- `USER32!GetWindowLongPtrW` at `0x1803c362a`
- `USER32!SetWindowLongPtrW` at `0x1803c36df`
- `USER32!SetWindowLongPtrW` at `0x1803c36df`
- `USER32!ShowWindow` at `0x1803c398e`
- `USER32!ShowWindow` at `0x1803c39e7`
- `USER32!ShowWindow` at `0x1803c398e`
- `USER32!ShowWindow` at `0x1803c39e7`
- `USER32!GetDlgItem` at `0x1803c36b2`
- `USER32!GetDlgItem` at `0x1803c397a`
- `USER32!GetDlgItem` at `0x1803c39d3`
- `USER32!GetDlgItem` at `0x1803c36b2`
- `USER32!GetDlgItem` at `0x1803c397a`
- `USER32!GetDlgItem` at `0x1803c39d3`
- `USER32!SetDlgItemTextW` at `0x1803c3742`
- `USER32!SetDlgItemTextW` at `0x1803c379b`
- `USER32!SetDlgItemTextW` at `0x1803c37d8`
- `USER32!SetDlgItemTextW` at `0x1803c3824`
- `USER32!SetDlgItemTextW` at `0x1803c3742`
- `USER32!SetDlgItemTextW` at `0x1803c379b`
- `USER32!SetDlgItemTextW` at `0x1803c37d8`
- `USER32!SetDlgItemTextW` at `0x1803c3824`
- `SHLWAPI!StrFormatByteSizeW` at `0x1803c3809`
- `SHLWAPI!StrFormatByteSizeW` at `0x1803c3809`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFileInfoW` at `0x1803c3715`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetFileInfoW` at `0x1803c3715`
- `Windows.Storage!SHGetPathFromIDListW` at `0x1803c383b`
- `Windows.Storage!SHGetPathFromIDListW` at `0x1803c383b`

## string_xrefs

- `0x1803c368e`: `undelete`

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
0x1803c35f0  push    rbp
0x1803c35f2  push    rbx
0x1803c35f3  push    rsi
0x1803c35f4  push    rdi
0x1803c35f5  push    r14
0x1803c35f7  push    r15
0x1803c35f9  lea     rbp, [rsp-8B8h]
0x1803c3601  sub     rsp, 9B8h
0x1803c3608  mov     rax, cs:__security_cookie
0x1803c360f  xor     rax, rsp
0x1803c3612  mov     [rbp+8E0h+var_40], rax
0x1803c3619  mov     r15d, edx
0x1803c361c  mov     r14, r9
0x1803c361f  mov     edx, 10h; nIndex
0x1803c3624  mov     rbx, r8
0x1803c3627  mov     rdi, rcx
0x1803c362a  call    cs:__imp_GetWindowLongPtrW
0x1803c3631  nop     dword ptr [rax+rax+00h]
0x1803c3636  mov     ecx, r15d
0x1803c3639  mov     rsi, rax
0x1803c363c  sub     ecx, 2
0x1803c363f  jz      loc_1803C3AD1
0x1803c3645  sub     ecx, 13h
0x1803c3648  jz      loc_1803C3ABE
0x1803c364e  sub     ecx, 5
0x1803c3651  jz      loc_1803C3ABE
0x1803c3657  sub     ecx, 34h ; '4'
0x1803c365a  jz      loc_1803C3A96
0x1803c3660  sub     ecx, 30h ; '0'
0x1803c3663  jz      loc_1803C3ABE
0x1803c3669  sub     ecx, 92h
0x1803c366f  jz      short loc_1803C36D4
0x1803c3671  cmp     ecx, 1
0x1803c3674  jnz     loc_1803C3B0C
0x1803c367a  mov     r14d, 3023h
0x1803c3680  cmp     bx, r14w
0x1803c3684  jnz     loc_1803C3B0C
0x1803c368a  mov     r8, [rsi+68h]; pidl
0x1803c368e  lea     rax, aUndelete_0; "undelete"
0x1803c3695  xor     edx, edx; dwAttrb
0x1803c3697  mov     qword ptr [rsp+9E0h+uFlags], rax; char *
0x1803c369c  mov     rcx, rdi; pszPath
0x1803c369f  call    ?SHInvokeCommandOnPidl@@YAJPEAUHWND__@@PEAUIUnknown@@PEBU_ITEMIDLIST_ABSOLUTE@@IPEBD@Z; SHInvokeCommandOnPidl(HWND__ *,IUnknown *,_ITEMIDLIST_ABSOLUTE const *,uint,char const *)
0x1803c36a4  test    eax, eax
0x1803c36a6  jnz     loc_1803C3B0C
0x1803c36ac  mov     edx, r14d; nIDDlgItem
0x1803c36af  mov     rcx, rdi; hDlg
0x1803c36b2  call    cs:__imp_GetDlgItem
0x1803c36b9  nop     dword ptr [rax+rax+00h]
0x1803c36be  mov     rcx, rax; hWnd
0x1803c36c1  xor     edx, edx; bEnable
0x1803c36c3  call    cs:__imp_EnableWindow
0x1803c36ca  nop     dword ptr [rax+rax+00h]
0x1803c36cf  jmp     loc_1803C3B0C
0x1803c36d4  mov     r8, r14; dwNewLong
0x1803c36d7  mov     edx, 10h; nIndex
0x1803c36dc  mov     rcx, rdi; hWnd
0x1803c36df  call    cs:__imp_SetWindowLongPtrW
0x1803c36e6  nop     dword ptr [rax+rax+00h]
0x1803c36eb  mov     ebx, 2B8h
0x1803c36f0  lea     rcx, [rsp+9E0h+psfi]; void *
0x1803c36f5  mov     r8d, ebx; Size
0x1803c36f8  xor     edx, edx; Val
0x1803c36fa  call    memset_0
0x1803c36ff  mov     rcx, [r14+68h]; pszPath
0x1803c3703  lea     r8, [rsp+9E0h+psfi]; psfi
0x1803c3708  mov     r9d, ebx; cbFileInfo
0x1803c370b  mov     [rsp+9E0h+uFlags], 728h; uFlags
0x1803c3713  xor     edx, edx; dwFileAttributes
0x1803c3715  call    cs:__imp_SHGetFileInfoW
0x1803c371c  nop     dword ptr [rax+rax+00h]
0x1803c3721  mov     r8, [rsp+9E0h+psfi.hIcon]; HICON
0x1803c3726  mov     edx, 3301h; unsigned int
0x1803c372b  mov     rcx, rdi; HWND
0x1803c372e  call    ?ReplaceDlgIcon@@YAXPEAUHWND__@@IPEAUHICON__@@@Z; ReplaceDlgIcon(HWND__ *,uint,HICON__ *)
0x1803c3733  lea     r8, [rbp+8E0h+psfi.szTypeName]; lpString
0x1803c373a  mov     edx, 3303h; nIDDlgItem
0x1803c373f  mov     rcx, rdi; hDlg
0x1803c3742  call    cs:__imp_SetDlgItemTextW
0x1803c3749  nop     dword ptr [rax+rax+00h]
0x1803c374e  mov     r8, [r14+80h]; unsigned __int16 *
0x1803c3755  lea     rcx, [rbp+8E0h+pszPath]; unsigned __int16 *
0x1803c375c  mov     r15d, 104h
0x1803c3762  mov     edx, r15d; unsigned __int64
0x1803c3765  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803c376a  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x1803c3771  call    cs:__imp_PathRemoveExtensionW
0x1803c3778  nop     dword ptr [rax+rax+00h]
0x1803c377d  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x1803c3784  call    cs:__imp_PathFindFileNameW
0x1803c378b  nop     dword ptr [rax+rax+00h]
0x1803c3790  mov     edx, 66h ; 'f'; nIDDlgItem
0x1803c3795  mov     rcx, rdi; hDlg
0x1803c3798  mov     r8, rax; lpString
0x1803c379b  call    cs:__imp_SetDlgItemTextW
0x1803c37a2  nop     dword ptr [rax+rax+00h]
0x1803c37a7  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x1803c37ae  call    cs:__imp_PathRemoveFileSpecW
0x1803c37b5  nop     dword ptr [rax+rax+00h]
0x1803c37ba  lea     rcx, [rbp+8E0h+pszPath]; pszPath
0x1803c37c1  call    cs:__imp_PathFindFileNameW
0x1803c37c8  nop     dword ptr [rax+rax+00h]
0x1803c37cd  mov     edx, 3309h; nIDDlgItem
0x1803c37d2  mov     rcx, rdi; hDlg
0x1803c37d5  mov     r8, rax; lpString
0x1803c37d8  call    cs:__imp_SetDlgItemTextW
0x1803c37df  nop     dword ptr [rax+rax+00h]
0x1803c37e4  lea     r8, [r14+70h]; pft
0x1803c37e8  mov     edx, 3317h; nIDDlgItem
0x1803c37ed  mov     r9d, 0Ch
0x1803c37f3  mov     rcx, rdi; hDlg
0x1803c37f6  call    SetDateTimeTextEx
0x1803c37fb  mov     rcx, [r14+78h]; qdw
0x1803c37ff  lea     rdx, [rbp+8E0h+pszPath]; pszBuf
0x1803c3806  mov     r8d, r15d; cchBuf
0x1803c3809  call    cs:__imp_StrFormatByteSizeW
0x1803c3810  nop     dword ptr [rax+rax+00h]
0x1803c3815  lea     r8, [rbp+8E0h+pszPath]; lpString
0x1803c381c  mov     edx, 3308h; nIDDlgItem
0x1803c3821  mov     rcx, rdi; hDlg
0x1803c3824  call    cs:__imp_SetDlgItemTextW
0x1803c382b  nop     dword ptr [rax+rax+00h]
0x1803c3830  mov     rcx, [r14+68h]; pidl
0x1803c3834  lea     rdx, [rbp+8E0h+pszPath]; pszPath
0x1803c383b  call    cs:__imp_SHGetPathFromIDListW
0x1803c3842  nop     dword ptr [rax+rax+00h]
0x1803c3847  xor     ebx, ebx
0x1803c3849  test    eax, eax
0x1803c384b  jz      loc_1803C3A57
0x1803c3851  xor     edx, edx; Val
0x1803c3853  lea     rcx, [rbp+8E0h+FindFileData]; void *
0x1803c385a  mov     r8d, 250h; Size
0x1803c3860  call    memset_0
0x1803c3865  lea     rdx, [rbp+8E0h+FindFileData]; lpFindFileData
0x1803c386c  lea     rcx, [rbp+8E0h+pszPath]; lpFileName
0x1803c3873  call    cs:__imp_FindFirstFileW
0x1803c387a  nop     dword ptr [rax+rax+00h]
0x1803c387f  mov     rsi, rax
0x1803c3882  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1803c3886  jz      loc_1803C3A57
0x1803c388c  lea     r9d, [rbx+0Ch]
0x1803c3890  mov     edx, 3310h; nIDDlgItem
0x1803c3895  lea     r8, [rbp+8E0h+FindFileData.ftCreationTime]; pft
0x1803c389c  mov     rcx, rdi; hDlg
0x1803c389f  call    SetDateTimeTextEx
0x1803c38a4  mov     rcx, rsi; hFindFile
0x1803c38a7  call    cs:__imp_FindClose
0x1803c38ae  nop     dword ptr [rax+rax+00h]
0x1803c38b3  lea     r8, [rbp+8E0h+pszPath]; unsigned __int16 *
0x1803c38ba  mov     edx, r15d; unsigned __int64
0x1803c38bd  lea     rcx, [rbp+8E0h+RootPathName]; unsigned __int16 *
0x1803c38c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803c38c9  lea     rcx, [rbp+8E0h+RootPathName]; pszPath
0x1803c38d0  call    cs:__imp_PathStripToRootW
0x1803c38d7  nop     dword ptr [rax+rax+00h]
0x1803c38dc  mov     edx, r15d; cchPath
0x1803c38df  lea     rcx, [rbp+8E0h+RootPathName]; pszPath
0x1803c38e6  call    cs:__imp_PathCchAddBackslash
0x1803c38ed  nop     dword ptr [rax+rax+00h]
0x1803c38f2  mov     [rsp+9E0h+nFileSystemNameSize], 0Ch; nFileSystemNameSize
0x1803c38fa  lea     rax, [rbp+8E0h+FileSystemNameBuffer]
0x1803c3901  mov     [rsp+9E0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x1803c3906  lea     rcx, [rbp+8E0h+RootPathName]; lpRootPathName
0x1803c390d  lea     rax, [rbp+8E0h+FileSystemFlags]
0x1803c3914  mov     [rbp+8E0h+FileSystemFlags], ebx
0x1803c391a  mov     [rsp+9E0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1803c391f  xor     r9d, r9d; lpVolumeSerialNumber
0x1803c3922  xor     r8d, r8d; nVolumeNameSize
0x1803c3925  mov     qword ptr [rsp+9E0h+uFlags], rbx; lpMaximumComponentLength
0x1803c392a  xor     edx, edx; lpVolumeNameBuffer
0x1803c392c  call    cs:__imp_GetVolumeInformationW
0x1803c3933  nop     dword ptr [rax+rax+00h]
0x1803c3938  lea     esi, [rbx+1]
0x1803c393b  test    eax, eax
0x1803c393d  jz      loc_1803C39F3
0x1803c3943  mov     eax, [rbp+8E0h+FileSystemFlags]
0x1803c3949  test    al, 10h
0x1803c394b  jz      short loc_1803C39A0
0x1803c394d  test    [rbp+8E0h+FindFileData.dwFileAttributes], 800h
0x1803c3957  mov     r15d, 3331h
0x1803c395d  jz      short loc_1803C3974
0x1803c395f  mov     r8d, esi; uCheck
0x1803c3962  mov     edx, r15d; nIDButton
0x1803c3965  mov     rcx, rdi; hDlg
0x1803c3968  call    cs:__imp_CheckDlgButton
0x1803c396f  nop     dword ptr [rax+rax+00h]
0x1803c3974  mov     edx, r15d; nIDDlgItem
0x1803c3977  mov     rcx, rdi; hDlg
0x1803c397a  call    cs:__imp_GetDlgItem
0x1803c3981  nop     dword ptr [rax+rax+00h]
0x1803c3986  mov     rcx, rax; hWnd
0x1803c3989  mov     edx, 5; nCmdShow
0x1803c398e  call    cs:__imp_ShowWindow
0x1803c3995  nop     dword ptr [rax+rax+00h]
0x1803c399a  mov     eax, [rbp+8E0h+FileSystemFlags]
0x1803c39a0  bt      eax, 11h
0x1803c39a4  jnb     short loc_1803C39F3
0x1803c39a6  test    [rbp+8E0h+FindFileData.dwFileAttributes], 4000h
0x1803c39b0  mov     r15d, 3367h
0x1803c39b6  jz      short loc_1803C39CD
0x1803c39b8  mov     r8d, esi; uCheck
0x1803c39bb  mov     edx, r15d; nIDButton
0x1803c39be  mov     rcx, rdi; hDlg
0x1803c39c1  call    cs:__imp_CheckDlgButton
0x1803c39c8  nop     dword ptr [rax+rax+00h]
0x1803c39cd  mov     edx, r15d; nIDDlgItem
0x1803c39d0  mov     rcx, rdi; hDlg
0x1803c39d3  call    cs:__imp_GetDlgItem
0x1803c39da  nop     dword ptr [rax+rax+00h]
0x1803c39df  mov     rcx, rax; hWnd
0x1803c39e2  mov     edx, 5; nCmdShow
0x1803c39e7  call    cs:__imp_ShowWindow
0x1803c39ee  nop     dword ptr [rax+rax+00h]
0x1803c39f3  mov     eax, [rbp+8E0h+FindFileData.dwFileAttributes]
0x1803c39f9  test    sil, al
0x1803c39fc  jz      short loc_1803C3A1B
0x1803c39fe  mov     r8d, esi; uCheck
0x1803c3a01  mov     edx, 3313h; nIDButton
0x1803c3a06  mov     rcx, rdi; hDlg
0x1803c3a09  call    cs:__imp_CheckDlgButton
0x1803c3a10  nop     dword ptr [rax+rax+00h]
0x1803c3a15  mov     eax, [rbp+8E0h+FindFileData.dwFileAttributes]
0x1803c3a1b  test    al, 20h
0x1803c3a1d  jz      short loc_1803C3A3C
0x1803c3a1f  mov     r8d, esi; uCheck
0x1803c3a22  mov     edx, 3315h; nIDButton
0x1803c3a27  mov     rcx, rdi; hDlg
0x1803c3a2a  call    cs:__imp_CheckDlgButton
0x1803c3a31  nop     dword ptr [rax+rax+00h]
0x1803c3a36  mov     eax, [rbp+8E0h+FindFileData.dwFileAttributes]
0x1803c3a3c  test    al, 2
0x1803c3a3e  jz      short loc_1803C3A57
0x1803c3a40  mov     r8d, esi; uCheck
0x1803c3a43  mov     edx, 3314h; nIDButton
0x1803c3a48  mov     rcx, rdi; hDlg
0x1803c3a4b  call    cs:__imp_CheckDlgButton
0x1803c3a52  nop     dword ptr [rax+rax+00h]
0x1803c3a57  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1803c3a5e  mov     ecx, 10h; unsigned __int64
0x1803c3a63  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1803c3a68  test    rax, rax
0x1803c3a6b  jz      short loc_1803C3A76
0x1803c3a6d  mov     [rax], rbx
0x1803c3a70  mov     [rax+8], rbx
0x1803c3a74  jmp     short loc_1803C3A79
0x1803c3a76  mov     rax, rbx
0x1803c3a79  mov     [r14+88h], rax
0x1803c3a80  test    rax, rax
0x1803c3a83  jz      loc_1803C3B0C
0x1803c3a89  mov     rdx, rdi; HWND
0x1803c3a8c  mov     rcx, rax; this
0x1803c3a8f  call    ?MakeAllLinesAndIconsInvisibleToNarrator@PropSheetAccAnnotation@@QEAAXPEAUHWND__@@@Z; PropSheetAccAnnotation::MakeAllLinesAndIconsInvisibleToNarrator(HWND__ *)
0x1803c3a94  jmp     short loc_1803C3B0C
0x1803c3a96  mov     ecx, [r14+10h]
0x1803c3a9a  mov     esi, 1
0x1803c3a9f  lea     eax, [rcx+0CAh]
0x1803c3aa5  cmp     eax, esi
0x1803c3aa7  jbe     short loc_1803C3AB9
0x1803c3aa9  xor     ebx, ebx
0x1803c3aab  cmp     ecx, 0FFFFFF38h
0x1803c3ab1  setz    bl
0x1803c3ab4  mov     rax, rbx
0x1803c3ab7  jmp     short loc_1803C3B0E
0x1803c3ab9  mov     rax, rsi
0x1803c3abc  jmp     short loc_1803C3B0E
0x1803c3abe  mov     r9, r14
0x1803c3ac1  mov     r8, rbx
0x1803c3ac4  mov     edx, r15d
0x1803c3ac7  mov     rcx, rdi
0x1803c3aca  call    RelayMessageToChildren
0x1803c3acf  jmp     short loc_1803C3B0C
0x1803c3ad1  xor     r8d, r8d; HICON
0x1803c3ad4  mov     edx, 3301h; unsigned int
0x1803c3ad9  mov     rcx, rdi; HWND
0x1803c3adc  call    ?ReplaceDlgIcon@@YAXPEAUHWND__@@IPEAUHICON__@@@Z; ReplaceDlgIcon(HWND__ *,uint,HICON__ *)
0x1803c3ae1  mov     rcx, [rsi+88h]; this
0x1803c3ae8  xor     ebx, ebx
0x1803c3aea  test    rcx, rcx
0x1803c3aed  jz      short loc_1803C3B0C
0x1803c3aef  call    ?ClearAllHwndAccProperties@PropSheetAccAnnotation@@QEAAXXZ; PropSheetAccAnnotation::ClearAllHwndAccProperties(void)
0x1803c3af4  mov     rcx, [rsi+88h]; this
0x1803c3afb  test    rcx, rcx
0x1803c3afe  jz      short loc_1803C3B05
0x1803c3b00  call    ??_GPropSheetAccAnnotation@@QEAAPEAXI@Z; PropSheetAccAnnotation::`scalar deleting destructor'(uint)
0x1803c3b05  mov     [rsi+88h], rbx
0x1803c3b0c  xor     eax, eax
0x1803c3b0e  mov     rcx, [rbp+8E0h+var_40]
0x1803c3b15  xor     rcx, rsp; StackCookie
0x1803c3b18  call    __security_check_cookie
0x1803c3b1d  add     rsp, 9B8h
0x1803c3b24  pop     r15
0x1803c3b26  pop     r14
0x1803c3b28  pop     rdi
0x1803c3b29  pop     rsi
0x1803c3b2a  pop     rbx
0x1803c3b2b  pop     rbp
0x1803c3b2c  retn
```
