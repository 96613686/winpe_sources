# CThemePackManager::InstallThemePack(ushort const *,ushort const *,THEMEPACK_FLAGS,ITheme *)

- ea: `0x180062f3c`
- end: `0x180063541`
- name: `?InstallThemePack@CThemePackManager@@QEAAJPEBG0W4THEMEPACK_FLAGS@@PEAUITheme@@@Z`
- size: `1541`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800547c0`

## callees

- `0x18000ab10`
- `0x1800179e0`
- `0x180030dac`
- `0x180030f64`
- `0x1800358c0`
- `0x180062f3c`
- `0x180063708`
- `0x180063ad4`
- `0x180063de0`
- `0x180064a38`
- `0x180065038`
- `0x1800654b4`
- `0x180065ab8`
- `0x18006791c`
- `0x180067990`
- `0x1800679e4`
- `0x180067b38`
- `0x180068760`
- `0x180068804`
- `0x180068978`
- `0x180068a1c`
- `0x180068f98`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1800631d3`
- `SHLWAPI!PathFindFileNameW` at `0x1800631d3`
- `SHLWAPI!PathFindExtensionW` at `0x18006301f`
- `SHLWAPI!PathFindExtensionW` at `0x18006301f`
- `SHLWAPI!StrTrimW` at `0x180063210`
- `SHLWAPI!StrTrimW` at `0x180063210`
- `SHLWAPI!PathRemoveExtensionW` at `0x1800631fe`
- `SHLWAPI!PathRemoveExtensionW` at `0x1800631fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006303f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006303f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800634af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800634e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800634af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800634e7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006349e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006349e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180063274`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180063274`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063174`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063196`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063253`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063410`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063174`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063196`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063253`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180063410`

## pseudocode

```c
__int64 __fastcall CThemePackManager::InstallThemePack(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        struct ITheme *a5)
{
  CabReader *v8; // r12
  HRESULT FileList; // ebx
  HDPA **v10; // r15
  HDPA *v11; // r12
  _DWORD *v12; // rax
  int v13; // ebx
  int i; // esi
  const WCHAR *Ptr; // rax
  const WCHAR *ExtensionW; // rax
  unsigned __int64 v17; // rdx
  const unsigned __int16 *v18; // rax
  const struct CabReader::FILE_INFO *v19; // rsi
  __int64 j; // r14
  _QWORD *v21; // rsi
  const WCHAR *v22; // r15
  __int64 v23; // rcx
  CThemePackManager *v24; // rcx
  CThemePackManager *v25; // rcx
  HRESULT ThemeFolder; // eax
  const unsigned __int16 *FileNameW; // rax
  unsigned int v28; // r8d
  struct ITheme *v29; // r15
  __int64 v30; // rdx
  int FileBatch; // eax
  __int64 v32; // rax
  void *v33; // rcx
  void *v34; // rcx
  int v35; // eax
  unsigned __int64 v37; // [rsp+28h] [rbp-D8h]
  struct ITheme *v38; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR pszPathOut[264]; // [rsp+460h] [rbp+360h] BYREF

  v38 = a5;
  if ( a2 && a3 )
  {
    v8 = (CabReader *)(a1 + 2232);
    *(_QWORD *)(a1 + 168) = a2;
    FileList = CabReader::OpenCab(a1 + 2232, a2, (a4 & 3) != 0);
    if ( FileList >= 0 )
    {
      v10 = (HDPA **)(a1 + 4384);
      FileList = CabReader::GetFileList(v8);
      if ( FileList >= 0 )
      {
        FileList = CThemePackManager::_InitInCabFileTable(a1, *v10);
        if ( FileList >= 0 )
        {
          v11 = *v10;
          v12 = **v10;
          if ( v12 )
            v13 = *v12;
          else
            v13 = 0;
          for ( i = 0; ; ++i )
          {
            if ( i >= v13 )
              goto LABEL_16;
            Ptr = (const WCHAR *)g_pfn_DPA_GetPtr(*v11, i);
            ExtensionW = PathFindExtensionW(Ptr + 2);
            if ( CompareStringOrdinal(ExtensionW, -1, L".theme", -1, 1) == 2 )
              break;
          }
          FileList = GetTempFile(ExistingFileName, v17);
          if ( FileList < 0 )
          {
LABEL_17:
            v8 = (CabReader *)(a1 + 2232);
            goto LABEL_18;
          }
          v18 = (const unsigned __int16 *)g_pfn_DPA_GetPtr(**v10, i);
          *(_QWORD *)(a1 + 4360) = 0;
          v19 = (const struct CabReader::FILE_INFO *)v18;
          *(_QWORD *)(a1 + 4368) = 0;
          if ( *(_DWORD *)v18 > 0x500000u )
          {
            CThemePackManager::_ShowDialog(a1, 11, a4);
LABEL_16:
            FileList = -2147467259;
            goto LABEL_17;
          }
          v22 = v18 + 2;
          v8 = (CabReader *)(a1 + 2232);
          FileList = CabReader::ExtractFileWithNameOnDisk((CabReader *)(a1 + 2232), v18 + 2, ExistingFileName);
          if ( FileList >= 0 )
          {
            if ( !CThemePackManager::s_IsValidThemeFile(ExistingFileName) )
            {
              CThemePackManager::_ShowDialog(a1, 13, a4);
              FileList = -2147467259;
            }
            if ( FileList >= 0 )
            {
              if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
                McTemplateU0z_EtwEventWriteTransfer(v23, ThemePack_FileUnpacked_Info, v22);
              *((_DWORD *)v19 + 133) = 1;
              *((_DWORD *)v19 + 134) = 1;
              *(_DWORD *)(a1 + 156) = 1;
              *(_QWORD *)(a1 + 160) = *(int *)v19;
              if ( (a4 & 8) != 0 )
              {
                FileList = PathCchCombine(pszPathOut, 0x104u, a3, L"Roamed.theme");
                if ( FileList < 0 )
                  goto LABEL_60;
                if ( PathCchCombine(pszPath, 0x104u, a3, L"RoamedThemeFiles") >= 0 )
                  CThemePackManager::_DeleteThemeFolder(v25, pszPath);
                ThemeFolder = CThemePackManager::_CreateThemeFolder(
                                (CThemePackManager *)a1,
                                a3,
                                L"RoamedThemeFiles",
                                v19,
                                (unsigned __int16 *)(a1 + 4432),
                                v37);
              }
              else
              {
                FileNameW = PathFindFileNameW(v22);
                FileList = StringCchCopyW(pszPath, 0x104u, FileNameW);
                if ( FileList < 0 )
                  goto LABEL_60;
                PathRemoveExtensionW(pszPath);
                StrTrimW(pszPath, L" ");
                FileList = CThemePackManager::_CreateThemeFolder(
                             (CThemePackManager *)a1,
                             a3,
                             pszPath,
                             v19,
                             (unsigned __int16 *)(a1 + 4432),
                             v37);
                if ( FileList < 0 )
                  goto LABEL_60;
                ThemeFolder = PathCchCombine(pszPathOut, 0x104u, (PCWSTR)(a1 + 4432), v22);
              }
              FileList = ThemeFolder;
              if ( ThemeFolder >= 0 )
              {
                if ( CopyFileW(ExistingFileName, pszPathOut, 0)
                  || (FileList = ResultFromKnownLastError(), FileList >= 0) )
                {
                  FileList = SyncFileTime(ExistingFileName, pszPathOut, v28);
                  if ( FileList >= 0 )
                  {
                    v29 = v38;
                    FileList = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)v38 + 296LL))(
                                 v38,
                                 pszPathOut);
                    if ( FileList >= 0 )
                    {
                      FileList = CThemePackManager::_SetFileList(
                                   (CThemePackManager *)a1,
                                   v38,
                                   (const unsigned __int16 *)(a1 + 4432));
                      if ( FileList >= 0 )
                      {
                        if ( *(_DWORD *)(a1 + 156) > 0x2710u )
                        {
                          v30 = 7;
LABEL_44:
                          CThemePackManager::_ShowDialog(a1, v30, a4);
                          FileList = -2147467259;
                          goto LABEL_60;
                        }
                        if ( *(_QWORD *)(a1 + 160) > 0x80000000 )
                        {
                          v30 = 8;
                          goto LABEL_44;
                        }
                        FileList = CheckDiskSpace((const unsigned __int16 *)(a1 + 4432), 2LL * *(_QWORD *)(a1 + 160));
                        if ( FileList == -2147024784 )
                        {
                          CThemePackManager::_ShowDialog(a1, 12, a4);
                        }
                        else
                        {
                          if ( (a4 & 4) != 0 || *(_QWORD *)(a1 + 160) <= 0x100000u )
                          {
                            *(_QWORD *)(a1 + 4368) = a1;
                            *(_QWORD *)(a1 + 4360) = CThemePackManager::_UnpackNotify;
                            *(_QWORD *)(a1 + 4960) = 0;
                            *(_DWORD *)(a1 + 152) = 0;
                            FileBatch = CabReader::ExtractFileBatch(
                                          (CabReader *)(a1 + 2232),
                                          (const unsigned __int16 *)(a1 + 4432));
                          }
                          else
                          {
                            FileBatch = CThemePackManager::_UnpackFilesWithUI((CThemePackManager *)a1);
                          }
                          FileList = FileBatch;
                          if ( FileBatch >= 0 )
                          {
                            v32 = *(_QWORD *)v29;
                            v38 = 0;
                            if ( (*(int (__fastcall **)(struct ITheme *, struct ITheme **))(v32 + 272))(v29, &v38) < 0 )
                              goto LABEL_62;
                            if ( !(*(unsigned int (__fastcall **)(struct ITheme *))(*(_QWORD *)v38 + 72LL))(v38)
                              && PathCchCombine(pszPath, 0x104u, (PCWSTR)(a1 + 4432), L"DesktopBackground") >= 0 )
                            {
                              FileList = (*(__int64 (__fastcall **)(struct ITheme *, WCHAR *))(*(_QWORD *)v38 + 80LL))(
                                           v38,
                                           pszPath);
                              if ( FileList >= 0 )
                                FileList = (*(__int64 (__fastcall **)(struct ITheme *, struct ITheme *))(*(_QWORD *)v29 + 232LL))(
                                             v29,
                                             v38);
                            }
                            (*(void (__fastcall **)(struct ITheme *))(*(_QWORD *)v38 + 16LL))(v38);
                            if ( FileList >= 0 )
                              goto LABEL_62;
                          }
                          if ( FileList != -2147023673 )
                          {
                            CThemePackManager::_ShowDialog(a1, 10, a4);
                            if ( FileList >= 0 )
                              goto LABEL_62;
                          }
                        }
                      }
                    }
                  }
                }
              }
LABEL_60:
              if ( *(_DWORD *)(a1 + 4952) )
                CThemePackManager::_DeleteThemeFolder(v24, (const unsigned __int16 *)(a1 + 4432));
LABEL_62:
              DeleteFileW(ExistingFileName);
              goto LABEL_17;
            }
          }
LABEL_18:
          for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 4404); j = (unsigned int)(j + 1) )
          {
            v21 = *(_QWORD **)(*(_QWORD *)(a1 + 4408) + 8 * j);
            while ( v21 )
            {
              v33 = v21;
              v21 = (_QWORD *)*v21;
              LocalFree(v33);
            }
            *(_QWORD *)(*(_QWORD *)(a1 + 4408) + 8 * j) = 0;
          }
          v34 = *(void **)(a1 + 4408);
          *(_QWORD *)(a1 + 4400) = 0;
          LocalFree(v34);
          *(_QWORD *)(a1 + 4408) = 0;
          CabReader::ClearFileList(v8);
        }
      }
      v35 = CabReader::CloseCab(v8);
      if ( v35 < 0 )
        return (unsigned int)v35;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)FileList;
}

