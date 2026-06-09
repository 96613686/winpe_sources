# CDrivesFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x18012eaa0`
- end: `0x18012f608`
- name: `?ParseDisplayName@CDrivesFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `2920`
- prototype: `int(CDrivesFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x18004bb30`
- `0x1800d3ba0`
- `0x1800d3d10`
- `0x1800d3dc0`
- `0x1801279b0`
- `0x18012d080`
- `0x18012eaa0`
- `0x18012f610`
- `0x18012f9d0`
- `0x18012fa08`
- `0x18012fa50`
- `0x18012fcb0`
- `0x180131564`
- `0x180132790`
- `0x18016cd40`
- `0x1801b7428`
- `0x1801ed410`
- `0x1802ac0a0`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ee57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012ee57`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18012ece3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18012ece3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18012ebb6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18012ebb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012ed33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012ed33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012ee99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012efb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012efbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f2ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f417`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f4fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012ee99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012efb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012efbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f2ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f417`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012f4fd`
- `SHCORE!__imp_GUIDFromStringW` at `0x18012ef02`
- `SHCORE!__imp_GUIDFromStringW` at `0x18012ef02`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18012eb9c`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x18012eb9c`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootA` at `0x18012ec1f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootA` at `0x18012ec1f`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18012f3d7`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x18012f3d7`

## string_xrefs

- `0x18012eb90`: `SHBindCtxPathType`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDrivesFolder::ParseDisplayName(
        IBindCtx *this,
        struct _ITEMID_CHILD *a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  struct IBindCtx *v8; // r12
  LPBC v9; // r15
  volatile __int64 *v10; // r13
  HRESULT FileSysFolder; // edi
  int v12; // ebx
  unsigned int DriveNumberW; // r14d
  __int64 v14; // rbx
  BOOL v15; // r15d
  unsigned __int16 *v16; // rsi
  struct IBindCtxVtbl *lpVtbl; // rcx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // r12
  __int64 v20; // r8
  CMountPoint *v21; // rcx
  int MountPointForDriveLetter; // r12d
  bool v23; // sf
  void *v24; // rcx
  char *v26; // rax
  char *v27; // r12
  IPropertyBag *v28; // rdx
  unsigned __int16 *v29; // r9
  char v30; // cl
  __int16 v31; // dx
  _BYTE *v32; // rax
  struct IBindCtxVtbl *v33; // r14
  unsigned int v34; // r15d
  _WORD *v35; // r13
  struct IBindCtxVtbl *v36; // rdx
  unsigned int v37; // ebx
  __int64 QueryInterface_low; // rcx
  unsigned int v39; // edi
  struct IBindCtx *v40; // r14
  void *v41; // rsi
  void *v42; // r14
  unsigned __int16 *v43; // rdx
  int v44; // r8d
  __int64 v45; // rcx
  __int64 v46; // rdi
  unsigned __int16 *v47; // rdx
  __int64 v48; // rcx
  unsigned int v49; // r12d
  char *v50; // rax
  char *v51; // rsi
  size_t v52; // rbx
  const struct IDDRIVE *v53; // r12
  int inited; // eax
  CDrivesFolder *v55; // r13
  const struct IDDRIVE *v56; // r12
  int v57; // eax
  LPITEMIDLIST v58; // rcx
  LPBC v59; // rcx
  struct _ITEMID_CHILD *v60; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int *v61; // [rsp+50h] [rbp-B0h]
  LPBC ppbc; // [rsp+58h] [rbp-A8h] BYREF
  IPropertyBag *propBag; // [rsp+60h] [rbp-A0h] BYREF
  CMountPoint *v64; // [rsp+68h] [rbp-98h] BYREF
  LPITEMIDLIST ppidl; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  DWORD value; // [rsp+80h] [rbp-80h] BYREF
  struct IBindCtx *v68; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v69; // [rsp+90h] [rbp-70h] BYREF
  CHAR pszRoot[16]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v71[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszName[264]; // [rsp+D0h] [rbp-30h] BYREF

  v8 = a3;
  v68 = a3;
  v60 = a2;
  v9 = this;
  ppbc = this;
  v10 = (volatile __int64 *)a6;
  v61 = a7;
  FileSysFolder = -2147024809;
  if ( !a6 )
    return (unsigned int)FileSysFolder;
  *(_OWORD *)pszRoot = 0;
  memset(v71, 0, 27);
  *a6 = 0;
  if ( !a4 )
  {
LABEL_46:
    v24 = (void *)_InterlockedExchange64(v10, 0);
    if ( v24 )
      CoTaskMemFree(v24);
    return (unsigned int)FileSysFolder;
  }
  value = 0;
  propBag = 0;
  ppidl = 0;
  if ( a3 )
  {
    if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, LPITEMIDLIST *))a3->lpVtbl->GetObjectParam)(
           a3,
           L"SHBindCtxPropertyBag",
           &ppidl) >= 0 )
    {
      v12 = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, IPropertyBag **))&ppidl->mkid.cb)(
              ppidl,
              &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
              &propBag);
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
      if ( v12 >= 0 )
      {
        PSPropertyBag_ReadDWORD(propBag, L"SHBindCtxPathType", &value);
        ((void (__fastcall *)(IPropertyBag *))propBag->lpVtbl->Release)(propBag);
      }
    }
  }
  DriveNumberW = PathGetDriveNumberW(a4);
  v14 = 4;
  if ( DriveNumberW == -1 )
  {
    if ( value != 22 )
      goto LABEL_46;
    v69 = 0;
    if ( !(unsigned int)GUIDFromStringW(a4 + 10) )
      goto LABEL_46;
    *(_OWORD *)pszRoot = 0;
    memset(v71, 0, 27);
    if ( !(unsigned int)BindCtx_ContainsObject(v8, L"File System Bind Data") && (BindCtx_GetMode(v8, 0) & 0x1000) == 0 )
    {
      FileSysFolder = -2147024881;
      v64 = 0;
      if ( (int)CMountPoint::GetSimulatedMountPointFromVolumeGuid(a4, &v64) < 0 )
        goto LABEL_58;
      CMountPoint::Release(v64);
    }
    strcpy(pszRoot, ")");
    pszRoot[2] = 33;
    *(struct _GUID *)((char *)v71 + 9) = v69;
    FileSysFolder = 0;
LABEL_58:
    v16 = a4 + 48;
    goto LABEL_23;
  }
  FileSysFolder = 0;
  v15 = 0;
  if ( v8 )
  {
    *(_QWORD *)&v69.Data1 = 16;
    *(_QWORD *)v69.Data4 = 0;
    if ( ((int (__fastcall *)(struct IBindCtx *, struct _GUID *))v8->lpVtbl->GetBindOptions)(v8, &v69) >= 0 )
      v15 = *(_DWORD *)&v69.Data2 == 2;
  }
  *(_OWORD *)pszRoot = 0;
  memset(v71, 0, 27);
  PathBuildRootA(&pszRoot[3], DriveNumberW);
  v64 = 0;
  if ( !v8 )
    goto LABEL_37;
  if ( ((int (__fastcall *)(struct IBindCtx *, const unsigned __int16 *, CMountPoint **))v8->lpVtbl->GetObjectParam)(
         v8,
         L"File System Bind Data",
         &v64) >= 0 )
  {
    (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v64 + 16LL))(v64);
    goto LABEL_14;
  }
  v69.Data1 = 16;
  *(_QWORD *)&v69.Data2 = 0;
  *(_DWORD *)&v69.Data4[4] = 0;
  if ( ((int (__fastcall *)(struct IBindCtx *, struct _GUID *))v8->lpVtbl->GetBindOptions)(v8, &v69) < 0
    || (*(_WORD *)v69.Data4 & 0x1000) == 0 )
  {
LABEL_37:
    FileSysFolder = -2147024881;
    propBag = 0;
    Microsoft::WRL::ComPtr<CMtPtLocal>::InternalRelease(&propBag);
    v21 = 0;
    propBag = 0;
    MountPointForDriveLetter = -2147024809;
    if ( DriveNumberW <= 0x19 )
    {
      CCritSecDelayInitBase::Enter(&Parameter);
      MountPointForDriveLetter = -2147467260;
      if ( !HIDWORD(qword_1808041C0) )
        MountPointForDriveLetter = CMountPoint::_GetMountPointForDriveLetter(
                                     DriveNumberW,
                                     (struct CMountPoint **)&propBag);
      LeaveCriticalSection(&Parameter);
      v21 = (CMountPoint *)propBag;
    }
    if ( v21 )
    {
      propBag = 0;
      CMountPoint::Release(v21);
    }
    v23 = MountPointForDriveLetter < 0;
    v8 = v68;
    if ( v23 )
      goto LABEL_19;
    FileSysFolder = 0;
  }
