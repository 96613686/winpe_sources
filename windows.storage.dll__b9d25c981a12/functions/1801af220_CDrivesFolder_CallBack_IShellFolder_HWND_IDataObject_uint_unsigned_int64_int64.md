# CDrivesFolder::CallBack(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)

- ea: `0x1801af220`
- end: `0x1801af68a`
- name: `?CallBack@CDrivesFolder@@UEAAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z`
- size: `1130`
- prototype: `int(CDrivesFolder *__hidden this, struct IShellFolder *, HWND, struct IDataObject *, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, loader_planting, installer_update`

## callees

- `0x180058560`
- `0x180058cc0`
- `0x180058d68`
- `0x1800693a0`
- `0x180133f50`
- `0x1801720f0`
- `0x1801af1f4`
- `0x1801af220`
- `0x1801af690`
- `0x1801afbf4`
- `0x1801afc3c`
- `0x1801afd34`
- `0x1801d32e0`
- `0x1802e2368`
- `0x1803b1f60`
- `0x1803b2470`
- `0x1805de968`
- `0x1805ec684`
- `0x1806211cc`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af29c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af388`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af29c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801af388`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af2d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af530`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af2d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801af530`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1801af3d4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1801af57b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806703ef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806705aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806705da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806705fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1801af3d4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1801af57b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806703ef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806705aa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806705da`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1806705fe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801af54a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801af54a`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x1801af55a`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x1801af55a`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af43e`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af51b`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af597`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af5b2`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af5cd`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af43e`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af51b`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af597`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af5b2`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1801af5cd`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHLaunchPropSheet` at `0x1806703c7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHLaunchPropSheet` at `0x1806703c7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHFormatDriveAsync` at `0x1806705c8`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHFormatDriveAsync` at `0x1806705c8`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x1801af3aa`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x1801af3aa`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_GetLiveFSDiscInfo` at `0x1801af3ee`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_GetLiveFSDiscInfo` at `0x1801af3ee`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_OnEject` at `0x180670404`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_OnEject` at `0x180670404`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_Erase` at `0x180670610`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_Erase` at `0x180670610`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_CloseSession` at `0x1806705ec`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_CloseSession` at `0x1806705ec`

## string_xrefs

