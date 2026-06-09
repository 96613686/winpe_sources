# MountPointProperties(IDataObject *)

- ea: `0x18035b938`
- end: `0x18035bc31`
- name: `?MountPointProperties@@YAJPEAUIDataObject@@@Z`
- size: `761`
- prototype: `__int64 __fastcall(IDataObject *pdtInner)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180209898`

## callees

- `0x1800208d8`
- `0x18003eab0`
- `0x1800757f4`
- `0x180148038`
- `0x180233280`
- `0x1802342fc`
- `0x1802ed100`
- `0x18035b938`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18035ba8d`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18035ba8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18035baba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18035baba`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18035ba01`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18035ba01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18035bae9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18035bae9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18035bada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18035bada`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18035baf9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x18035baf9`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18035bc02`
- `ext-ms-win-com-ole32-l1-1-3!ReleaseStgMedium` at `0x18035bc02`
- `Windows.Storage!ILFindLastID` at `0x18035bb4a`
- `Windows.Storage!ILFindLastID` at `0x18035bb4a`
- `Windows.Storage!SHParseDisplayName` at `0x18035ba47`
- `Windows.Storage!SHParseDisplayName` at `0x18035ba47`
- `Windows.Storage!ILClone` at `0x18035bb2a`
- `Windows.Storage!ILClone` at `0x18035bb2a`
- `Windows.Storage!DragQueryFileW` at `0x18035b9ea`
- `Windows.Storage!DragQueryFileW` at `0x18035b9ea`
- `Windows.Storage!ILRemoveLastID` at `0x18035bb3f`
- `Windows.Storage!ILRemoveLastID` at `0x18035bb3f`
- `Windows.Storage!ILFree` at `0x18035bbd0`
- `Windows.Storage!ILFree` at `0x18035bbe2`
- `Windows.Storage!ILFree` at `0x18035bbd0`
- `Windows.Storage!ILFree` at `0x18035bbe2`
- `Windows.Storage!SHCreateDataObject` at `0x18035bb7b`
- `Windows.Storage!SHCreateDataObject` at `0x18035bb7b`

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
0x18035b938  mov     [rsp-8+arg_8], rbx
0x18035b93d  mov     [rsp-8+arg_10], rsi
0x18035b942  push    rbp
0x18035b943  push    rdi
0x18035b944  push    r14
0x18035b946  lea     rbp, [rsp-5E0h]
0x18035b94e  sub     rsp, 6E0h
0x18035b955  mov     rax, cs:__security_cookie
0x18035b95c  xor     rax, rsp
0x18035b95f  mov     [rbp+5F0h+var_20], rax
0x18035b966  mov     rsi, rcx
0x18035b969  call    IDLData_InitializeClipboardFormats
0x18035b96e  xor     eax, eax
0x18035b970  mov     [rsp+6F0h+var_688], 1
0x18035b978  mov     [rbp+5F0h+var_660], rax
0x18035b97c  lea     r8, [rbp+5F0h+hDrop]
0x18035b980  movzx   eax, cs:g_cfMountedVolume
0x18035b987  lea     rdx, [rsp+6F0h+var_698]
0x18035b98c  mov     [rsp+6F0h+var_698], ax
0x18035b991  xorps   xmm0, xmm0
0x18035b994  xor     eax, eax
0x18035b996  mov     [rsp+6F0h+var_684], 0FFFFFFFFh
0x18035b99e  mov     [rsp+6F0h+var_696], eax
0x18035b9a2  xor     r14d, r14d
0x18035b9a5  mov     [rsp+6F0h+var_692], ax
0x18035b9aa  mov     rcx, rsi
0x18035b9ad  mov     rax, [rsi]
0x18035b9b0  movups  xmmword ptr [rbp+5F0h+hDrop], xmm0
0x18035b9b4  mov     [rsp+6F0h+var_690], r14
0x18035b9b9  mov     [rsp+6F0h+var_680], 1
0x18035b9c2  mov     rax, [rax+18h]
0x18035b9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18035b9cb  mov     ebx, eax
0x18035b9cd  test    eax, eax
0x18035b9cf  js      loc_18035BC08
0x18035b9d5  mov     rcx, [rbp+5F0h+hDrop+8]; hDrop
0x18035b9d9  lea     r8, [rbp+5F0h+szFile]; lpszFile
0x18035b9e0  mov     edi, 104h
0x18035b9e5  xor     edx, edx; iFile
0x18035b9e7  mov     r9d, edi; cch
0x18035b9ea  call    cs:__imp_DragQueryFileW
0x18035b9f0  mov     r8d, edi; cchBufferLength
0x18035b9f3  lea     rdx, [rbp+5F0h+szVolumeName]; lpszVolumeName
0x18035b9fa  lea     rcx, [rbp+5F0h+szFile]; lpszVolumeMountPoint
0x18035ba01  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18035ba07  test    eax, eax
0x18035ba09  jnz     short loc_18035BA1A
0x18035ba0b  call    ResultFromKnownLastError
0x18035ba10  mov     ebx, eax
0x18035ba12  test    eax, eax
0x18035ba14  js      loc_18035BBFE
0x18035ba1a  lea     r9, [rsp+6F0h+pbc]
0x18035ba1f  mov     [rsp+6F0h+pbc], r14
0x18035ba24  call    ??$_CreatePropertyBagBindCtx@K@@YAJPEAUIBindCtx@@PEBGKPEAPEAU0@@Z; _CreatePropertyBagBindCtx<ulong>(IBindCtx *,ushort const *,ulong,IBindCtx * *)
0x18035ba29  mov     rdx, [rsp+6F0h+pbc]; pbc
0x18035ba2e  lea     r8, [rsp+6F0h+ppidl]; ppidl
0x18035ba33  xor     r9d, r9d; sfgaoIn
0x18035ba36  mov     [rsp+6F0h+ppidl], r14
0x18035ba3b  lea     rcx, [rbp+5F0h+szVolumeName]; pszName
0x18035ba42  mov     [rsp+6F0h+psfgaoOut], r14; psfgaoOut
0x18035ba47  call    cs:__imp_SHParseDisplayName
0x18035ba4d  mov     ebx, eax
0x18035ba4f  test    eax, eax
0x18035ba51  js      loc_18035BBE8
0x18035ba57  xor     edx, edx; Val
0x18035ba59  lea     rcx, [rbp+5F0h+VolumeNameBuffer]; void *
0x18035ba5d  mov     r8d, 208h; Size
0x18035ba63  call    memset_0
0x18035ba68  mov     [rsp+6F0h+nFileSystemNameSize], r14d; nFileSystemNameSize
0x18035ba6d  lea     rdx, [rbp+5F0h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18035ba71  mov     [rsp+6F0h+lpFileSystemNameBuffer], r14; lpFileSystemNameBuffer
0x18035ba76  lea     rcx, [rbp+5F0h+szVolumeName]; lpRootPathName
0x18035ba7d  mov     [rsp+6F0h+lpFileSystemFlags], r14; lpFileSystemFlags
0x18035ba82  xor     r9d, r9d; lpVolumeSerialNumber
0x18035ba85  mov     r8d, edi; nVolumeNameSize
0x18035ba88  mov     [rsp+6F0h+psfgaoOut], r14; lpMaximumComponentLength
0x18035ba8d  call    cs:__imp_GetVolumeInformationW
0x18035ba93  test    eax, eax
0x18035ba95  jnz     short loc_18035BAA0
0x18035ba97  call    ResultFromKnownLastError
0x18035ba9c  test    eax, eax
0x18035ba9e  js      short loc_18035BAA7
0x18035baa0  cmp     [rbp+5F0h+VolumeNameBuffer], r14w
0x18035baa5  jnz     short loc_18035BAD3
0x18035baa7  mov     rcx, cs:g_hinst; hInstance
0x18035baae  lea     r8, [rbp+5F0h+VolumeNameBuffer]; lpBuffer
0x18035bab2  mov     r9d, edi; cchBufferMax
0x18035bab5  mov     edx, 107Eh; uID
0x18035baba  call    cs:__imp_LoadStringW
0x18035bac0  test    eax, eax
0x18035bac2  jnz     short loc_18035BAD3
0x18035bac4  call    ResultFromKnownLastError
0x18035bac9  mov     ebx, eax
0x18035bacb  test    eax, eax
0x18035bacd  js      loc_18035BBDD
0x18035bad3  lea     rcx, [rbp+5F0h+szFile]; pszPath
0x18035bada  call    cs:__imp_PathGetDriveNumberW
0x18035bae0  cmp     eax, 0FFFFFFFFh
0x18035bae3  jz      short loc_18035BB20
0x18035bae5  lea     rcx, [rbp+5F0h+VolumeNameBuffer]; lpString
0x18035bae9  call    cs:__imp_lstrlenW
0x18035baef  lea     rcx, [rbp+5F0h+szFile]; pszPath
0x18035baf6  movsxd  rbx, eax
0x18035baf9  call    cs:__imp_PathRemoveBackslashW
0x18035baff  sub     rdi, rbx
0x18035bb02  lea     rcx, [rbp+5F0h+VolumeNameBuffer]
0x18035bb06  lea     rcx, [rcx+rbx*2]; unsigned __int16 *
0x18035bb0a  mov     rdx, rdi; unsigned __int64
0x18035bb0d  lea     r9, [rbp+5F0h+szFile]
0x18035bb14  lea     r8, aS_3; " (%s)"
0x18035bb1b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18035bb20  mov     rcx, [rsp+6F0h+ppidl]; pidl
0x18035bb25  mov     [rsp+6F0h+ppv], r14
0x18035bb2a  call    cs:__imp_ILClone
0x18035bb30  mov     rdi, rax
0x18035bb33  test    rax, rax
0x18035bb36  jz      loc_18035BBD8
0x18035bb3c  mov     rcx, rax; pidl
0x18035bb3f  call    cs:__imp_ILRemoveLastID
0x18035bb45  mov     rcx, [rsp+6F0h+ppidl]; pidl
0x18035bb4a  call    cs:__imp_ILFindLastID
0x18035bb50  mov     [rsp+6F0h+apidl], rax
0x18035bb55  mov     r9, rsi; pdtInner
0x18035bb58  lea     r8, [rsp+6F0h+apidl]; apidl
0x18035bb5d  mov     edx, 1; cidl
0x18035bb62  lea     rax, [rsp+6F0h+ppv]
0x18035bb67  mov     rcx, rdi; pidlFolder
0x18035bb6a  mov     [rsp+6F0h+lpFileSystemFlags], rax; ppv
0x18035bb6f  lea     rax, _GUID_0000010e_0000_0000_c000_000000000046
0x18035bb76  mov     [rsp+6F0h+psfgaoOut], rax; riid
0x18035bb7b  call    cs:__imp_SHCreateDataObject
0x18035bb81  mov     ebx, eax
0x18035bb83  test    eax, eax
0x18035bb85  js      short loc_18035BBCD
0x18035bb87  mov     rax, [rsp+6F0h+ppv]
0x18035bb8c  lea     r9, CLSID_ShellDrvDefExt; pclsidDefault
0x18035bb93  mov     [rsp+6F0h+lpFileSystemNameBuffer], r14; pStartPage
0x18035bb98  lea     rcx, [rbp+5F0h+VolumeNameBuffer]; pszCaption
0x18035bb9c  mov     [rsp+6F0h+lpFileSystemFlags], r14; psb
0x18035bba1  xor     r8d, r8d; ckeys
0x18035bba4  xor     edx, edx; ahkeys
0x18035bba6  mov     [rsp+6F0h+psfgaoOut], rax; pdtobj
0x18035bbab  call    SHOpenPropSheetW
0x18035bbb0  mov     rcx, [rsp+6F0h+ppv]
0x18035bbb5  neg     eax
0x18035bbb7  sbb     ebx, ebx
0x18035bbb9  not     ebx
0x18035bbbb  mov     rax, [rcx]
0x18035bbbe  and     ebx, 80004005h
0x18035bbc4  mov     rax, [rax+10h]
0x18035bbc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18035bbcd  mov     rcx, rdi; pidl
0x18035bbd0  call    cs:__imp_ILFree
0x18035bbd6  jmp     short loc_18035BBDD
0x18035bbd8  mov     ebx, 8007000Eh
0x18035bbdd  mov     rcx, [rsp+6F0h+ppidl]; pidl
0x18035bbe2  call    cs:__imp_ILFree
0x18035bbe8  mov     rcx, [rsp+6F0h+pbc]
0x18035bbed  test    rcx, rcx
0x18035bbf0  jz      short loc_18035BBFE
0x18035bbf2  mov     rax, [rcx]
0x18035bbf5  mov     rax, [rax+10h]
0x18035bbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18035bbfe  lea     rcx, [rbp+5F0h+hDrop]; LPSTGMEDIUM
0x18035bc02  call    cs:__imp_ReleaseStgMedium
0x18035bc08  mov     eax, ebx
0x18035bc0a  mov     rcx, [rbp+5F0h+var_20]
0x18035bc11  xor     rcx, rsp; StackCookie
0x18035bc14  call    __security_check_cookie
0x18035bc19  lea     r11, [rsp+6F0h+var_10]
0x18035bc21  mov     rbx, [r11+28h]
0x18035bc25  mov     rsi, [r11+30h]
0x18035bc29  mov     rsp, r11
0x18035bc2c  pop     r14
0x18035bc2e  pop     rdi
0x18035bc2f  pop     rbp
0x18035bc30  retn
```