LABEL_14:
  *(_WORD *)pszRoot = 25;
  pszRoot[2] = 47;
  v69 = 0;
  if ( !v15 && (int)CMountPoint::GetDriveJunctionCLSID(DriveNumberW, &v69) >= 0 )
  {
    *(struct _GUID *)((char *)v71 + 9) = v69;
    strcpy(pszRoot, ")");
    *(_WORD *)((char *)v71 + 7) = 257;
  }
  v64 = 0;
  if ( !v8
    || ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, CMountPoint **))v8->lpVtbl->GetObjectParam)(
         v8,
         L"FailIfDriveHasNoMedia",
         &v64) < 0 )
  {
LABEL_19:
    v9 = ppbc;
    goto LABEL_20;
  }
  (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v64 + 16LL))(v64);
  v9 = ppbc;
  if ( (unsigned int)CDrivesFolder::_GetDriveVisibility(&ppbc[-6], pszRoot) )
  {
    FileSysFolder = -2147020578;
    goto LABEL_46;
  }
LABEL_20:
  if ( value == 18 )
  {
    v16 = a4 + 6;
  }
  else if ( StrCmpNICW(a4, L"\\\\?\\", 4) )
  {
    v16 = a4 + 2;
  }
  else
  {
    if ( (value & 0x10) == 0 )
    {
LABEL_117:
      FileSysFolder = -2147024809;
      goto LABEL_46;
    }
    SHSetPathTypeBindCtx(v8, 0x12u);
    v16 = a4 + 6;
  }