- `0x1801af295`: `shell32.dll`
- `0x1801af381`: `shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDrivesFolder::CallBack(
        CDrivesFolder *this,
        struct IShellFolder *a2,
        HWND a3,
        struct IDataObject *a4,
        unsigned int a5,
        const void *a6,
        __int64 a7)
{
  int v10; // r12d
  HMODULE Library; // rbx
  unsigned int v12; // edi
  const struct _ITEMIDLIST_RELATIVE *v14; // rcx
  struct _IDA *v15; // rsi
  const struct IDDRIVE *v16; // r14
  int v17; // r13d
  HMODULE v18; // rbx
  int v19; // eax
  CMountPoint *v20; // r14
  const struct _ITEMIDLIST_RELATIVE *v21; // rcx
  struct _IDA *v22; // rsi
  int v23; // eax
  int v24; // ecx
  const struct IDDRIVE *v25; // rax
  const void *v26; // rcx
  __int64 v27; // r8
  const struct IDDRIVE *v28; // rbx
  int v29; // eax
  CMountPoint *v30; // rbx
  unsigned int i; // ebx
  const struct _ITEMIDLIST_RELATIVE *IDListPtr; // rax
  const struct IDDRIVE *v33; // r15
  CMountPoint *v34; // r14
  int v35; // r12d
  __int64 v36; // rax
  int v37; // eax
  int v38; // eax
  int DriveNumberA; // eax
  struct _IDA *v40; // [rsp+38h] [rbp-C8h] BYREF
  int v41; // [rsp+40h] [rbp-C0h]
  CMountPoint *v42; // [rsp+48h] [rbp-B8h] BYREF
  LPCSTR pszPath; // [rsp+50h] [rbp-B0h]
  HMODULE v44; // [rsp+58h] [rbp-A8h]
  _QWORD v45[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+80h] [rbp-80h]
  int v48; // [rsp+88h] [rbp-78h] BYREF
  int v49; // [rsp+8Ch] [rbp-74h] BYREF
  STGMEDIUM hMem; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v51[56]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR dwItem1[56]; // [rsp+120h] [rbp+20h] BYREF

  v10 = 0;
  if ( a5 != 1 )
  {
    if ( a5 != 2 )
    {
      if ( a5 == 5 || a5 == 9 || a5 == 11 || a5 == 13 || a5 - 15 < 2 )
      {
        Library = LoadLibraryExW(L"shell32.dll", 0, 2u);
        v12 = HandleStandardDFM(Library, a5, (unsigned __int64)a6, a7, (const struct ICIVERBTOIDMAP *)&off_180699580);
        if ( Library )
          FreeLibrary(Library);
      }
      else
      {
        return (unsigned int)-2147467263;
      }
      return v12;
    }
    v40 = 0;
    memset(&hMem, 0, sizeof(hMem));
    if ( (int)SHGetItemArrayFromDataObj(a4, &hMem, &v40) < 0 )
      return 0;
    v21 = 0;
    v22 = v40;
    if ( v40 && v40->cidl )
      v21 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v40 + v40[1].cidl);
    v25 = CDrivesFolder::_IsValidID(v21);
    v28 = v25;
    if ( v25 )
    {
      v26 = a6;
      if ( a6 == (const void *)3 )
      {
        DriveNumberA = PathGetDriveNumberA((LPCSTR)v25 + 3);
        if ( DriveNumberA >= 0 )
          SHELL32_CDBurn_Erase((unsigned int)DriveNumberA);
      }
      else if ( a6 == (const void *)4 )
      {
        v38 = PathGetDriveNumberA((LPCSTR)v25 + 3);
        if ( v38 >= 0 )
          SHELL32_CDBurn_CloseSession((unsigned int)v38);
      }
      else if ( a6 == (const void *)8 )
      {
        v37 = PathGetDriveNumberA((LPCSTR)v25 + 3);
        if ( v37 >= 0 )
          SHELL32_SHFormatDriveAsync(a3, (unsigned int)v37, 0xFFFF, 0);
      }
      else
      {
        if ( a6 == (const void *)9 )
        {
          Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 9), 13633, v27, a4);
          v45[0] = 40;
          v45[1] = a3;
          v46 = 0;
          v47 = 1;
          for ( i = 0; i < v22->cidl; ++i )
          {
            IDListPtr = IDA_GetIDListPtr(v22, i);
            v33 = CDrivesFolder::_IsValidID(IDListPtr);
            v40 = 0;
            if ( CDrivesFolder::_GetMountPoint(v33, (struct CMountPoint **)&v40) >= 0 )
            {
              v34 = (CMountPoint *)v40;
              if ( (*(unsigned int (__fastcall **)(struct _IDA *))(*(_QWORD *)v40 + 360LL))(v40) )
              {
                v35 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)v34 + 336LL))(v34);
                CDrivesFolder::_GetParsingName(v33, v51, 0x32u);
                StringCchCopyW(dwItem1, 0x32u, v51);
                v36 = -1;
                do
                  ++v36;
                while ( v51[v36] );
                if ( (_DWORD)v36 )
                {
                  if ( 2 * (unsigned __int64)(unsigned int)(v36 - 1) >= 0x64 )
                    _report_rangecheckfailure();
                  v51[(unsigned int)(v36 - 1)] = 0;
                }
                *(_QWORD *)&v46 = v51;
                if ( !(unsigned int)SHWNetDisconnectDialog1(v45) && v35 )
                {
                  CMountPoint::NotifyUnavailableNetDriveGone(dwItem1);
                  SHChangeNotify(128, 5u, dwItem1, 0);
                }
              }
              CMountPoint::Release(v34);
            }
          }
          SHChangeNotify(0, 0x1000u, 0, 0);
          v12 = 0;
          goto LABEL_97;
        }
        if ( a6 != (const void *)10 )
        {
          if ( a6 == (const void *)4294967291LL )
            v12 = SHELL32_SHLaunchPropSheet(a4, a7, &GUID_NULL);
          else
            v12 = 1;
          goto LABEL_97;
        }
        Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 9), 15425, v27, a4);
        v29 = PathGetDriveNumberA((LPCSTR)v28 + 3);
        if ( v29 >= 0 )
          SHELL32_CDBurn_OnEject(a3, (unsigned int)v29);
        v40 = 0;
        if ( CDrivesFolder::_GetMountPoint(v28, (struct CMountPoint **)&v40) >= 0 )
        {
          v30 = (CMountPoint *)v40;
          (*(void (__fastcall **)(struct _IDA *, HWND))(*(_QWORD *)v40 + 272LL))(v40, a3);
          CMountPoint::Release(v30);
        }
      }
    }
    v12 = 0;
LABEL_97:
    ReleaseStgMediumHGLOBAL(v26, &hMem);
    return v12;
  }
  v40 = 0;
  memset(&hMem, 0, sizeof(hMem));
  _InitClipboardFormats();
  if ( SHGetItemArrayFromDataObjEx(a4, g_cfHIDA_Storage, &hMem, &v40) < 0 )
    return 0;
  v14 = 0;
  v15 = v40;
  if ( v40 && v40->cidl )
    v14 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v40 + v40[1].cidl);
  v16 = CDrivesFolder::_IsValidID(v14);
  if ( v16 )
  {
    v17 = *(_DWORD *)(a7 + 12);
    v18 = LoadLibraryExW(L"shell32.dll", 0, 2u);
    v44 = v18;
    SHELL32_CDefFolderMenu_MergeMenu(v18, 247, 0, a7);
    v41 = 0;
    v48 = 0;
    v49 = 0;
    LODWORD(v40) = 0;
    pszPath = (char *)v16 + 3;
    v19 = PathGetDriveNumberA((LPCSTR)v16 + 3);
    if ( v19 >= 0 )
      SHELL32_CDBurn_GetLiveFSDiscInfo((unsigned int)v19, &v48, &v49);
    if ( v15->cidl != 1 || !v48 )
      DeleteMenu(*(HMENU *)a7, v17 + 3, 0);
    if ( v15->cidl != 1 || !v49 )
      DeleteMenu(*(HMENU *)a7, v17 + 4, 0);
    v42 = 0;
    if ( CDrivesFolder::_GetMountPoint(v16, &v42) < 0 )
      goto LABEL_20;
    v20 = v42;
    if ( (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v42 + 360LL))(v42)
      && !SHRestricted(REST_NONETCONNECTDISCONNECT) )
    {
      v10 = 1;
    }
    if ( v15->cidl == 1
      && (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 464LL))(v20)
      && (!(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 392LL))(v20)
       || !SHRestricted(REST_NOCDBURNING)) )
    {
      LODWORD(v40) = 1;
    }
    if ( (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 480LL))(v20) )
    {
      v23 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 280LL))(v20);
      v24 = v41;
      if ( !v23 )
        v24 = 1;
      v41 = v24;
    }
    CMountPoint::Release(v20);
    if ( !v10 )
LABEL_20:
      DeleteMenu(*(HMENU *)a7, v17 + 9, 0);
    if ( !(_DWORD)v40 )
      DeleteMenu(*(HMENU *)a7, v17 + 8, 0);
    if ( v15->cidl != 1 || !v41 || PathGetDriveNumberA(pszPath) < 0 )
      DeleteMenu(*(HMENU *)a7, v17 + 10, 0);
    if ( v18 )
      FreeLibrary(v18);
  }
  if ( hMem.hBitmap && hMem.tymed == 1 )
    GlobalUnlock(hMem.hBitmap);
  ReleaseStgMedium(&hMem);
  return 0;
}

```