```

## disassembly

```asm
0x180062f3c  mov     [rsp-8+arg_18], rbx
0x180062f41  push    rbp
0x180062f42  push    rsi
0x180062f43  push    rdi
0x180062f44  push    r12
0x180062f46  push    r13
0x180062f48  push    r14
0x180062f4a  push    r15
0x180062f4c  lea     rbp, [rsp-580h]
0x180062f54  sub     rsp, 680h
0x180062f5b  mov     rax, cs:__security_cookie
0x180062f62  xor     rax, rsp
0x180062f65  mov     [rbp+5B0h+var_40], rax
0x180062f6c  mov     rax, [rbp+5B0h+arg_20]
0x180062f73  mov     r14d, r9d
0x180062f76  mov     [rsp+6B0h+var_680], rax
0x180062f7b  mov     r13, r8
0x180062f7e  mov     rdi, rcx
0x180062f81  test    rdx, rdx
0x180062f84  jz      loc_180063510
0x180062f8a  test    r8, r8
0x180062f8d  jz      loc_180063510
0x180062f93  lea     r12, [rcx+8B8h]
0x180062f9a  mov     [rcx+0A8h], rdx
0x180062fa1  mov     r8d, 0
0x180062fa7  test    r14b, 3
0x180062fab  mov     rcx, r12
0x180062fae  setnz   r8b
0x180062fb2  call    ?OpenCab@CabReader@@QEAAJPEBGW4CAB_OPTIONS@@@Z; CabReader::OpenCab(ushort const *,CAB_OPTIONS)
0x180062fb7  mov     ebx, eax
0x180062fb9  test    eax, eax
0x180062fbb  js      loc_180063515
0x180062fc1  lea     r15, [rdi+1120h]
0x180062fc8  mov     rcx, r12; this
0x180062fcb  mov     rdx, r15
0x180062fce  call    ?GetFileList@CabReader@@QEAAJPEAPEAV?$CDPA@UFILE_INFO@CabReader@@V?$CTContainer_PolicyUnOwned@UFILE_INFO@CabReader@@@@@@@Z; CabReader::GetFileList(CDPA<CabReader::FILE_INFO,CTContainer_PolicyUnOwned<CabReader::FILE_INFO>> * *)
0x180062fd3  mov     ebx, eax
0x180062fd5  test    eax, eax
0x180062fd7  js      loc_180063500
0x180062fdd  mov     rdx, [r15]
0x180062fe0  mov     rcx, rdi
0x180062fe3  call    ?_InitInCabFileTable@CThemePackManager@@AEAAJPEAV?$CDPA@UFILE_INFO@CabReader@@V?$CTContainer_PolicyUnOwned@UFILE_INFO@CabReader@@@@@@@Z; CThemePackManager::_InitInCabFileTable(CDPA<CabReader::FILE_INFO,CTContainer_PolicyUnOwned<CabReader::FILE_INFO>> *)
0x180062fe8  mov     ebx, eax
0x180062fea  test    eax, eax
0x180062fec  js      loc_180063500
0x180062ff2  mov     r12, [r15]
0x180062ff5  mov     rax, [r12]
0x180062ff9  test    rax, rax
0x180062ffc  jz      short loc_180063002
0x180062ffe  mov     ebx, [rax]
0x180063000  jmp     short loc_180063004
0x180063002  xor     ebx, ebx
0x180063004  xor     esi, esi
0x180063006  cmp     esi, ebx
0x180063008  jge     loc_1800630A2
0x18006300e  mov     rcx, [r12]; hdpa
0x180063012  movsxd  rdx, esi; i
0x180063015  call    cs:g_pfn_DPA_GetPtr
0x18006301b  lea     rcx, [rax+4]; pszPath
0x18006301f  call    cs:__imp_PathFindExtensionW
0x180063025  or      ecx, 0FFFFFFFFh
0x180063028  mov     [rsp+6B0h+bIgnoreCase], 1; bIgnoreCase
0x180063030  mov     r9d, ecx; cchCount2
0x180063033  lea     r8, aTheme; ".theme"
0x18006303a  mov     edx, ecx; cchCount1
0x18006303c  mov     rcx, rax; lpString1
0x18006303f  call    cs:__imp_CompareStringOrdinal
0x180063045  cmp     eax, 2
0x180063048  jz      short loc_18006304E
0x18006304a  inc     esi
0x18006304c  jmp     short loc_180063006
0x18006304e  lea     rcx, [rbp+5B0h+ExistingFileName]; lpTempFileName
0x180063055  call    ?GetTempFile@@YAJPEAG_K@Z; GetTempFile(ushort *,unsigned __int64)
0x18006305a  mov     ebx, eax
0x18006305c  test    eax, eax
0x18006305e  js      short loc_1800630A7
0x180063060  mov     rcx, [r15]
0x180063063  movsxd  rdx, esi; i
0x180063066  mov     rcx, [rcx]; hdpa
0x180063069  call    cs:g_pfn_DPA_GetPtr
0x18006306f  mov     qword ptr [rdi+1108h], 0
0x18006307a  mov     rsi, rax
0x18006307d  mov     qword ptr [rdi+1110h], 0
0x180063088  cmp     dword ptr [rax], 500000h
0x18006308e  jbe     short loc_1800630CE
0x180063090  xor     r9d, r9d
0x180063093  mov     r8d, r14d
0x180063096  mov     rcx, rdi
0x180063099  lea     edx, [r9+0Bh]
0x18006309d  call    ?_ShowDialog@CThemePackManager@@CAJPEAV1@HW4THEMEPACK_FLAGS@@PEAH@Z; CThemePackManager::_ShowDialog(CThemePackManager *,int,THEMEPACK_FLAGS,int *)
0x1800630a2  mov     ebx, 80004005h
0x1800630a7  lea     r12, [rdi+8B8h]
0x1800630ae  xor     r14d, r14d
0x1800630b1  cmp     [rdi+1134h], r14d
0x1800630b8  jbe     loc_1800634D5
0x1800630be  mov     rax, [rdi+1138h]
0x1800630c5  mov     rsi, [rax+r14*8]
0x1800630c9  jmp     loc_1800634B5
0x1800630ce  lea     r15, [rax+4]
0x1800630d2  lea     r12, [rdi+8B8h]
0x1800630d9  mov     rdx, r15; unsigned __int16 *
0x1800630dc  mov     rcx, r12; this
0x1800630df  lea     r8, [rbp+5B0h+ExistingFileName]; unsigned __int16 *
0x1800630e6  call    ?ExtractFileWithNameOnDisk@CabReader@@QEAAJPEBG0@Z; CabReader::ExtractFileWithNameOnDisk(ushort const *,ushort const *)
0x1800630eb  mov     ebx, eax
0x1800630ed  test    eax, eax
0x1800630ef  js      short loc_1800630AE
0x1800630f1  lea     rcx, [rbp+5B0h+ExistingFileName]; lpFileName
0x1800630f8  call    ?s_IsValidThemeFile@CThemePackManager@@CA_NPEBG@Z; CThemePackManager::s_IsValidThemeFile(ushort const *)
0x1800630fd  test    al, al
0x1800630ff  jnz     short loc_180063118
0x180063101  xor     r9d, r9d
0x180063104  mov     r8d, r14d
0x180063107  mov     rcx, rdi
0x18006310a  lea     edx, [r9+0Dh]
0x18006310e  call    ?_ShowDialog@CThemePackManager@@CAJPEAV1@HW4THEMEPACK_FLAGS@@PEAH@Z; CThemePackManager::_ShowDialog(CThemePackManager *,int,THEMEPACK_FLAGS,int *)
0x180063113  mov     ebx, 80004005h
0x180063118  test    ebx, ebx
0x18006311a  js      short loc_1800630AE
0x18006311c  mov     ebx, 1
0x180063121  test    cs:Microsoft_Windows_ThemeUIEnableBits, bl
0x180063127  jz      short loc_180063138
0x180063129  mov     r8, r15
0x18006312c  lea     rdx, ThemePack_FileUnpacked_Info
0x180063133  call    McTemplateU0z_EtwEventWriteTransfer
0x180063138  mov     [rsi+214h], ebx
0x18006313e  mov     [rsi+218h], ebx
0x180063144  mov     [rdi+9Ch], ebx
0x18006314a  movsxd  rax, dword ptr [rsi]
0x18006314d  mov     [rdi+0A0h], rax
0x180063154  test    r14b, 8
0x180063158  jz      short loc_1800631D0
0x18006315a  mov     r12d, 104h
0x180063160  lea     r9, aRoamedTheme; "Roamed.theme"
0x180063167  mov     edx, r12d; cchPathOut
0x18006316a  lea     rcx, [rbp+5B0h+pszPathOut]; pszPathOut
0x180063171  mov     r8, r13; pszPathIn
0x180063174  call    cs:__imp_PathCchCombine
0x18006317a  mov     ebx, eax
0x18006317c  test    eax, eax
0x18006317e  js      loc_180063482
0x180063184  lea     r9, aRoamedthemefil; "RoamedThemeFiles"
0x18006318b  mov     r8, r13; pszPathIn
0x18006318e  mov     edx, r12d; cchPathOut
0x180063191  lea     rcx, [rsp+6B0h+pszPath]; pszPathOut
0x180063196  call    cs:__imp_PathCchCombine
0x18006319c  test    eax, eax
0x18006319e  js      short loc_1800631AA
0x1800631a0  lea     rdx, [rsp+6B0h+pszPath]; unsigned __int16 *
0x1800631a5  call    ?_DeleteThemeFolder@CThemePackManager@@AEAAJPEBG@Z; CThemePackManager::_DeleteThemeFolder(ushort const *)
0x1800631aa  lea     rax, [rdi+1150h]
0x1800631b1  mov     r9, rsi; struct CabReader::FILE_INFO *
0x1800631b4  lea     r8, aRoamedthemefil; "RoamedThemeFiles"
0x1800631bb  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; unsigned __int16 *
0x1800631c0  mov     rdx, r13; unsigned __int16 *
0x1800631c3  mov     rcx, rdi; this
0x1800631c6  call    ?_CreateThemeFolder@CThemePackManager@@AEAAJPEBG0PEBUFILE_INFO@CabReader@@PEAG_K@Z; CThemePackManager::_CreateThemeFolder(ushort const *,ushort const *,CabReader::FILE_INFO const *,ushort *,unsigned __int64)
0x1800631cb  jmp     loc_180063259
0x1800631d0  mov     rcx, r15; pszPath
0x1800631d3  call    cs:__imp_PathFindFileNameW
0x1800631d9  mov     r12d, 104h
0x1800631df  lea     rcx, [rsp+6B0h+pszPath]; unsigned __int16 *
0x1800631e4  mov     r8, rax; unsigned __int16 *
0x1800631e7  mov     edx, r12d; unsigned __int64
0x1800631ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800631ef  mov     ebx, eax
0x1800631f1  test    eax, eax
0x1800631f3  js      loc_180063482
0x1800631f9  lea     rcx, [rsp+6B0h+pszPath]; pszPath
0x1800631fe  call    cs:__imp_PathRemoveExtensionW
0x180063204  lea     rdx, pszTrimChars; " "
0x18006320b  lea     rcx, [rsp+6B0h+pszPath]; psz
0x180063210  call    cs:__imp_StrTrimW
0x180063216  lea     rax, [rdi+1150h]
0x18006321d  mov     r9, rsi; struct CabReader::FILE_INFO *
0x180063220  lea     r8, [rsp+6B0h+pszPath]; unsigned __int16 *
0x180063225  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax; unsigned __int16 *
0x18006322a  mov     rdx, r13; unsigned __int16 *
0x18006322d  mov     rcx, rdi; this
0x180063230  call    ?_CreateThemeFolder@CThemePackManager@@AEAAJPEBG0PEBUFILE_INFO@CabReader@@PEAG_K@Z; CThemePackManager::_CreateThemeFolder(ushort const *,ushort const *,CabReader::FILE_INFO const *,ushort *,unsigned __int64)
0x180063235  mov     ebx, eax
0x180063237  test    eax, eax
0x180063239  js      loc_180063482
0x18006323f  mov     r9, r15; pszMore
0x180063242  lea     r8, [rdi+1150h]; pszPathIn
0x180063249  mov     edx, r12d; cchPathOut
0x18006324c  lea     rcx, [rbp+5B0h+pszPathOut]; pszPathOut
0x180063253  call    cs:__imp_PathCchCombine
0x180063259  mov     ebx, eax
0x18006325b  test    eax, eax
0x18006325d  js      loc_180063482
0x180063263  xor     r8d, r8d; bFailIfExists
0x180063266  lea     rdx, [rbp+5B0h+pszPathOut]; lpNewFileName
0x18006326d  lea     rcx, [rbp+5B0h+ExistingFileName]; lpExistingFileName
0x180063274  call    cs:__imp_CopyFileW
0x18006327a  test    eax, eax
0x18006327c  jnz     short loc_18006328D
0x18006327e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180063283  mov     ebx, eax
0x180063285  test    eax, eax
0x180063287  js      loc_180063482
0x18006328d  lea     rdx, [rbp+5B0h+pszPathOut]; unsigned __int16 *
0x180063294  lea     rcx, [rbp+5B0h+ExistingFileName]; unsigned __int16 *
0x18006329b  call    ?SyncFileTime@@YAJPEBG0K@Z; SyncFileTime(ushort const *,ushort const *,ulong)
0x1800632a0  mov     ebx, eax
0x1800632a2  test    eax, eax
0x1800632a4  js      loc_180063482
0x1800632aa  mov     r15, [rsp+6B0h+var_680]
0x1800632af  lea     rdx, [rbp+5B0h+pszPathOut]
0x1800632b6  mov     rcx, r15
0x1800632b9  mov     rax, [r15]
0x1800632bc  mov     rax, [rax+128h]
0x1800632c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632c8  mov     ebx, eax
0x1800632ca  test    eax, eax
0x1800632cc  js      loc_180063482
0x1800632d2  lea     rsi, [rdi+1150h]
0x1800632d9  mov     rdx, r15; struct ITheme *
0x1800632dc  mov     r8, rsi; unsigned __int16 *
0x1800632df  mov     rcx, rdi; this
0x1800632e2  call    ?_SetFileList@CThemePackManager@@AEAAJPEAUITheme@@PEBG@Z; CThemePackManager::_SetFileList(ITheme *,ushort const *)
0x1800632e7  mov     ebx, eax
0x1800632e9  test    eax, eax
0x1800632eb  js      loc_180063482
0x1800632f1  cmp     dword ptr [rdi+9Ch], 2710h
0x1800632fb  jbe     short loc_180063304
0x1800632fd  mov     edx, 7
0x180063302  jmp     short loc_180063317
0x180063304  mov     eax, 80000000h
0x180063309  cmp     [rdi+0A0h], rax
0x180063310  jbe     short loc_18006332F
0x180063312  mov     edx, 8
0x180063317  mov     r8d, r14d
0x18006331a  xor     r9d, r9d
0x18006331d  mov     rcx, rdi
0x180063320  call    ?_ShowDialog@CThemePackManager@@CAJPEAV1@HW4THEMEPACK_FLAGS@@PEAH@Z; CThemePackManager::_ShowDialog(CThemePackManager *,int,THEMEPACK_FLAGS,int *)
0x180063325  mov     ebx, 80004005h
0x18006332a  jmp     loc_180063482
0x18006332f  mov     rdx, [rdi+0A0h]
0x180063336  mov     rcx, rsi; unsigned __int16 *
0x180063339  add     rdx, rdx; unsigned __int64
0x18006333c  call    ?CheckDiskSpace@@YAJPEBG_K@Z; CheckDiskSpace(ushort const *,unsigned __int64)
0x180063341  mov     ebx, eax
0x180063343  cmp     eax, 80070070h
0x180063348  jnz     short loc_180063361
0x18006334a  xor     r9d, r9d
0x18006334d  mov     r8d, r14d
0x180063350  mov     rcx, rdi
0x180063353  lea     edx, [r9+0Ch]
0x180063357  call    ?_ShowDialog@CThemePackManager@@CAJPEAV1@HW4THEMEPACK_FLAGS@@PEAH@Z; CThemePackManager::_ShowDialog(CThemePackManager *,int,THEMEPACK_FLAGS,int *)
0x18006335c  jmp     loc_180063482
0x180063361  test    r14b, 4
0x180063365  jnz     short loc_18006337E
0x180063367  cmp     qword ptr [rdi+0A0h], 100000h
0x180063372  jbe     short loc_18006337E
0x180063374  mov     rcx, rdi; this
0x180063377  call    ?_UnpackFilesWithUI@CThemePackManager@@AEAAJXZ; CThemePackManager::_UnpackFilesWithUI(void)
0x18006337c  jmp     short loc_1800633B7
0x18006337e  mov     [rdi+1110h], rdi
0x180063385  lea     rax, ?_UnpackNotify@CThemePackManager@@CAHI_J0PEAX@Z; CThemePackManager::_UnpackNotify(uint,__int64,__int64,void *)
0x18006338c  mov     [rdi+1108h], rax
0x180063393  lea     rcx, [rdi+8B8h]; this
0x18006339a  mov     rdx, rsi; unsigned __int16 *
0x18006339d  mov     qword ptr [rdi+1360h], 0
0x1800633a8  mov     dword ptr [rdi+98h], 0
0x1800633b2  call    ?ExtractFileBatch@CabReader@@QEAAJPEBG@Z; CabReader::ExtractFileBatch(ushort const *)
0x1800633b7  mov     ebx, eax
0x1800633b9  test    eax, eax
0x1800633bb  js      loc_180063464
0x1800633c1  mov     rax, [r15]
0x1800633c4  lea     rdx, [rsp+6B0h+var_680]
0x1800633c9  mov     rcx, r15
0x1800633cc  mov     [rsp+6B0h+var_680], 0
0x1800633d5  mov     rax, [rax+110h]
0x1800633dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633e1  test    eax, eax
0x1800633e3  js      loc_180063497
0x1800633e9  mov     rcx, [rsp+6B0h+var_680]
0x1800633ee  mov     rax, [rcx]
0x1800633f1  mov     rax, [rax+48h]
0x1800633f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633fa  test    eax, eax
0x1800633fc  jnz     short loc_18006344F
0x1800633fe  lea     r9, aDesktopbackgro; "DesktopBackground"
0x180063405  mov     r8, rsi; pszPathIn
0x180063408  mov     rdx, r12; cchPathOut
0x18006340b  lea     rcx, [rsp+6B0h+pszPath]; pszPathOut
0x180063410  call    cs:__imp_PathCchCombine
0x180063416  test    eax, eax
0x180063418  js      short loc_18006344F
0x18006341a  mov     rcx, [rsp+6B0h+var_680]
0x18006341f  lea     rdx, [rsp+6B0h+pszPath]
0x180063424  mov     rax, [rcx]
0x180063427  mov     rax, [rax+50h]
0x18006342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063430  mov     ebx, eax
0x180063432  test    eax, eax
0x180063434  js      short loc_18006344F
0x180063436  mov     rax, [r15]
0x180063439  mov     rcx, r15
  ... truncated ...
```
