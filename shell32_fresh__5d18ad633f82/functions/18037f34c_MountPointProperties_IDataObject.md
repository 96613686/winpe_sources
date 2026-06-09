# MountPointProperties(IDataObject *)

- ea: `0x18037f34c`
- end: `0x18037f6a0`
- name: `?MountPointProperties@@YAJPEAUIDataObject@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(IDataObject *pdtInner)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180220e7c`

## callees

- `0x180018e4c`
- `0x18003a3e0`
- `0x180048c54`
- `0x180159030`
- `0x180249490`
- `0x18024a53c`
- `0x18030c4c0`
- `0x18037f34c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18037f4b3`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18037f4b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18037f4e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18037f4e6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18037f41b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18037f41b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18037f521`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18037f521`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18037f537`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18037f537`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18037f50c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18037f50c`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18037f66a`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18037f66a`
- `Windows.Storage!ILFindLastID` at `0x18037f59a`
- `Windows.Storage!ILFindLastID` at `0x18037f59a`
- `Windows.Storage!SHParseDisplayName` at `0x18037f467`
- `Windows.Storage!SHParseDisplayName` at `0x18037f467`
- `Windows.Storage!ILClone` at `0x18037f56e`
- `Windows.Storage!ILClone` at `0x18037f56e`
- `Windows.Storage!DragQueryFileW` at `0x18037f3fe`
- `Windows.Storage!DragQueryFileW` at `0x18037f3fe`
- `Windows.Storage!ILRemoveLastID` at `0x18037f589`
- `Windows.Storage!ILRemoveLastID` at `0x18037f589`
- `Windows.Storage!ILFree` at `0x18037f62c`
- `Windows.Storage!ILFree` at `0x18037f644`
- `Windows.Storage!ILFree` at `0x18037f62c`
- `Windows.Storage!ILFree` at `0x18037f644`
- `Windows.Storage!SHCreateDataObject` at `0x18037f5d1`
- `Windows.Storage!SHCreateDataObject` at `0x18037f5d1`

## pseudocode

```c
__int64 __fastcall MountPointProperties(IDataObject *pdtInner)
{
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT Error; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rbx
  ITEMIDLIST *v8; // rax
  ITEMIDLIST *v9; // rdi
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  IBindCtx *pbc; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v14; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+5Ah] [rbp-A6h]
  __int16 v16; // [rsp+5Eh] [rbp-A2h]
  __int64 v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+68h] [rbp-98h]
  int v19; // [rsp+6Ch] [rbp-94h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  LPCITEMIDLIST apidl; // [rsp+78h] [rbp-88h] BYREF
  STGMEDIUM hDrop; // [rsp+80h] [rbp-80h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR szFile[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  IDLData_InitializeClipboardFormats();
  v18 = 1;
  v14 = g_cfMountedVolume;
  v19 = -1;
  v15 = 0;
  v16 = 0;
  lpVtbl = pdtInner->lpVtbl;
  memset(&hDrop, 0, sizeof(hDrop));
  v17 = 0;
  v20 = 1;
  Error = ((__int64 (__fastcall *)(IDataObject *, __int16 *, STGMEDIUM *))lpVtbl->GetData)(pdtInner, &v14, &hDrop);
  if ( Error >= 0 )
  {
    DragQueryFileW((HDROP)hDrop.hBitmap, 0, szFile, 0x104u);
    if ( GetVolumeNameForVolumeMountPointW(szFile, szVolumeName, 0x104u)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      pbc = 0;
      _CreatePropertyBagBindCtx<unsigned long>(v5, v4, v6, &pbc);
      ppidl = 0;
      Error = SHParseDisplayName(szVolumeName, pbc, &ppidl, 0, 0);
      if ( Error >= 0 )
      {
        memset_0(VolumeNameBuffer, 0, 0x208u);
        if ( (GetVolumeInformationW(szVolumeName, VolumeNameBuffer, 0x104u, 0, 0, 0, 0, 0)
           || (int)ResultFromKnownLastError() >= 0)
          && VolumeNameBuffer[0]
          || LoadStringW(g_hinst, 0x107Eu, VolumeNameBuffer, 260)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          if ( PathGetDriveNumberW(szFile) != -1 )
          {
            v7 = lstrlenW(VolumeNameBuffer);
            PathRemoveBackslashW(szFile);
            StringCchPrintfW(&VolumeNameBuffer[v7], 260 - v7, L" (%s)", szFile);
          }
          ppv = 0;
          v8 = ILClone(ppidl);
          v9 = v8;
          if ( v8 )
          {
            ILRemoveLastID(v8);
            apidl = ILFindLastID(ppidl);
            Error = SHCreateDataObject(v9, 1u, &apidl, pdtInner, &GUID_0000010e_0000_0000_c000_000000000046, &ppv);
            if ( Error >= 0 )
            {
              Error = !SHOpenPropSheetW(VolumeNameBuffer, 0, 0, &CLSID_ShellDrvDefExt, (IDataObject *)ppv, 0, 0)
                    ? 0x80004005
                    : 0;
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            ILFree(v9);
          }
          else
          {
            Error = -2147024882;
          }
        }
        ILFree(ppidl);
      }
      if ( pbc )
        ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
    }
    ReleaseStgMedium(&hDrop);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18037f34c  mov     [rsp-8+arg_8], rbx
0x18037f351  mov     [rsp-8+arg_10], rsi
0x18037f356  push    rbp
0x18037f357  push    rdi
0x18037f358  push    r14
0x18037f35a  lea     rbp, [rsp-5E0h]
0x18037f362  sub     rsp, 6E0h
0x18037f369  mov     rax, cs:__security_cookie
0x18037f370  xor     rax, rsp
0x18037f373  mov     [rbp+5F0h+var_20], rax
0x18037f37a  mov     rsi, rcx
0x18037f37d  call    IDLData_InitializeClipboardFormats
0x18037f382  xor     eax, eax
0x18037f384  mov     [rsp+6F0h+var_688], 1
0x18037f38c  mov     [rbp+5F0h+var_660], rax
0x18037f390  lea     r8, [rbp+5F0h+hDrop]
0x18037f394  movzx   eax, cs:g_cfMountedVolume
0x18037f39b  lea     rdx, [rsp+6F0h+var_698]
0x18037f3a0  mov     [rsp+6F0h+var_698], ax
0x18037f3a5  xorps   xmm0, xmm0
0x18037f3a8  xor     eax, eax
0x18037f3aa  mov     [rsp+6F0h+var_684], 0FFFFFFFFh
0x18037f3b2  mov     [rsp+6F0h+var_696], eax
0x18037f3b6  xor     r14d, r14d
0x18037f3b9  mov     [rsp+6F0h+var_692], ax
0x18037f3be  mov     rcx, rsi
0x18037f3c1  mov     rax, [rsi]
0x18037f3c4  movups  xmmword ptr [rbp+5F0h+hDrop], xmm0
0x18037f3c8  mov     [rsp+6F0h+var_690], r14
0x18037f3cd  mov     [rsp+6F0h+var_680], 1
0x18037f3d6  mov     rax, [rax+18h]
0x18037f3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f3df  mov     ebx, eax
0x18037f3e1  test    eax, eax
0x18037f3e3  js      loc_18037F676
0x18037f3e9  mov     rcx, [rbp+5F0h+hDrop+8]; hDrop
0x18037f3ed  lea     r8, [rbp+5F0h+szFile]; lpszFile
0x18037f3f4  mov     edi, 104h
0x18037f3f9  xor     edx, edx; iFile
0x18037f3fb  mov     r9d, edi; cch
0x18037f3fe  call    cs:__imp_DragQueryFileW
0x18037f405  nop     dword ptr [rax+rax+00h]
0x18037f40a  mov     r8d, edi; cchBufferLength
0x18037f40d  lea     rdx, [rbp+5F0h+szVolumeName]; lpszVolumeName
0x18037f414  lea     rcx, [rbp+5F0h+szFile]; lpszVolumeMountPoint
0x18037f41b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18037f422  nop     dword ptr [rax+rax+00h]
0x18037f427  test    eax, eax
0x18037f429  jnz     short loc_18037F43A
0x18037f42b  call    ResultFromKnownLastError
0x18037f430  mov     ebx, eax
0x18037f432  test    eax, eax
0x18037f434  js      loc_18037F666
0x18037f43a  lea     r9, [rsp+6F0h+pbc]
0x18037f43f  mov     [rsp+6F0h+pbc], r14
0x18037f444  call    ??$_CreatePropertyBagBindCtx@K@@YAJPEAUIBindCtx@@PEBGKPEAPEAU0@@Z; _CreatePropertyBagBindCtx<ulong>(IBindCtx *,ushort const *,ulong,IBindCtx * *)
0x18037f449  mov     rdx, [rsp+6F0h+pbc]; pbc
0x18037f44e  lea     r8, [rsp+6F0h+ppidl]; ppidl
0x18037f453  xor     r9d, r9d; sfgaoIn
0x18037f456  mov     [rsp+6F0h+ppidl], r14
0x18037f45b  lea     rcx, [rbp+5F0h+szVolumeName]; pszName
0x18037f462  mov     [rsp+6F0h+psfgaoOut], r14; psfgaoOut
0x18037f467  call    cs:__imp_SHParseDisplayName
0x18037f46e  nop     dword ptr [rax+rax+00h]
0x18037f473  mov     ebx, eax
0x18037f475  test    eax, eax
0x18037f477  js      loc_18037F650
0x18037f47d  xor     edx, edx; Val
0x18037f47f  lea     rcx, [rbp+5F0h+VolumeNameBuffer]; void *
0x18037f483  mov     r8d, 208h; Size
0x18037f489  call    memset_0
0x18037f48e  mov     [rsp+6F0h+nFileSystemNameSize], r14d; nFileSystemNameSize
0x18037f493  lea     rdx, [rbp+5F0h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18037f497  mov     [rsp+6F0h+lpFileSystemNameBuffer], r14; lpFileSystemNameBuffer
0x18037f49c  lea     rcx, [rbp+5F0h+szVolumeName]; lpRootPathName
0x18037f4a3  mov     [rsp+6F0h+lpFileSystemFlags], r14; lpFileSystemFlags
0x18037f4a8  xor     r9d, r9d; lpVolumeSerialNumber
0x18037f4ab  mov     r8d, edi; nVolumeNameSize
0x18037f4ae  mov     [rsp+6F0h+psfgaoOut], r14; lpMaximumComponentLength
0x18037f4b3  call    cs:__imp_GetVolumeInformationW
0x18037f4ba  nop     dword ptr [rax+rax+00h]
0x18037f4bf  test    eax, eax
0x18037f4c1  jnz     short loc_18037F4CC
0x18037f4c3  call    ResultFromKnownLastError
0x18037f4c8  test    eax, eax
0x18037f4ca  js      short loc_18037F4D3
0x18037f4cc  cmp     [rbp+5F0h+VolumeNameBuffer], r14w
0x18037f4d1  jnz     short loc_18037F505
0x18037f4d3  mov     rcx, cs:g_hinst; hInstance
0x18037f4da  lea     r8, [rbp+5F0h+VolumeNameBuffer]; lpBuffer
0x18037f4de  mov     r9d, edi; cchBufferMax
0x18037f4e1  mov     edx, 107Eh; uID
0x18037f4e6  call    cs:__imp_LoadStringW
0x18037f4ed  nop     dword ptr [rax+rax+00h]
0x18037f4f2  test    eax, eax
0x18037f4f4  jnz     short loc_18037F505
0x18037f4f6  call    ResultFromKnownLastError
0x18037f4fb  mov     ebx, eax
0x18037f4fd  test    eax, eax
0x18037f4ff  js      loc_18037F63F
0x18037f505  lea     rcx, [rbp+5F0h+szFile]; pszPath
0x18037f50c  call    cs:__imp_PathGetDriveNumberW
0x18037f513  nop     dword ptr [rax+rax+00h]
0x18037f518  cmp     eax, 0FFFFFFFFh
0x18037f51b  jz      short loc_18037F564
0x18037f51d  lea     rcx, [rbp+5F0h+VolumeNameBuffer]; lpString
0x18037f521  call    cs:__imp_lstrlenW
0x18037f528  nop     dword ptr [rax+rax+00h]
0x18037f52d  lea     rcx, [rbp+5F0h+szFile]; pszPath
0x18037f534  movsxd  rbx, eax
0x18037f537  call    cs:__imp_PathRemoveBackslashW
0x18037f53e  nop     dword ptr [rax+rax+00h]
0x18037f543  sub     rdi, rbx
0x18037f546  lea     rcx, [rbp+5F0h+VolumeNameBuffer]
0x18037f54a  lea     rcx, [rcx+rbx*2]; unsigned __int16 *
0x18037f54e  mov     rdx, rdi; unsigned __int64
0x18037f551  lea     r9, [rbp+5F0h+szFile]
0x18037f558  lea     r8, aS_3; " (%s)"
0x18037f55f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18037f564  mov     rcx, [rsp+6F0h+ppidl]; pidl
0x18037f569  mov     [rsp+6F0h+ppv], r14
0x18037f56e  call    cs:__imp_ILClone
0x18037f575  nop     dword ptr [rax+rax+00h]
0x18037f57a  mov     rdi, rax
0x18037f57d  test    rax, rax
0x18037f580  jz      loc_18037F63A
0x18037f586  mov     rcx, rax; pidl
0x18037f589  call    cs:__imp_ILRemoveLastID
0x18037f590  nop     dword ptr [rax+rax+00h]
0x18037f595  mov     rcx, [rsp+6F0h+ppidl]; pidl
0x18037f59a  call    cs:__imp_ILFindLastID
0x18037f5a1  nop     dword ptr [rax+rax+00h]
0x18037f5a6  mov     [rsp+6F0h+apidl], rax
0x18037f5ab  mov     r9, rsi; pdtInner
0x18037f5ae  lea     r8, [rsp+6F0h+apidl]; apidl
0x18037f5b3  mov     edx, 1; cidl
0x18037f5b8  lea     rax, [rsp+6F0h+ppv]
0x18037f5bd  mov     rcx, rdi; pidlFolder
0x18037f5c0  mov     [rsp+6F0h+lpFileSystemFlags], rax; ppv
0x18037f5c5  lea     rax, _GUID_0000010e_0000_0000_c000_000000000046
0x18037f5cc  mov     [rsp+6F0h+psfgaoOut], rax; riid
0x18037f5d1  call    cs:__imp_SHCreateDataObject
0x18037f5d8  nop     dword ptr [rax+rax+00h]
0x18037f5dd  mov     ebx, eax
0x18037f5df  test    eax, eax
0x18037f5e1  js      short loc_18037F629
0x18037f5e3  mov     rax, [rsp+6F0h+ppv]
0x18037f5e8  lea     r9, CLSID_ShellDrvDefExt; pclsidDefault
0x18037f5ef  mov     [rsp+6F0h+lpFileSystemNameBuffer], r14; pStartPage
0x18037f5f4  lea     rcx, [rbp+5F0h+VolumeNameBuffer]; pszCaption
0x18037f5f8  mov     [rsp+6F0h+lpFileSystemFlags], r14; psb
0x18037f5fd  xor     r8d, r8d; ckeys
0x18037f600  xor     edx, edx; ahkeys
0x18037f602  mov     [rsp+6F0h+psfgaoOut], rax; pdtobj
0x18037f607  call    SHOpenPropSheetW
0x18037f60c  mov     rcx, [rsp+6F0h+ppv]
0x18037f611  neg     eax
0x18037f613  sbb     ebx, ebx
0x18037f615  not     ebx
0x18037f617  mov     rax, [rcx]
0x18037f61a  and     ebx, 80004005h
0x18037f620  mov     rax, [rax+10h]
0x18037f624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f629  mov     rcx, rdi; pidl
0x18037f62c  call    cs:__imp_ILFree
0x18037f633  nop     dword ptr [rax+rax+00h]
0x18037f638  jmp     short loc_18037F63F
0x18037f63a  mov     ebx, 8007000Eh
0x18037f63f  mov     rcx, [rsp+6F0h+ppidl]; pidl
0x18037f644  call    cs:__imp_ILFree
0x18037f64b  nop     dword ptr [rax+rax+00h]
0x18037f650  mov     rcx, [rsp+6F0h+pbc]
0x18037f655  test    rcx, rcx
0x18037f658  jz      short loc_18037F666
0x18037f65a  mov     rax, [rcx]
0x18037f65d  mov     rax, [rax+10h]
0x18037f661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037f666  lea     rcx, [rbp+5F0h+hDrop]; LPSTGMEDIUM
0x18037f66a  call    cs:__imp_ReleaseStgMedium
0x18037f671  nop     dword ptr [rax+rax+00h]
0x18037f676  mov     eax, ebx
0x18037f678  mov     rcx, [rbp+5F0h+var_20]
0x18037f67f  xor     rcx, rsp; StackCookie
0x18037f682  call    __security_check_cookie
0x18037f687  lea     r11, [rsp+6F0h+var_10]
0x18037f68f  mov     rbx, [r11+28h]
0x18037f693  mov     rsi, [r11+30h]
0x18037f697  mov     rsp, r11
0x18037f69a  pop     r14
0x18037f69c  pop     rdi
0x18037f69d  pop     rbp
0x18037f69e  retn
```