LABEL_23:
  if ( FileSysFolder < 0 )
    goto LABEL_46;
  Src = &v9[-6];
  if ( HIDWORD(v9[22].lpVtbl) == 1 && (unsigned int)CDrivesFolder::_GetDriveVisibility(&v9[-6], pszRoot) )
    goto LABEL_117;
  ppbc = 0;
  *a6 = 0;
  lpVtbl = v9[21].lpVtbl;
  if ( !lpVtbl )
  {
    v18 = (unsigned __int16 *)CoTaskMemAlloc(0x2Fu);
    if ( v18 )
    {
      *(_OWORD *)v18 = *(_OWORD *)pszRoot;
      *((_OWORD *)v18 + 1) = v71[0];
      *(_OWORD *)((char *)v18 + 27) = *(_OWORD *)((char *)v71 + 11);
      goto LABEL_28;
    }
LABEL_59:
    *a6 = 0;
    FileSysFolder = -2147024882;
LABEL_45:
    v10 = (volatile __int64 *)a6;
    goto LABEL_46;
  }
  v18 = (unsigned __int16 *)(*((__int64 (__fastcall **)(struct IBindCtxVtbl *, __int64))lpVtbl->QueryInterface + 3))(
                              lpVtbl,
                              47);
  if ( !v18 )
    goto LABEL_59;
  *(_DWORD *)(v18 + 3) = -173623536;
  *(_OWORD *)(v18 + 5) = *(_OWORD *)pszRoot;
  *(_OWORD *)(v18 + 13) = v71[0];
  *(_OWORD *)((char *)v18 + 37) = *(_OWORD *)((char *)v71 + 11);