## disassembly

```asm
0x1801af220  mov     [rsp-8+arg_8], rbx
0x1801af225  push    rbp
0x1801af226  push    rsi
0x1801af227  push    rdi
0x1801af228  push    r12
0x1801af22a  push    r13
0x1801af22c  push    r14
0x1801af22e  push    r15
0x1801af230  lea     rbp, [rsp-0A0h]
0x1801af238  sub     rsp, 1A0h
0x1801af23f  mov     rax, cs:__security_cookie
0x1801af246  xor     rax, rsp
0x1801af249  mov     [rbp+0D0h+var_40], rax
0x1801af250  mov     rdi, r9
0x1801af253  mov     r14, r8
0x1801af256  mov     r13, rcx
0x1801af259  mov     r15, [rbp+0D0h+arg_30]
0x1801af260  xor     r12d, r12d
0x1801af263  mov     [rsp+1D0h+var_1A0], r12d
0x1801af268  mov     eax, [rbp+0D0h+arg_20]
0x1801af26e  sub     eax, 1
0x1801af271  jz      loc_1801AF312
0x1801af277  sub     eax, 1
0x1801af27a  jz      loc_1801AF603
0x1801af280  lea     r8d, [r12+2]; dwFlags
0x1801af285  sub     eax, 3
0x1801af288  jz      short loc_1801AF293
0x1801af28a  sub     eax, 4
0x1801af28d  jnz     loc_1801AF44F
0x1801af293  xor     edx, edx; hFile
0x1801af295  lea     rcx, aShell32Dll; "shell32.dll"
0x1801af29c  call    cs:__imp_LoadLibraryExW
0x1801af2a3  nop     dword ptr [rax+rax+00h]
0x1801af2a8  mov     rbx, rax
0x1801af2ab  lea     rax, off_180699580; "format"
0x1801af2b2  mov     [rsp+1D0h+var_1B0], rax; struct ICIVERBTOIDMAP *
0x1801af2b7  mov     r9, r15; __int64
0x1801af2ba  mov     r8, [rbp+0D0h+arg_28]; unsigned __int64
0x1801af2c1  mov     edx, [rbp+0D0h+arg_20]; unsigned int
0x1801af2c7  mov     rcx, rbx; HINSTANCE
0x1801af2ca  call    ?HandleStandardDFM@@YAJPEAUHINSTANCE__@@I_K_JPEBUICIVERBTOIDMAP@@@Z; HandleStandardDFM(HINSTANCE__ *,uint,unsigned __int64,__int64,ICIVERBTOIDMAP const *)
0x1801af2cf  mov     edi, eax
0x1801af2d1  test    rbx, rbx
0x1801af2d4  jz      short loc_1801AF2E5
0x1801af2d6  mov     rcx, rbx; hLibModule
0x1801af2d9  call    cs:__imp_FreeLibrary
0x1801af2e0  nop     dword ptr [rax+rax+00h]
0x1801af2e5  mov     eax, edi
0x1801af2e7  mov     rcx, [rbp+0D0h+var_40]
0x1801af2ee  xor     rcx, rsp; StackCookie
0x1801af2f1  call    __security_check_cookie
0x1801af2f6  mov     rbx, [rsp+1D0h+arg_8]
0x1801af2fe  add     rsp, 1A0h
0x1801af305  pop     r15
0x1801af307  pop     r14
0x1801af309  pop     r13
0x1801af30b  pop     r12
0x1801af30d  pop     rdi
0x1801af30e  pop     rsi
0x1801af30f  pop     rbp
0x1801af310  retn
0x1801af312  mov     [rsp+1D0h+var_198], r12
0x1801af317  xorps   xmm0, xmm0
0x1801af31a  xor     eax, eax
0x1801af31c  movups  xmmword ptr [rbp+0D0h+hMem], xmm0
0x1801af320  mov     [rbp+0D0h+var_130], rax
0x1801af324  call    ?_InitClipboardFormats@@YAXXZ; _InitClipboardFormats(void)
0x1801af329  lea     r9, [rsp+1D0h+var_198]; struct _IDA **
0x1801af32e  lea     r8, [rbp+0D0h+hMem]; struct tagSTGMEDIUM *
0x1801af332  movzx   edx, cs:?g_cfHIDA_Storage@@3GA; unsigned __int16
0x1801af339  mov     rcx, rdi; struct IDataObject *
0x1801af33c  call    ?SHGetItemArrayFromDataObjEx@@YAJPEAUIDataObject@@GPEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObjEx(IDataObject *,ushort,tagSTGMEDIUM *,_IDA * *)
0x1801af341  test    eax, eax
0x1801af343  js      loc_1801AF62A
0x1801af349  mov     rcx, r12
0x1801af34c  mov     rsi, [rsp+1D0h+var_198]
0x1801af351  test    rsi, rsi
0x1801af354  jz      short loc_1801AF361
0x1801af356  cmp     [rsi], r12d
0x1801af359  jbe     short loc_1801AF361
0x1801af35b  mov     ecx, [rsi+8]
0x1801af35e  add     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1801af361  call    ?_IsValidID@CDrivesFolder@@CAPEFBUIDDRIVE@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CDrivesFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x1801af366  mov     r14, rax
0x1801af369  mov     edi, 1
0x1801af36e  test    rax, rax
0x1801af371  jz      loc_1801AF53C
0x1801af377  mov     r13d, [r15+0Ch]
0x1801af37b  xor     edx, edx; hFile
0x1801af37d  lea     r8d, [rdi+1]; dwFlags
0x1801af381  lea     rcx, aShell32Dll; "shell32.dll"
0x1801af388  call    cs:__imp_LoadLibraryExW
0x1801af38f  nop     dword ptr [rax+rax+00h]
0x1801af394  mov     rbx, rax
0x1801af397  mov     [rsp+1D0h+var_178], rax
0x1801af39c  mov     r9, r15
0x1801af39f  xor     r8d, r8d
0x1801af3a2  mov     edx, 0F7h
0x1801af3a7  mov     rcx, rax
0x1801af3aa  call    cs:__imp_SHELL32_CDefFolderMenu_MergeMenu
0x1801af3b1  nop     dword ptr [rax+rax+00h]
0x1801af3b6  mov     [rsp+1D0h+var_190], r12d
0x1801af3bb  mov     [rbp+0D0h+var_148], r12d
0x1801af3bf  mov     [rbp+0D0h+var_144], r12d
0x1801af3c3  mov     dword ptr [rsp+1D0h+var_198], r12d
0x1801af3c8  lea     rax, [r14+3]
0x1801af3cc  mov     [rsp+1D0h+pszPath], rax
0x1801af3d1  mov     rcx, rax; pszPath
0x1801af3d4  call    cs:__imp_PathGetDriveNumberA
0x1801af3db  nop     dword ptr [rax+rax+00h]
0x1801af3e0  test    eax, eax
0x1801af3e2  js      short loc_1801AF3FA
0x1801af3e4  lea     r8, [rbp+0D0h+var_144]
0x1801af3e8  lea     rdx, [rbp+0D0h+var_148]
0x1801af3ec  mov     ecx, eax
0x1801af3ee  call    cs:__imp_SHELL32_CDBurn_GetLiveFSDiscInfo
0x1801af3f5  nop     dword ptr [rax+rax+00h]
0x1801af3fa  cmp     [rsi], edi
0x1801af3fc  jnz     loc_1801AF58D
0x1801af402  cmp     [rbp+0D0h+var_148], r12d
0x1801af406  jz      loc_1801AF58D
0x1801af40c  cmp     [rsi], edi
0x1801af40e  jnz     loc_1801AF5C3
0x1801af414  cmp     [rbp+0D0h+var_144], r12d
0x1801af418  jz      loc_1801AF5C3
0x1801af41e  mov     [rsp+1D0h+var_188], r12
0x1801af423  lea     rdx, [rsp+1D0h+var_188]; struct CMountPoint **
0x1801af428  mov     rcx, r14; struct IDDRIVE *
0x1801af42b  call    ?_GetMountPoint@CDrivesFolder@@CAJPEFBUIDDRIVE@@PEAPEAVCMountPoint@@@Z; CDrivesFolder::_GetMountPoint(IDDRIVE const *,CMountPoint * *)
0x1801af430  test    eax, eax
0x1801af432  jns     short loc_1801AF47D
0x1801af434  lea     edx, [r13+9]; uPosition
0x1801af438  xor     r8d, r8d; uFlags
0x1801af43b  mov     rcx, [r15]; hMenu
0x1801af43e  call    cs:__imp_DeleteMenu
0x1801af445  nop     dword ptr [rax+rax+00h]
0x1801af44a  jmp     loc_1801AF502
0x1801af44f  sub     eax, r8d
0x1801af452  jz      loc_1801AF293
0x1801af458  sub     eax, r8d
0x1801af45b  jz      loc_1801AF293
0x1801af461  sub     eax, r8d
0x1801af464  jz      loc_1801AF293
0x1801af46a  cmp     eax, 1
0x1801af46d  jz      loc_1801AF293
0x1801af473  mov     edi, 80004001h
0x1801af478  jmp     loc_1801AF2E5
0x1801af47d  mov     r14, [rsp+1D0h+var_188]
0x1801af482  mov     rax, [r14]
0x1801af485  mov     rcx, r14
0x1801af488  mov     rax, [rax+168h]
0x1801af48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af494  test    eax, eax
0x1801af496  jnz     loc_1801AF632
0x1801af49c  cmp     [rsi], edi
0x1801af49e  jnz     short loc_1801AF4D4
0x1801af4a0  mov     rax, [r14]
0x1801af4a3  mov     rcx, r14
0x1801af4a6  mov     rax, [rax+1D0h]
0x1801af4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af4b2  test    eax, eax
0x1801af4b4  jz      short loc_1801AF4D4
0x1801af4b6  mov     rax, [r14]
0x1801af4b9  mov     rcx, r14
0x1801af4bc  mov     rax, [rax+188h]
0x1801af4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af4c8  test    eax, eax
0x1801af4ca  jnz     loc_1801AF647
0x1801af4d0  mov     dword ptr [rsp+1D0h+var_198], edi
0x1801af4d4  mov     rax, [r14]
0x1801af4d7  mov     rcx, r14
0x1801af4da  mov     rax, [rax+1E0h]
0x1801af4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af4e6  test    eax, eax
0x1801af4e8  jnz     loc_1801AF65E
0x1801af4ee  mov     rcx, r14; this
0x1801af4f1  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1801af4f6  test    r12d, r12d
0x1801af4f9  jz      loc_1801AF682
0x1801af4ff  xor     r12d, r12d
0x1801af502  cmp     dword ptr [rsp+1D0h+var_198], r12d
0x1801af507  jz      loc_1801AF5A8
0x1801af50d  cmp     [rsi], edi
0x1801af50f  jz      short loc_1801AF56F
0x1801af511  lea     edx, [r13+0Ah]; uPosition
0x1801af515  xor     r8d, r8d; uFlags
0x1801af518  mov     rcx, [r15]; hMenu
0x1801af51b  call    cs:__imp_DeleteMenu
0x1801af522  nop     dword ptr [rax+rax+00h]
0x1801af527  nop
0x1801af528  test    rbx, rbx
0x1801af52b  jz      short loc_1801AF53C
0x1801af52d  mov     rcx, rbx; hLibModule
0x1801af530  call    cs:__imp_FreeLibrary
0x1801af537  nop     dword ptr [rax+rax+00h]
0x1801af53c  mov     rcx, [rbp+0D0h+hMem+8]; hMem
0x1801af540  test    rcx, rcx
0x1801af543  jz      short loc_1801AF556
0x1801af545  cmp     dword ptr [rbp+0D0h+hMem], edi
0x1801af548  jnz     short loc_1801AF556
0x1801af54a  call    cs:__imp_GlobalUnlock
0x1801af551  nop     dword ptr [rax+rax+00h]
0x1801af556  lea     rcx, [rbp+0D0h+hMem]; LPSTGMEDIUM
0x1801af55a  call    cs:__imp_ReleaseStgMedium
0x1801af561  nop     dword ptr [rax+rax+00h]
0x1801af566  mov     edi, [rsp+1D0h+var_1A0]
0x1801af56a  jmp     loc_1801AF2E5
0x1801af56f  cmp     [rsp+1D0h+var_190], r12d
0x1801af574  jz      short loc_1801AF511
0x1801af576  mov     rcx, [rsp+1D0h+pszPath]; pszPath
0x1801af57b  call    cs:__imp_PathGetDriveNumberA
0x1801af582  nop     dword ptr [rax+rax+00h]
0x1801af587  test    eax, eax
0x1801af589  jns     short loc_1801AF528
0x1801af58b  jmp     short loc_1801AF511
0x1801af58d  lea     edx, [r13+3]; uPosition
0x1801af591  xor     r8d, r8d; uFlags
0x1801af594  mov     rcx, [r15]; hMenu
0x1801af597  call    cs:__imp_DeleteMenu
0x1801af59e  nop     dword ptr [rax+rax+00h]
0x1801af5a3  jmp     loc_1801AF40C
0x1801af5a8  lea     edx, [r13+8]; uPosition
0x1801af5ac  xor     r8d, r8d; uFlags
0x1801af5af  mov     rcx, [r15]; hMenu
0x1801af5b2  call    cs:__imp_DeleteMenu
0x1801af5b9  nop     dword ptr [rax+rax+00h]
0x1801af5be  jmp     loc_1801AF50D
0x1801af5c3  lea     edx, [r13+4]; uPosition
0x1801af5c7  xor     r8d, r8d; uFlags
0x1801af5ca  mov     rcx, [r15]; hMenu
0x1801af5cd  call    cs:__imp_DeleteMenu
0x1801af5d4  nop     dword ptr [rax+rax+00h]
0x1801af5d9  jmp     loc_1801AF41E
0x1801af5de  mov     rcx, r12; struct _ITEMIDLIST_RELATIVE *
0x1801af5e1  mov     rsi, [rsp+1D0h+var_198]
0x1801af5e6  test    rsi, rsi
0x1801af5e9  jz      loc_180670360
0x1801af5ef  cmp     [rsi], r12d
0x1801af5f2  jbe     loc_180670360
0x1801af5f8  mov     ecx, [rsi+8]
0x1801af5fb  add     rcx, rsi
0x1801af5fe  jmp     loc_180670360
0x1801af603  mov     [rsp+1D0h+var_198], r12
0x1801af608  xorps   xmm0, xmm0
0x1801af60b  xor     eax, eax
0x1801af60d  movups  xmmword ptr [rbp+0D0h+hMem], xmm0
0x1801af611  mov     [rbp+0D0h+var_130], rax
0x1801af615  lea     r8, [rsp+1D0h+var_198]; struct _IDA **
0x1801af61a  lea     rdx, [rbp+0D0h+hMem]; struct tagSTGMEDIUM *
0x1801af61e  mov     rcx, rdi; struct IDataObject *
0x1801af621  call    ?SHGetItemArrayFromDataObj@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObj(IDataObject *,tagSTGMEDIUM *,_IDA * *)
0x1801af626  test    eax, eax
0x1801af628  jns     short loc_1801AF5DE
0x1801af62a  mov     edi, r12d
0x1801af62d  jmp     loc_1801AF2E5
0x1801af632  mov     ecx, 8000000h; rest
0x1801af637  call    SHRestricted
0x1801af63c  test    eax, eax
0x1801af63e  cmovz   r12d, edi
0x1801af642  jmp     loc_1801AF49C
0x1801af647  mov     ecx, 40000057h; rest
0x1801af64c  call    SHRestricted
0x1801af651  test    eax, eax
0x1801af653  jnz     loc_1801AF4D4
0x1801af659  jmp     loc_1801AF4D0
0x1801af65e  mov     rax, [r14]
0x1801af661  mov     rcx, r14
0x1801af664  mov     rax, [rax+118h]
0x1801af66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af670  mov     ecx, [rsp+1D0h+var_190]
0x1801af674  test    eax, eax
0x1801af676  cmovz   ecx, edi
0x1801af679  mov     [rsp+1D0h+var_190], ecx
0x1801af67d  jmp     loc_1801AF4EE
0x1801af682  xor     r12d, r12d
0x1801af685  jmp     loc_1801AF434
0x180670360  call    ?_IsValidID@CDrivesFolder@@CAPEFBUIDDRIVE@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CDrivesFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x180670365  mov     rbx, rax
0x180670368  test    rax, rax
0x18067036b  jz      loc_18067061C
0x180670371  mov     rcx, [rbp+0D0h+arg_28]
0x180670378  cmp     rcx, 3
0x18067037c  jz      loc_1806705FA
0x180670382  cmp     rcx, 4
0x180670386  jz      loc_1806705D6
0x18067038c  cmp     rcx, 8
0x180670390  jz      loc_1806705A6
0x180670396  cmp     rcx, 9
0x18067039a  jz      loc_180670451
0x1806703a0  cmp     rcx, 0Ah
0x1806703a4  jz      short loc_1806703DA
0x1806703a6  mov     eax, 0FFFFFFFBh
0x1806703ab  cmp     rcx, rax
0x1806703ae  jz      short loc_1806703BA
0x1806703b0  mov     edi, 1
0x1806703b5  jmp     loc_18067061F
0x1806703ba  lea     r8, GUID_NULL
0x1806703c1  mov     rdx, r15
0x1806703c4  mov     rcx, rdi
0x1806703c7  call    cs:__imp_SHELL32_SHLaunchPropSheet
  ... truncated ...
```
