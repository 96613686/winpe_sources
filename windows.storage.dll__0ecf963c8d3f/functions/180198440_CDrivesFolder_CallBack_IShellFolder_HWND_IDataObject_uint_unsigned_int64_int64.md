# CDrivesFolder::CallBack(IShellFolder *,HWND__ *,IDataObject *,uint,unsigned __int64,__int64)

- ea: `0x180198440`
- end: `0x18019884b`
- name: `?CallBack@CDrivesFolder@@UEAAJPEAUIShellFolder@@PEAUHWND__@@PEAUIDataObject@@I_K_J@Z`
- size: `1035`
- prototype: `__int64 __fastcall(CDrivesFolder *this, struct IShellFolder *, HWND, struct IDataObject *, unsigned int, const void *, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, loader_planting, installer_update`

## callees

- `0x1800a3080`
- `0x1800aa710`
- `0x1800d7650`
- `0x18012fa50`
- `0x180130330`
- `0x18013046c`
- `0x180132790`
- `0x180198440`
- `0x180198854`
- `0x180198d5c`
- `0x180198da4`
- `0x180198e64`
- `0x1802d2644`
- `0x1803a4cb0`
- `0x1803a51c0`
- `0x1805c1518`
- `0x1805ce9c4`
- `0x180600c6c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801984bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18019859b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801984bc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18019859b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801984f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019871b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801984f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18019871b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1801985db`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x180198754`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064b917`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064bab3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064bad7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064baef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x1801985db`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x180198754`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064b917`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064bab3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064bad7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberA` at `0x18064baef`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019872f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18019872f`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x180198739`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x180198739`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x180198639`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x18019870c`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x18019876a`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x18019877f`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x180198794`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x180198639`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x18019870c`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x18019876a`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x18019877f`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x180198794`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHLaunchPropSheet` at `0x18064b8f5`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHLaunchPropSheet` at `0x18064b8f5`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHFormatDriveAsync` at `0x18064bacb`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHFormatDriveAsync` at `0x18064bacb`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x1801985b7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDefFolderMenu_MergeMenu` at `0x1801985b7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_GetLiveFSDiscInfo` at `0x1801985ef`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_GetLiveFSDiscInfo` at `0x1801985ef`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_OnEject` at `0x18064b926`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_OnEject` at `0x18064b926`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_Erase` at `0x18064bafb`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_Erase` at `0x18064bafb`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_CloseSession` at `0x18064bae3`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CDBurn_CloseSession` at `0x18064bae3`

## string_xrefs

- `0x1801984b5`: `shell32.dll`
- `0x180198594`: `shell32.dll`

## pseudocode

```c
__int64 __fastcall CDrivesFolder::CallBack(
        CDrivesFolder *this,
        struct IShellFolder *a2,
        HWND a3,
        struct IDataObject *a4,
        unsigned int a5,
        const void *a6,
        __int64 a7)
{
  struct IDataObject *v7; // rdi
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
  const struct IDDRIVE *v31; // r14
  CMountPoint *v32; // rbx
  int v33; // r15d
  __int64 v34; // rax
  int v35; // eax
  int v36; // eax
  int DriveNumberA; // eax
  struct _IDA *v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+40h] [rbp-C0h]
  CMountPoint *v40; // [rsp+48h] [rbp-B8h] BYREF
  LPCSTR pszPath; // [rsp+50h] [rbp-B0h]
  HMODULE v42; // [rsp+58h] [rbp-A8h]
  _QWORD v43[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+88h] [rbp-78h] BYREF
  int v47; // [rsp+8Ch] [rbp-74h] BYREF
  STGMEDIUM hMem; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v49[56]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR dwItem1[56]; // [rsp+120h] [rbp+20h] BYREF

  v7 = a4;
  v10 = 0;
  if ( a5 != 1 )
  {
    if ( a5 != 2 )
    {
      if ( a5 == 5 || a5 == 9 || a5 == 11 || a5 == 13 || a5 - 15 < 2 )
      {
        Library = LoadLibraryExW(L"shell32.dll", 0, 2u);
        v12 = HandleStandardDFM(Library, a5, (unsigned __int64)a6, a7, (const struct ICIVERBTOIDMAP *)&off_180675950);
        if ( Library )
          FreeLibrary(Library);
      }
      else
      {
        return (unsigned int)-2147467263;
      }
      return v12;
    }
    v38 = 0;
    memset(&hMem, 0, sizeof(hMem));
    if ( (int)SHGetItemArrayFromDataObj(a4, &hMem, &v38) < 0 )
      return 0;
    v21 = 0;
    v22 = v38;
    if ( v38 && v38->cidl )
      v21 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v38 + v38[1].cidl);
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
        v36 = PathGetDriveNumberA((LPCSTR)v25 + 3);
        if ( v36 >= 0 )
          SHELL32_CDBurn_CloseSession((unsigned int)v36);
      }
      else if ( a6 == (const void *)8 )
      {
        v35 = PathGetDriveNumberA((LPCSTR)v25 + 3);
        if ( v35 >= 0 )
          SHELL32_SHFormatDriveAsync(a3, (unsigned int)v35, 0xFFFF, 0);
      }
      else if ( a6 == (const void *)9 )
      {
        Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 9), 13633, v27, v7);
        v43[0] = 40;
        v43[1] = a3;
        v44 = 0;
        v45 = 1;
        LODWORD(v7) = 0;
        while ( (unsigned int)v7 < v22->cidl )
        {
          v7 = (struct IDataObject *)(unsigned int)((_DWORD)v7 + 1);
          v31 = CDrivesFolder::_IsValidID((const struct _ITEMIDLIST_RELATIVE *)((char *)v22 + v22->aoffset[(_QWORD)v7]));
          v38 = 0;
          if ( CDrivesFolder::_GetMountPoint(v31, (struct CMountPoint **)&v38) >= 0 )
          {
            v32 = (CMountPoint *)v38;
            if ( (*(unsigned int (__fastcall **)(struct _IDA *))(*(_QWORD *)v38 + 360LL))(v38) )
            {
              v33 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)v32 + 336LL))(v32);
              CDrivesFolder::_GetParsingName(v31, v49, 0x32u);
              StringCchCopyW(dwItem1, 0x32u, v49);
              v34 = -1;
              do
                ++v34;
              while ( v49[v34] );
              if ( (_DWORD)v34 )
              {
                if ( 2 * (unsigned __int64)(unsigned int)(v34 - 1) >= 0x64 )
                  _report_rangecheckfailure();
                v49[(unsigned int)(v34 - 1)] = 0;
              }
              *(_QWORD *)&v44 = v49;
              if ( !(unsigned int)SHWNetDisconnectDialog1(v43) && v33 )
              {
                CMountPoint::NotifyUnavailableNetDriveGone(dwItem1);
                SHChangeNotify(128, 5u, dwItem1, 0);
              }
            }
            CMountPoint::Release(v32);
          }
        }
        SHChangeNotify(0, 0x1000u, 0, 0);
      }
      else
      {
        if ( a6 != (const void *)10 )
        {
          if ( a6 == (const void *)4294967291LL )
            v12 = SHELL32_SHLaunchPropSheet(v7, a7, &GUID_NULL);
          else
            v12 = 1;
          goto LABEL_96;
        }
        Fire_ExplorerTelemetryFromSiteWithDataObject(*((_QWORD *)this - 9), 15425, v27, v7);
        v29 = PathGetDriveNumberA((LPCSTR)v28 + 3);
        if ( v29 >= 0 )
          SHELL32_CDBurn_OnEject(a3, (unsigned int)v29);
        v38 = 0;
        if ( CDrivesFolder::_GetMountPoint(v28, (struct CMountPoint **)&v38) >= 0 )
        {
          v30 = (CMountPoint *)v38;
          (*(void (__fastcall **)(struct _IDA *, HWND))(*(_QWORD *)v38 + 272LL))(v38, a3);
          CMountPoint::Release(v30);
        }
      }
    }
    v12 = 0;