LABEL_28:
  v19 = v18;
  ppbc = (LPBC)v18;
  *a6 = (struct _ITEMIDLIST_RELATIVE *)v18;
  if ( *v16 == 92 )
  {
    *(_QWORD *)&v69.Data1 = v16 + 1;
    if ( v16[1] )
    {
      propBag = 0;
      v20 = *v18;
      if ( (unsigned int)v20 < 0x19 )
        goto LABEL_34;
      if ( (v18[1] & 0x70) == 0x20 )
      {
        v29 = v18;
      }
      else
      {
        if ( v18[2] != 47 || *(_DWORD *)(v18 + 3) != -173623536 )
          goto LABEL_34;
        v29 = v18 + 5;
      }
      ppidl = (LPITEMIDLIST)v29;
      v30 = *((_BYTE *)v29 + 2);
      if ( v30 != 33 )
      {
        v31 = *(unsigned __int16 *)((char *)v29 + 23);
        if ( (v31 & 0xFF00) != 0x100 || (v31 & 1) == 0 )
          goto LABEL_81;
      }
      if ( *v29 < 0x29u )
        goto LABEL_34;
      if ( v30 == 33 )
      {
        if ( *((_BYTE *)v29 + 3) )
        {
          FileSysFolder = -2147024809;
          goto LABEL_65;
        }
      }
      else
      {
LABEL_81:
        if ( v30 == 47 )
        {
          v32 = (char *)v29 + 3;
          if ( v29 == (unsigned __int16 *)-3LL )
            goto LABEL_34;
          do
          {
            if ( !*v32 )
              break;
            ++v32;
            --v14;
          }
          while ( v14 );
          if ( !v14 )
            goto LABEL_34;
        }
      }
      v33 = v9[20].lpVtbl;
      v34 = 2;
      if ( !v33 )
      {
        FileSysFolder = -2147024809;
        goto LABEL_88;
      }
      v35 = (unsigned __int16 *)((char *)v19 + v20);
      v36 = v33;
      v37 = 2;
      do
      {
        QueryInterface_low = LOWORD(v36->QueryInterface);
        if ( !(_WORD)QueryInterface_low )
          break;
        v37 += QueryInterface_low;
        v36 = (struct IBindCtxVtbl *)((char *)v36 + QueryInterface_low);
      }
      while ( v36 );
      v39 = v20;
      if ( v37 + (unsigned int)v20 < v37 )
      {
        FileSysFolder = -2147024362;
LABEL_88:
        v40 = v68;
        goto LABEL_89;
      }
      v49 = v37 + v20;
      v50 = (char *)WINRT_IMPL_CoTaskMemAlloc(v37 + (unsigned int)v20);
      v51 = v50;
      if ( !v50 )
      {
        FileSysFolder = -2147024882;
        goto LABEL_88;
      }
      memset_0(v50, 0, v49);
      v52 = v37 - 2;
      memcpy_0(v51, v33, v52);
      memcpy_0(&v51[v52], ppbc, v39);
      if ( v35 && *v35 )
      {
        ppbc = 0;
        v64 = 0;
        v53 = (const struct IDDRIVE *)ppidl;
        v40 = v68;
        inited = CDrivesFolder::_CreateAndInitHandler(
                   v68,
                   (const struct IDDRIVE *)ppidl,
                   &GUID_000214e6_0000_0000_c000_000000000046,
                   &v64);
        FileSysFolder = inited;
        if ( inited >= 0 )
        {
          FileSysFolder = (*(__int64 (__fastcall **)(CMountPoint *, char *, struct IBindCtx *, GUID *, LPBC *))(*(_QWORD *)v64 + 40LL))(
                            v64,
                            v51,
                            v40,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            &ppbc);
          (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v64 + 16LL))(v64);
LABEL_106:
          if ( FileSysFolder >= 0 )
          {
            FileSysFolder = ((__int64 (__fastcall *)(LPBC, _WORD *, struct IBindCtx *, GUID *, IPropertyBag **))ppbc->lpVtbl->ReleaseBoundObjects)(
                              ppbc,
                              v35,
                              v40,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              &propBag);
            ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
          }
          goto LABEL_108;
        }
        if ( !(unsigned int)FailForceReturn(inited) )
        {
          FileSysFolder = CDrivesFolder::_CreateFileSysFolder(
                            (CDrivesFolder *)Src,
                            v40,
                            (const struct _ITEMIDLIST_ABSOLUTE *)v51,
                            v53,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            (void **)&ppbc);
          goto LABEL_106;
        }
      }
      else
      {
        v55 = (CDrivesFolder *)Src;
        if ( *((_QWORD *)Src + 27)
          && (!memcmp_0(&IID_IDelegateItem, &GUID_000214e6_0000_0000_c000_000000000046, 0x10u)
           || !memcmp_0(&IID_IIdentityName, &GUID_000214e6_0000_0000_c000_000000000046, 0x10u)) )
        {
          CDrivesFolder::_GetParsingName((const struct IDDRIVE *)ppidl, pszName, 0x104u);
          ppbc = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppbc);
          FileSysFolder = CreateBindCtx(0, &ppbc);
          if ( FileSysFolder >= 0 )
          {
            ppidl = 0;
            FileSysFolder = SHParseDisplayName(pszName, ppbc, &ppidl, 0, 0);
            if ( FileSysFolder >= 0 )
              FileSysFolder = SHCreateRelatedItemFromIDList(ppidl, &GUID_000214e6_0000_0000_c000_000000000046, &propBag);
            v58 = ppidl;
            ppidl = 0;
            CoTaskMemFree(v58);
          }
          v59 = ppbc;
          if ( ppbc )
          {
            ppbc = 0;
            ((void (__fastcall *)(LPBC))v59->lpVtbl->Release)(v59);
          }
          v40 = v68;
          CoTaskMemFree(v51);
          goto LABEL_89;
        }
        propBag = 0;
        v64 = 0;
        v56 = (const struct IDDRIVE *)ppidl;
        v40 = v68;
        v57 = CDrivesFolder::_CreateAndInitHandler(
                v68,
                (const struct IDDRIVE *)ppidl,
                &GUID_000214e6_0000_0000_c000_000000000046,
                &v64);
        FileSysFolder = v57;
        if ( v57 >= 0 )
        {
          FileSysFolder = (*(__int64 (__fastcall **)(CMountPoint *, char *, struct IBindCtx *, GUID *, IPropertyBag **))(*(_QWORD *)v64 + 40LL))(
                            v64,
                            v51,
                            v40,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            &propBag);
          (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v64 + 16LL))(v64);
          CoTaskMemFree(v51);
LABEL_89:
          if ( FileSysFolder < 0 )
            goto LABEL_65;
          LODWORD(v68) = 0;
          Src = 0;
          FileSysFolder = ((__int64 (__fastcall *)(IPropertyBag *, struct _ITEMID_CHILD *, struct IBindCtx *, _QWORD, struct IBindCtx **, void **, unsigned int *))propBag->lpVtbl->Read)(
                            propBag,
                            v60,
                            v40,
                            *(_QWORD *)&v69.Data1,
                            &v68,
                            &Src,
                            v61);
          if ( FileSysFolder < 0 )
            goto LABEL_65;
          v41 = Src;
          v42 = *a6;
          if ( Src && v42 )
          {
            v43 = (unsigned __int16 *)*a6;
            v44 = 2;
            do
            {
              v45 = *v43;
              if ( !(_WORD)v45 )
                break;
              v44 += v45;
              v43 = (unsigned __int16 *)((char *)v43 + v45);
            }
            while ( v43 );
            v46 = (unsigned int)(v44 - 2);
            v47 = (unsigned __int16 *)Src;
            do
            {
              v48 = *v47;
              if ( !(_WORD)v48 )
                break;
              v34 += v48;
              v47 = (unsigned __int16 *)((char *)v47 + v48);
            }
            while ( v47 );
            v26 = (char *)WINRT_IMPL_CoTaskMemAlloc(v34 + (unsigned int)v46);
            v27 = v26;
            if ( v26 )
            {
              memset_0(v26, 0, v34 + (unsigned int)v46);
              memcpy_0(v27, v42, (unsigned int)v46);
              memcpy_0(&v27[v46], v41, v34);
            }
            *a6 = (struct _ITEMIDLIST_RELATIVE *)v27;
            FileSysFolder = 0;
            if ( !v27 )
              FileSysFolder = -2147024882;
            CoTaskMemFree(v42);
            CoTaskMemFree(v41);
LABEL_65:
            v28 = propBag;
            if ( propBag )
            {
              propBag = 0;
              ((void (__fastcall *)(IPropertyBag *))v28->lpVtbl->Release)(v28);
            }
            if ( FileSysFolder >= 0 )
              return (unsigned int)FileSysFolder;
            goto LABEL_45;
          }
          FileSysFolder = 0;
          if ( v42 )
            goto LABEL_65;
          if ( Src )
          {
            *a6 = (struct _ITEMIDLIST_RELATIVE *)Src;
            goto LABEL_65;
          }
LABEL_34:
          FileSysFolder = -2147024809;
          goto LABEL_65;
        }
        if ( !(unsigned int)FailForceReturn(v57) )
          FileSysFolder = CDrivesFolder::_CreateFileSysFolder(
                            v55,
                            v40,
                            (const struct _ITEMIDLIST_ABSOLUTE *)v51,
                            v56,
                            &GUID_000214e6_0000_0000_c000_000000000046,
                            (void **)&propBag);
      }
LABEL_108:
      CoTaskMemFree(v51);
      goto LABEL_89;
    }
  }
  else if ( *v16 )
  {
    FileSysFolder = -2147024809;
    goto LABEL_46;
  }
  if ( v61 && *v61 )
  {
    v60 = (struct _ITEMID_CHILD *)v18;
    CDrivesFolder::GetAttributesOf((CDrivesFolder *)v9, 1u, &v60, v61);
  }
  return 0;
}

```

## disassembly

```asm
0x18012eaa0  push    rbp
0x18012eaa2  push    rbx
0x18012eaa3  push    rsi
0x18012eaa4  push    rdi
0x18012eaa5  push    r12
0x18012eaa7  push    r13
0x18012eaa9  push    r14
0x18012eaab  push    r15
0x18012eaad  lea     rbp, [rsp-1F8h]
0x18012eab5  sub     rsp, 2F8h
0x18012eabc  mov     rax, cs:__security_cookie
0x18012eac3  xor     rax, rsp
0x18012eac6  mov     [rbp+230h+var_50], rax
0x18012eacd  mov     rsi, r9
0x18012ead0  mov     r12, r8
0x18012ead3  mov     [rbp+230h+var_2A8], r8
0x18012ead7  mov     [rsp+330h+var_2E8], rdx
0x18012eadc  mov     r15, rcx
0x18012eadf  mov     [rsp+330h+ppbc], rcx
0x18012eae4  mov     r13, [rbp+230h+arg_28]
0x18012eaeb  mov     [rsp+330h+var_2F0], r13
0x18012eaf0  mov     rax, [rbp+230h+arg_30]
0x18012eaf7  mov     [rsp+330h+var_2E0], rax
0x18012eafc  mov     edi, 80070057h
0x18012eb01  test    r13, r13
0x18012eb04  jz      loc_18012EE9F
0x18012eb0a  xorps   xmm0, xmm0
0x18012eb0d  xor     eax, eax
0x18012eb0f  movups  xmmword ptr [rbp+230h+pszRoot], xmm0
0x18012eb13  movups  xmmword ptr [rbp+230h+var_280], xmm0
0x18012eb17  movups  xmmword ptr [rbp+230h+var_280+0Bh], xmm0
0x18012eb1b  mov     [r13+0], rax
0x18012eb1f  test    r9, r9
0x18012eb22  jz      loc_18012EE8E
0x18012eb28  mov     [rbp+230h+value], eax
0x18012eb2b  mov     [rsp+330h+propBag], rax
0x18012eb30  mov     [rsp+330h+ppidl], rax
0x18012eb35  test    r8, r8
0x18012eb38  jz      short loc_18012EBB3
0x18012eb3a  mov     rax, [r8]
0x18012eb3d  lea     r8, [rsp+330h+ppidl]
0x18012eb42  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x18012eb49  mov     rcx, r12
0x18012eb4c  mov     rax, [rax+50h]
0x18012eb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012eb55  test    eax, eax
0x18012eb57  js      short loc_18012EBB3
0x18012eb59  mov     rcx, [rsp+330h+ppidl]
0x18012eb5e  mov     rax, [rcx]
0x18012eb61  lea     r8, [rsp+330h+propBag]
0x18012eb66  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18012eb6d  mov     rax, [rax]
0x18012eb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012eb75  mov     ebx, eax
0x18012eb77  mov     rcx, [rsp+330h+ppidl]
0x18012eb7c  mov     rax, [rcx]
0x18012eb7f  mov     rax, [rax+10h]
0x18012eb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012eb88  test    ebx, ebx
0x18012eb8a  js      short loc_18012EBB3
0x18012eb8c  lea     r8, [rbp+230h+value]; value
0x18012eb90  lea     rdx, aShbindctxpatht; "SHBindCtxPathType"
0x18012eb97  mov     rcx, [rsp+330h+propBag]; propBag
0x18012eb9c  call    cs:__imp_PSPropertyBag_ReadDWORD
0x18012eba2  mov     rcx, [rsp+330h+propBag]
0x18012eba7  mov     rax, [rcx]
0x18012ebaa  mov     rax, [rax+10h]
0x18012ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ebb3  mov     rcx, rsi; pszPath
0x18012ebb6  call    cs:__imp_PathGetDriveNumberW
0x18012ebbc  mov     r14d, eax
0x18012ebbf  mov     ebx, 4
0x18012ebc4  cmp     eax, 0FFFFFFFFh
0x18012ebc7  jz      loc_18012EEED
0x18012ebcd  xor     edi, edi
0x18012ebcf  mov     r15d, edi
0x18012ebd2  test    r12, r12
0x18012ebd5  jz      short loc_18012EC09
0x18012ebd7  mov     qword ptr [rbp+230h+var_2A0.Data1], 10h
0x18012ebdf  xor     eax, eax
0x18012ebe1  mov     qword ptr [rbp+230h+var_2A0.Data4], rax
0x18012ebe5  mov     rax, [r12]
0x18012ebe9  lea     rdx, [rbp+230h+var_2A0]
0x18012ebed  mov     rcx, r12
0x18012ebf0  mov     rax, [rax+38h]
0x18012ebf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ebf9  test    eax, eax
0x18012ebfb  js      short loc_18012EC09
0x18012ebfd  cmp     dword ptr [rbp+230h+var_2A0.Data2], 2
0x18012ec01  jnz     short loc_18012EC09
0x18012ec03  mov     r15d, 1
0x18012ec09  xorps   xmm0, xmm0
0x18012ec0c  movups  xmmword ptr [rbp+230h+pszRoot], xmm0
0x18012ec10  movups  xmmword ptr [rbp+230h+var_280], xmm0
0x18012ec14  movups  xmmword ptr [rbp+230h+var_280+0Bh], xmm0
0x18012ec18  mov     edx, r14d; iDrive
0x18012ec1b  lea     rcx, [rbp+230h+pszRoot+3]; pszRoot
0x18012ec1f  call    cs:__imp_PathBuildRootA
0x18012ec25  mov     [rsp+330h+var_2C8], rdi
0x18012ec2a  test    r12, r12
0x18012ec2d  jz      loc_18012EDFA
0x18012ec33  mov     rax, [r12]
0x18012ec37  lea     r8, [rsp+330h+var_2C8]
0x18012ec3c  lea     rdx, aFileSystemBind; "File System Bind Data"
0x18012ec43  mov     rcx, r12
0x18012ec46  mov     rax, [rax+50h]
0x18012ec4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ec4f  test    eax, eax
0x18012ec51  js      loc_18012EDC5
0x18012ec57  mov     rcx, [rsp+330h+var_2C8]
0x18012ec5c  mov     rax, [rcx]
0x18012ec5f  mov     rax, [rax+10h]
0x18012ec63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ec68  mov     eax, 19h
0x18012ec6d  mov     word ptr [rbp+230h+pszRoot], ax
0x18012ec71  mov     [rbp+230h+pszRoot+2], 2Fh ; '/'
0x18012ec75  xorps   xmm0, xmm0
0x18012ec78  movups  xmmword ptr [rbp+230h+var_2A0.Data1], xmm0
0x18012ec7c  test    r15d, r15d
0x18012ec7f  jnz     short loc_18012EC95
0x18012ec81  lea     rdx, [rbp+230h+var_2A0]; struct _GUID *
0x18012ec85  mov     ecx, r14d; iDrive
0x18012ec88  call    ?GetDriveJunctionCLSID@CMountPoint@@SAJHPEAU_GUID@@@Z; CMountPoint::GetDriveJunctionCLSID(int,_GUID *)
0x18012ec8d  test    eax, eax
0x18012ec8f  jns     loc_18012F54A
0x18012ec95  mov     [rsp+330h+var_2C8], 0
0x18012ec9e  test    r12, r12
0x18012eca1  jz      short loc_18012ECC7
0x18012eca3  mov     rax, [r12]
0x18012eca7  lea     r8, [rsp+330h+var_2C8]
0x18012ecac  lea     rdx, aFailifdrivehas; "FailIfDriveHasNoMedia"
0x18012ecb3  mov     rcx, r12
0x18012ecb6  mov     rax, [rax+50h]
0x18012ecba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ecbf  test    eax, eax
0x18012ecc1  jns     loc_18012F48E
0x18012ecc7  mov     r15, [rsp+330h+ppbc]
0x18012eccc  cmp     [rbp+230h+value], 12h
0x18012ecd0  jz      loc_18012EED8
0x18012ecd6  mov     r8d, ebx; nChar
0x18012ecd9  lea     rdx, asc_1806F9508; "\\\\?\\"
0x18012ece0  mov     rcx, rsi; pszStr1
0x18012ece3  call    cs:__imp_StrCmpNICW
0x18012ece9  test    eax, eax
0x18012eceb  jz      loc_18012F569
0x18012ecf1  add     rsi, 4
0x18012ecf5  test    edi, edi
0x18012ecf7  js      loc_18012EE8E
0x18012ecfd  lea     rax, [r15-30h]
0x18012ed01  mov     [rsp+330h+Src], rax
0x18012ed06  cmp     dword ptr [rax+0E4h], 1
0x18012ed0d  jz      loc_18012F356
0x18012ed13  xor     edi, edi
0x18012ed15  mov     [rsp+330h+ppbc], rdi
0x18012ed1a  mov     [r13+0], rdi
0x18012ed1e  mov     rcx, [r15+0A8h]
0x18012ed25  test    rcx, rcx
0x18012ed28  jnz     loc_18012EFF0
0x18012ed2e  mov     ecx, 2Fh ; '/'; cb
0x18012ed33  call    cs:__imp_CoTaskMemAlloc
0x18012ed39  test    rax, rax
0x18012ed3c  jz      loc_18012EF52
0x18012ed42  movups  xmm0, xmmword ptr [rbp+230h+pszRoot]
0x18012ed46  movups  xmmword ptr [rax], xmm0
0x18012ed49  movups  xmm1, xmmword ptr [rbp+230h+var_280]
0x18012ed4d  movups  xmmword ptr [rax+10h], xmm1
0x18012ed51  movups  xmm0, xmmword ptr [rbp+230h+var_280+0Bh]
0x18012ed55  movups  xmmword ptr [rax+1Bh], xmm0
0x18012ed59  mov     r12, rax
0x18012ed5c  mov     [rsp+330h+ppbc], rax
0x18012ed61  mov     [r13+0], rax
0x18012ed65  movzx   eax, word ptr [rsi]
0x18012ed68  cmp     ax, 5Ch ; '\'
0x18012ed6c  jnz     loc_18012EEE1
0x18012ed72  lea     rax, [rsi+2]
0x18012ed76  mov     qword ptr [rbp+230h+var_2A0.Data1], rax
0x18012ed7a  cmp     [rax], di
0x18012ed7d  jz      loc_18012EEC4
0x18012ed83  mov     [rsp+330h+propBag], rdi
0x18012ed88  movzx   r8d, word ptr [r12]
0x18012ed8d  cmp     r8d, 19h
0x18012ed91  jb      short loc_18012EDBB
0x18012ed93  movzx   eax, byte ptr [r12+2]
0x18012ed99  and     al, 70h
0x18012ed9b  cmp     al, 20h ; ' '
0x18012ed9d  jz      loc_18012F02E
0x18012eda3  cmp     word ptr [r12+4], 2Fh ; '/'
0x18012edaa  jnz     short loc_18012EDBB
0x18012edac  cmp     dword ptr [r12+6], 0F5A6B710h
0x18012edb5  jz      loc_18012F5CF
0x18012edbb  mov     edi, 80070057h
0x18012edc0  jmp     loc_18012EFC2
0x18012edc5  mov     [rbp+230h+var_2A0.Data1], 10h
0x18012edcc  xor     eax, eax
0x18012edce  mov     qword ptr [rbp+230h+var_2A0.Data2], rax
0x18012edd2  mov     dword ptr [rbp+230h+var_2A0.Data4+4], eax
0x18012edd5  mov     rax, [r12]
0x18012edd9  lea     rdx, [rbp+230h+var_2A0]
0x18012eddd  mov     rcx, r12
0x18012ede0  mov     rax, [rax+38h]
0x18012ede4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ede9  test    eax, eax
0x18012edeb  js      short loc_18012EDFA
0x18012eded  test    dword ptr [rbp+230h+var_2A0.Data4], 1000h
0x18012edf4  jnz     loc_18012EC68
0x18012edfa  mov     edi, 8007000Fh
0x18012edff  mov     [rsp+330h+propBag], 0
0x18012ee08  lea     rcx, [rsp+330h+propBag]
0x18012ee0d  call    ?InternalRelease@?$ComPtr@VCMtPtLocal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMtPtLocal>::InternalRelease(void)
0x18012ee12  xor     ecx, ecx
0x18012ee14  mov     [rsp+330h+propBag], rcx
0x18012ee19  mov     r12d, 80070057h
0x18012ee1f  cmp     r14d, 19h
0x18012ee23  ja      short loc_18012EE62
0x18012ee25  lea     rcx, Parameter; Parameter
0x18012ee2c  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x18012ee31  mov     r12d, 80004004h
0x18012ee37  cmp     dword ptr cs:qword_1808041C0+4, 0
0x18012ee3e  jnz     short loc_18012EE50
0x18012ee40  lea     rdx, [rsp+330h+propBag]; struct CMountPoint **
0x18012ee45  mov     ecx, r14d; int
0x18012ee48  call    ?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z; CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)
0x18012ee4d  mov     r12d, eax
0x18012ee50  lea     rcx, Parameter; lpCriticalSection
0x18012ee57  call    cs:__imp_LeaveCriticalSection
0x18012ee5d  mov     rcx, [rsp+330h+propBag]; this
0x18012ee62  test    rcx, rcx
0x18012ee65  jz      short loc_18012EE75
0x18012ee67  mov     [rsp+330h+propBag], 0
0x18012ee70  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x18012ee75  test    r12d, r12d
0x18012ee78  mov     r12, [rbp+230h+var_2A8]
0x18012ee7c  js      loc_18012ECC7
0x18012ee82  xor     edi, edi
0x18012ee84  jmp     loc_18012EC68
0x18012ee89  mov     r13, [rsp+330h+var_2F0]
0x18012ee8e  xor     ecx, ecx
0x18012ee90  xchg    rcx, [r13+0]; pv
0x18012ee94  test    rcx, rcx
0x18012ee97  jz      short loc_18012EE9F
0x18012ee99  call    cs:__imp_CoTaskMemFree
0x18012ee9f  mov     eax, edi
0x18012eea1  mov     rcx, [rbp+230h+var_50]
0x18012eea8  xor     rcx, rsp; StackCookie
0x18012eeab  call    __security_check_cookie
0x18012eeb0  add     rsp, 2F8h
0x18012eeb7  pop     r15
0x18012eeb9  pop     r14
0x18012eebb  pop     r13
0x18012eebd  pop     r12
0x18012eebf  pop     rdi
0x18012eec0  pop     rsi
0x18012eec1  pop     rbx
0x18012eec2  pop     rbp
0x18012eec3  retn
0x18012eec4  mov     ebx, edi
0x18012eec6  mov     r9, [rsp+330h+var_2E0]; unsigned int *
0x18012eecb  test    r9, r9
0x18012eece  jnz     loc_18012F5E3
0x18012eed4  mov     eax, ebx
0x18012eed6  jmp     short loc_18012EEA1
0x18012eed8  add     rsi, 0Ch
0x18012eedc  jmp     loc_18012ECF5
0x18012eee1  test    ax, ax
0x18012eee4  jz      short loc_18012EEC4
0x18012eee6  mov     edi, 80070057h
0x18012eeeb  jmp     short loc_18012EE8E
0x18012eeed  cmp     [rbp+230h+value], 16h
0x18012eef1  jnz     short loc_18012EE8E
0x18012eef3  xorps   xmm0, xmm0
0x18012eef6  movups  xmmword ptr [rbp+230h+var_2A0.Data1], xmm0
0x18012eefa  lea     rcx, [rsi+14h]
0x18012eefe  lea     rdx, [rbp+230h+var_2A0]
0x18012ef02  call    cs:__imp_GUIDFromStringW
0x18012ef08  test    eax, eax
0x18012ef0a  jz      short loc_18012EE8E
0x18012ef0c  xorps   xmm0, xmm0
0x18012ef0f  movups  xmmword ptr [rbp+230h+pszRoot], xmm0
0x18012ef13  movups  xmmword ptr [rbp+230h+var_280], xmm0
0x18012ef17  movups  xmmword ptr [rbp+230h+var_280+0Bh], xmm0
0x18012ef1b  lea     rdx, aFileSystemBind; "File System Bind Data"
0x18012ef22  mov     rcx, r12; struct IBindCtx *
0x18012ef25  call    ?BindCtx_ContainsObject@@YAHPEAUIBindCtx@@PEBG@Z; BindCtx_ContainsObject(IBindCtx *,ushort const *)
0x18012ef2a  test    eax, eax
0x18012ef2c  jz      loc_18012F589
0x18012ef32  mov     eax, 29h ; ')'
0x18012ef37  mov     word ptr [rbp+230h+pszRoot], ax
0x18012ef3b  mov     [rbp+230h+pszRoot+2], 21h ; '!'
0x18012ef3f  movups  xmm0, xmmword ptr [rbp+230h+var_2A0.Data1]
0x18012ef43  movups  xmmword ptr [rbp+230h+var_280+9], xmm0
0x18012ef47  xor     edi, edi
0x18012ef49  add     rsi, 60h ; '`'
0x18012ef4d  jmp     loc_18012ECF5
0x18012ef52  mov     [r13+0], rdi
0x18012ef56  mov     edi, 8007000Eh
0x18012ef5b  jmp     loc_18012EE89
0x18012ef60  lea     eax, [r15+rdi]
0x18012ef64  mov     ebx, eax
0x18012ef66  mov     ecx, eax; cb
0x18012ef68  call    WINRT_IMPL_CoTaskMemAlloc
  ... truncated ...
```