LABEL_96:
    ReleaseStgMediumHGLOBAL(v26, &hMem);
    return v12;
  }
  v38 = 0;
  memset(&hMem, 0, sizeof(hMem));
  _InitClipboardFormats();
  if ( SHGetItemArrayFromDataObjEx(v7, g_cfHIDA_Storage, &hMem, &v38) < 0 )
    return 0;
  v14 = 0;
  v15 = v38;
  if ( v38 && v38->cidl )
    v14 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v38 + v38[1].cidl);
  v16 = CDrivesFolder::_IsValidID(v14);
  if ( v16 )
  {
    v17 = *(_DWORD *)(a7 + 12);
    v18 = LoadLibraryExW(L"shell32.dll", 0, 2u);
    v42 = v18;
    SHELL32_CDefFolderMenu_MergeMenu(v18, 247, 0, a7);
    v39 = 0;
    v46 = 0;
    v47 = 0;
    LODWORD(v38) = 0;
    pszPath = (char *)v16 + 3;
    v19 = PathGetDriveNumberA((LPCSTR)v16 + 3);
    if ( v19 >= 0 )
      SHELL32_CDBurn_GetLiveFSDiscInfo((unsigned int)v19, &v46, &v47);
    if ( v15->cidl != 1 || !v46 )
      DeleteMenu(*(HMENU *)a7, v17 + 3, 0);
    if ( v15->cidl != 1 || !v47 )
      DeleteMenu(*(HMENU *)a7, v17 + 4, 0);
    v40 = 0;
    if ( CDrivesFolder::_GetMountPoint(v16, &v40) < 0 )
      goto LABEL_20;
    v20 = v40;
    if ( (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v40 + 360LL))(v40)
      && !SHRestricted(REST_NONETCONNECTDISCONNECT) )
    {
      v10 = 1;
    }
    if ( v15->cidl == 1
      && (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 464LL))(v20)
      && (!(*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 392LL))(v20)
       || !SHRestricted(REST_NOCDBURNING)) )
    {
      LODWORD(v38) = 1;
    }
    if ( (*(unsigned int (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 480LL))(v20) )
    {
      v23 = (*(__int64 (__fastcall **)(CMountPoint *))(*(_QWORD *)v20 + 280LL))(v20);
      v24 = v39;
      if ( !v23 )
        v24 = 1;
      v39 = v24;
    }
    CMountPoint::Release(v20);
    if ( !v10 )
LABEL_20:
      DeleteMenu(*(HMENU *)a7, v17 + 9, 0);
    if ( !(_DWORD)v38 )
      DeleteMenu(*(HMENU *)a7, v17 + 8, 0);
    if ( v15->cidl != 1 || !v39 || PathGetDriveNumberA(pszPath) < 0 )
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
0x180198440  mov     [rsp-8+arg_8], rbx
0x180198445  push    rbp
0x180198446  push    rsi
0x180198447  push    rdi
0x180198448  push    r12
0x18019844a  push    r13
0x18019844c  push    r14
0x18019844e  push    r15
0x180198450  lea     rbp, [rsp-0A0h]
0x180198458  sub     rsp, 1A0h
0x18019845f  mov     rax, cs:__security_cookie
0x180198466  xor     rax, rsp
0x180198469  mov     [rbp+0D0h+var_40], rax
0x180198470  mov     rdi, r9
0x180198473  mov     r14, r8
0x180198476  mov     r13, rcx
0x180198479  mov     r15, [rbp+0D0h+arg_30]
0x180198480  xor     r12d, r12d
0x180198483  mov     [rsp+1D0h+var_1A0], r12d
0x180198488  mov     eax, [rbp+0D0h+arg_20]
0x18019848e  sub     eax, 1
0x180198491  jz      loc_180198525
0x180198497  sub     eax, 1
0x18019849a  jz      loc_1801987C4
0x1801984a0  lea     r8d, [r12+2]; dwFlags
0x1801984a5  sub     eax, 3
0x1801984a8  jz      short loc_1801984B3
0x1801984aa  sub     eax, 4
0x1801984ad  jnz     loc_180198644
0x1801984b3  xor     edx, edx; hFile
0x1801984b5  lea     rcx, aShell32Dll; "shell32.dll"
0x1801984bc  call    cs:__imp_LoadLibraryExW
0x1801984c2  mov     rbx, rax
0x1801984c5  lea     rax, off_180675950; "format"
0x1801984cc  mov     [rsp+1D0h+var_1B0], rax; struct ICIVERBTOIDMAP *
0x1801984d1  mov     r9, r15; __int64
0x1801984d4  mov     r8, [rbp+0D0h+arg_28]; unsigned __int64
0x1801984db  mov     edx, [rbp+0D0h+arg_20]; unsigned int
0x1801984e1  mov     rcx, rbx; HINSTANCE
0x1801984e4  call    ?HandleStandardDFM@@YAJPEAUHINSTANCE__@@I_K_JPEBUICIVERBTOIDMAP@@@Z; HandleStandardDFM(HINSTANCE__ *,uint,unsigned __int64,__int64,ICIVERBTOIDMAP const *)
0x1801984e9  mov     edi, eax
0x1801984eb  test    rbx, rbx
0x1801984ee  jz      short loc_1801984F9
0x1801984f0  mov     rcx, rbx; hLibModule
0x1801984f3  call    cs:__imp_FreeLibrary
0x1801984f9  mov     eax, edi
0x1801984fb  mov     rcx, [rbp+0D0h+var_40]
0x180198502  xor     rcx, rsp; StackCookie
0x180198505  call    __security_check_cookie
0x18019850a  mov     rbx, [rsp+1D0h+arg_8]
0x180198512  add     rsp, 1A0h
0x180198519  pop     r15
0x18019851b  pop     r14
0x18019851d  pop     r13
0x18019851f  pop     r12
0x180198521  pop     rdi
0x180198522  pop     rsi
0x180198523  pop     rbp
0x180198524  retn
0x180198525  mov     [rsp+1D0h+var_198], r12
0x18019852a  xorps   xmm0, xmm0
0x18019852d  xor     eax, eax
0x18019852f  movups  xmmword ptr [rbp+0D0h+hMem], xmm0
0x180198533  mov     [rbp+0D0h+var_130], rax
0x180198537  call    ?_InitClipboardFormats@@YAXXZ; _InitClipboardFormats(void)
0x18019853c  lea     r9, [rsp+1D0h+var_198]; struct _IDA **
0x180198541  lea     r8, [rbp+0D0h+hMem]; struct tagSTGMEDIUM *
0x180198545  movzx   edx, cs:?g_cfHIDA_Storage@@3GA; unsigned __int16
0x18019854c  mov     rcx, rdi; struct IDataObject *
0x18019854f  call    ?SHGetItemArrayFromDataObjEx@@YAJPEAUIDataObject@@GPEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObjEx(IDataObject *,ushort,tagSTGMEDIUM *,_IDA * *)
0x180198554  test    eax, eax
0x180198556  js      loc_1801987EB
0x18019855c  mov     rcx, r12
0x18019855f  mov     rsi, [rsp+1D0h+var_198]
0x180198564  test    rsi, rsi
0x180198567  jz      short loc_180198574
0x180198569  cmp     [rsi], r12d
0x18019856c  jbe     short loc_180198574
0x18019856e  mov     ecx, [rsi+8]
0x180198571  add     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x180198574  call    ?_IsValidID@CDrivesFolder@@CAPEFBUIDDRIVE@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CDrivesFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x180198579  mov     r14, rax
0x18019857c  mov     edi, 1
0x180198581  test    rax, rax
0x180198584  jz      loc_180198721
0x18019858a  mov     r13d, [r15+0Ch]
0x18019858e  xor     edx, edx; hFile
0x180198590  lea     r8d, [rdi+1]; dwFlags
0x180198594  lea     rcx, aShell32Dll; "shell32.dll"
0x18019859b  call    cs:__imp_LoadLibraryExW
0x1801985a1  mov     rbx, rax
0x1801985a4  mov     [rsp+1D0h+var_178], rax
0x1801985a9  mov     r9, r15
0x1801985ac  xor     r8d, r8d
0x1801985af  mov     edx, 0F7h
0x1801985b4  mov     rcx, rax
0x1801985b7  call    cs:__imp_SHELL32_CDefFolderMenu_MergeMenu
0x1801985bd  mov     [rsp+1D0h+var_190], r12d
0x1801985c2  mov     [rbp+0D0h+var_148], r12d
0x1801985c6  mov     [rbp+0D0h+var_144], r12d
0x1801985ca  mov     dword ptr [rsp+1D0h+var_198], r12d
0x1801985cf  lea     rax, [r14+3]
0x1801985d3  mov     [rsp+1D0h+pszPath], rax
0x1801985d8  mov     rcx, rax; pszPath
0x1801985db  call    cs:__imp_PathGetDriveNumberA
0x1801985e1  test    eax, eax
0x1801985e3  js      short loc_1801985F5
0x1801985e5  lea     r8, [rbp+0D0h+var_144]
0x1801985e9  lea     rdx, [rbp+0D0h+var_148]
0x1801985ed  mov     ecx, eax
0x1801985ef  call    cs:__imp_SHELL32_CDBurn_GetLiveFSDiscInfo
0x1801985f5  cmp     [rsi], edi
0x1801985f7  jnz     loc_180198760
0x1801985fd  cmp     [rbp+0D0h+var_148], r12d
0x180198601  jz      loc_180198760
0x180198607  cmp     [rsi], edi
0x180198609  jnz     loc_18019878A
0x18019860f  cmp     [rbp+0D0h+var_144], r12d
0x180198613  jz      loc_18019878A
0x180198619  mov     [rsp+1D0h+var_188], r12
0x18019861e  lea     rdx, [rsp+1D0h+var_188]; struct CMountPoint **
0x180198623  mov     rcx, r14; struct IDDRIVE *
0x180198626  call    ?_GetMountPoint@CDrivesFolder@@CAJPEFBUIDDRIVE@@PEAPEAVCMountPoint@@@Z; CDrivesFolder::_GetMountPoint(IDDRIVE const *,CMountPoint * *)
0x18019862b  test    eax, eax
0x18019862d  jns     short loc_180198672
0x18019862f  lea     edx, [r13+9]; uPosition
0x180198633  xor     r8d, r8d; uFlags
0x180198636  mov     rcx, [r15]; hMenu
0x180198639  call    cs:__imp_DeleteMenu
0x18019863f  jmp     loc_1801986F7
0x180198644  sub     eax, r8d
0x180198647  jz      loc_1801984B3
0x18019864d  sub     eax, r8d
0x180198650  jz      loc_1801984B3
0x180198656  sub     eax, r8d
0x180198659  jz      loc_1801984B3
0x18019865f  cmp     eax, 1
0x180198662  jz      loc_1801984B3
0x180198668  mov     edi, 80004001h
0x18019866d  jmp     loc_1801984F9
0x180198672  mov     r14, [rsp+1D0h+var_188]
0x180198677  mov     rax, [r14]
0x18019867a  mov     rcx, r14
0x18019867d  mov     rax, [rax+168h]
0x180198684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198689  test    eax, eax
0x18019868b  jnz     loc_1801987F3
0x180198691  cmp     [rsi], edi
0x180198693  jnz     short loc_1801986C9
0x180198695  mov     rax, [r14]
0x180198698  mov     rcx, r14
0x18019869b  mov     rax, [rax+1D0h]
0x1801986a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986a7  test    eax, eax
0x1801986a9  jz      short loc_1801986C9
0x1801986ab  mov     rax, [r14]
0x1801986ae  mov     rcx, r14
0x1801986b1  mov     rax, [rax+188h]
0x1801986b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986bd  test    eax, eax
0x1801986bf  jnz     loc_180198808
0x1801986c5  mov     dword ptr [rsp+1D0h+var_198], edi
0x1801986c9  mov     rax, [r14]
0x1801986cc  mov     rcx, r14
0x1801986cf  mov     rax, [rax+1E0h]
0x1801986d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801986db  test    eax, eax
0x1801986dd  jnz     loc_18019881F
0x1801986e3  mov     rcx, r14; this
0x1801986e6  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1801986eb  test    r12d, r12d
0x1801986ee  jz      loc_180198843
0x1801986f4  xor     r12d, r12d
0x1801986f7  cmp     dword ptr [rsp+1D0h+var_198], r12d
0x1801986fc  jz      short loc_180198775
0x1801986fe  cmp     [rsi], edi
0x180198700  jz      short loc_180198748
0x180198702  lea     edx, [r13+0Ah]; uPosition
0x180198706  xor     r8d, r8d; uFlags
0x180198709  mov     rcx, [r15]; hMenu
0x18019870c  call    cs:__imp_DeleteMenu
0x180198712  nop
0x180198713  test    rbx, rbx
0x180198716  jz      short loc_180198721
0x180198718  mov     rcx, rbx; hLibModule
0x18019871b  call    cs:__imp_FreeLibrary
0x180198721  mov     rcx, [rbp+0D0h+hMem+8]; hMem
0x180198725  test    rcx, rcx
0x180198728  jz      short loc_180198735
0x18019872a  cmp     dword ptr [rbp+0D0h+hMem], edi
0x18019872d  jnz     short loc_180198735
0x18019872f  call    cs:__imp_GlobalUnlock
0x180198735  lea     rcx, [rbp+0D0h+hMem]; LPSTGMEDIUM
0x180198739  call    cs:__imp_ReleaseStgMedium
0x18019873f  mov     edi, [rsp+1D0h+var_1A0]
0x180198743  jmp     loc_1801984F9
0x180198748  cmp     [rsp+1D0h+var_190], r12d
0x18019874d  jz      short loc_180198702
0x18019874f  mov     rcx, [rsp+1D0h+pszPath]; pszPath
0x180198754  call    cs:__imp_PathGetDriveNumberA
0x18019875a  test    eax, eax
0x18019875c  jns     short loc_180198713
0x18019875e  jmp     short loc_180198702
0x180198760  lea     edx, [r13+3]; uPosition
0x180198764  xor     r8d, r8d; uFlags
0x180198767  mov     rcx, [r15]; hMenu
0x18019876a  call    cs:__imp_DeleteMenu
0x180198770  jmp     loc_180198607
0x180198775  lea     edx, [r13+8]; uPosition
0x180198779  xor     r8d, r8d; uFlags
0x18019877c  mov     rcx, [r15]; hMenu
0x18019877f  call    cs:__imp_DeleteMenu
0x180198785  jmp     loc_1801986FE
0x18019878a  lea     edx, [r13+4]; uPosition
0x18019878e  xor     r8d, r8d; uFlags
0x180198791  mov     rcx, [r15]; hMenu
0x180198794  call    cs:__imp_DeleteMenu
0x18019879a  jmp     loc_180198619
0x18019879f  mov     rcx, r12; struct _ITEMIDLIST_RELATIVE *
0x1801987a2  mov     rsi, [rsp+1D0h+var_198]
0x1801987a7  test    rsi, rsi
0x1801987aa  jz      loc_18064B88E
0x1801987b0  cmp     [rsi], r12d
0x1801987b3  jbe     loc_18064B88E
0x1801987b9  mov     ecx, [rsi+8]
0x1801987bc  add     rcx, rsi
0x1801987bf  jmp     loc_18064B88E
0x1801987c4  mov     [rsp+1D0h+var_198], r12
0x1801987c9  xorps   xmm0, xmm0
0x1801987cc  xor     eax, eax
0x1801987ce  movups  xmmword ptr [rbp+0D0h+hMem], xmm0
0x1801987d2  mov     [rbp+0D0h+var_130], rax
0x1801987d6  lea     r8, [rsp+1D0h+var_198]; struct _IDA **
0x1801987db  lea     rdx, [rbp+0D0h+hMem]; struct tagSTGMEDIUM *
0x1801987df  mov     rcx, rdi; struct IDataObject *
0x1801987e2  call    ?SHGetItemArrayFromDataObj@@YAJPEAUIDataObject@@PEAUtagSTGMEDIUM@@PEAPEAU_IDA@@@Z; SHGetItemArrayFromDataObj(IDataObject *,tagSTGMEDIUM *,_IDA * *)
0x1801987e7  test    eax, eax
0x1801987e9  jns     short loc_18019879F
0x1801987eb  mov     edi, r12d
0x1801987ee  jmp     loc_1801984F9
0x1801987f3  mov     ecx, 8000000h; rest
0x1801987f8  call    SHRestricted
0x1801987fd  test    eax, eax
0x1801987ff  cmovz   r12d, edi
0x180198803  jmp     loc_180198691
0x180198808  mov     ecx, 40000057h; rest
0x18019880d  call    SHRestricted
0x180198812  test    eax, eax
0x180198814  jnz     loc_1801986C9
0x18019881a  jmp     loc_1801986C5
0x18019881f  mov     rax, [r14]
0x180198822  mov     rcx, r14
0x180198825  mov     rax, [rax+118h]
0x18019882c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198831  mov     ecx, [rsp+1D0h+var_190]
0x180198835  test    eax, eax
0x180198837  cmovz   ecx, edi
0x18019883a  mov     [rsp+1D0h+var_190], ecx
0x18019883e  jmp     loc_1801986E3
0x180198843  xor     r12d, r12d
0x180198846  jmp     loc_18019862F
0x18064b88e  call    ?_IsValidID@CDrivesFolder@@CAPEFBUIDDRIVE@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CDrivesFolder::_IsValidID(_ITEMIDLIST_RELATIVE const *)
0x18064b893  mov     rbx, rax
0x18064b896  test    rax, rax
0x18064b899  jz      loc_18064BB01
0x18064b89f  mov     rcx, [rbp+0D0h+arg_28]
0x18064b8a6  cmp     rcx, 3
0x18064b8aa  jz      loc_18064BAEB
0x18064b8b0  cmp     rcx, 4
0x18064b8b4  jz      loc_18064BAD3
0x18064b8ba  cmp     rcx, 8
0x18064b8be  jz      loc_18064BAAF
0x18064b8c4  cmp     rcx, 9
0x18064b8c8  jz      loc_18064B96D
0x18064b8ce  cmp     rcx, 0Ah
0x18064b8d2  jz      short loc_18064B902
0x18064b8d4  mov     eax, 0FFFFFFFBh
0x18064b8d9  cmp     rcx, rax
0x18064b8dc  jz      short loc_18064B8E8
0x18064b8de  mov     edi, 1
0x18064b8e3  jmp     loc_18064BB04
0x18064b8e8  lea     r8, GUID_NULL
0x18064b8ef  mov     rdx, r15
0x18064b8f2  mov     rcx, rdi
0x18064b8f5  call    cs:__imp_SHELL32_SHLaunchPropSheet
0x18064b8fb  mov     edi, eax
0x18064b8fd  jmp     loc_18064BB04
0x18064b902  mov     r9, rdi
0x18064b905  mov     edx, 3C41h
0x18064b90a  mov     rcx, [r13-48h]
0x18064b90e  call    ?Fire_ExplorerTelemetryFromSiteWithDataObject@@YAXPEAUIUnknown@@W4EXPLORER_COMMAND_SQM_ID@@W4EXPLORER_COMMAND_SQM_SELECTED_STATE@@PEAUIDataObject@@@Z; Fire_ExplorerTelemetryFromSiteWithDataObject(IUnknown *,EXPLORER_COMMAND_SQM_ID,EXPLORER_COMMAND_SQM_SELECTED_STATE,IDataObject *)
0x18064b913  lea     rcx, [rbx+3]; pszPath
0x18064b917  call    cs:__imp_PathGetDriveNumberA
0x18064b91d  test    eax, eax
0x18064b91f  js      short loc_18064B92C
0x18064b921  mov     edx, eax
0x18064b923  mov     rcx, r14
0x18064b926  call    cs:__imp_SHELL32_CDBurn_OnEject
0x18064b92c  mov     [rsp+1D0h+var_198], r12
0x18064b931  lea     rdx, [rsp+1D0h+var_198]; struct CMountPoint **
  ... truncated ...
```
