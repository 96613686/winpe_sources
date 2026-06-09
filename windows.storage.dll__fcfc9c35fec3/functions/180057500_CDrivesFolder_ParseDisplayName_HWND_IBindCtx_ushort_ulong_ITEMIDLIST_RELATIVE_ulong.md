# CDrivesFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180057500`
- end: `0x18005809c`
- name: `?ParseDisplayName@CDrivesFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `2972`
- prototype: `int(CDrivesFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009fc0`
- `0x180040430`
- `0x1800559e0`
- `0x180057500`
- `0x1800580b0`
- `0x1800584d0`
- `0x180058510`
- `0x180058560`
- `0x1800587e0`
- `0x180059f74`
- `0x180065890`
- `0x180065a00`
- `0x180065ab0`
- `0x1800b7ae0`
- `0x1800d38a0`
- `0x180116e60`
- `0x1801d32e0`
- `0x1801ee6c0`
- `0x1802d7a50`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b2ea5`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800578d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800578d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180057755`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180057755`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18005761c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18005761c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800577ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800577ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005791d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005791d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057a48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057d4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ec3`
- `SHCORE!__imp_GUIDFromStringW` at `0x18005798d`
- `SHCORE!__imp_GUIDFromStringW` at `0x18005798d`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1800575fc`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x1800575fc`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootA` at `0x18005768b`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootA` at `0x18005768b`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x180057e7d`
- `api-ms-win-ole32-ie-l1-1-0!CreateBindCtx` at `0x180057e7d`

## string_xrefs

- `0x1800575f0`: `SHBindCtxPathType`

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
  int v54; // eax
  CDrivesFolder *v55; // r13
  const struct IDDRIVE *v56; // r12
  int inited; // eax
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
      if ( !HIDWORD(qword_180828300) )
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
      if ( !v35 || !*v35 )
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
        }
        else
        {
          propBag = 0;
          v64 = 0;
          v56 = (const struct IDDRIVE *)ppidl;
          v40 = v68;
          inited = CDrivesFolder::_CreateAndInitHandler(
                     v68,
                     (const struct IDDRIVE *)ppidl,
                     &GUID_000214e6_0000_0000_c000_000000000046,
                     &v64);
          FileSysFolder = inited;
          if ( inited >= 0 )
          {
            FileSysFolder = (*(__int64 (__fastcall **)(CMountPoint *, char *, struct IBindCtx *, GUID *, IPropertyBag **))(*(_QWORD *)v64 + 40LL))(
                              v64,
                              v51,
                              v40,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              &propBag);
            (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v64 + 16LL))(v64);
          }
          else if ( !(unsigned int)FailForceReturn(inited) )
          {
            FileSysFolder = CDrivesFolder::_CreateFileSysFolder(
                              v55,
                              v40,
                              (const struct _ITEMIDLIST_ABSOLUTE *)v51,
                              v56,
                              &GUID_000214e6_0000_0000_c000_000000000046,
                              (void **)&propBag);
          }
        }
        goto LABEL_108;
      }
      ppbc = 0;
      v64 = 0;
      v53 = (const struct IDDRIVE *)ppidl;
      v40 = v68;
      v54 = CDrivesFolder::_CreateAndInitHandler(
              v68,
              (const struct IDDRIVE *)ppidl,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &v64);
      FileSysFolder = v54;
      if ( v54 >= 0 )
      {
        FileSysFolder = (*(__int64 (__fastcall **)(CMountPoint *, char *, struct IBindCtx *, GUID *, LPBC *))(*(_QWORD *)v64 + 40LL))(
                          v64,
                          v51,
                          v40,
                          &GUID_000214e6_0000_0000_c000_000000000046,
                          &ppbc);
        (*(void (__fastcall **)(CMountPoint *))(*(_QWORD *)v64 + 16LL))(v64);
      }
      else
      {
        if ( (unsigned int)FailForceReturn(v54) )
        {
LABEL_108:
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
        FileSysFolder = CDrivesFolder::_CreateFileSysFolder(
                          (CDrivesFolder *)Src,
                          v40,
                          (const struct _ITEMIDLIST_ABSOLUTE *)v51,
                          v53,
                          &GUID_000214e6_0000_0000_c000_000000000046,
                          (void **)&ppbc);
      }
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
0x180057500  push    rbp
0x180057502  push    rbx
0x180057503  push    rsi
0x180057504  push    rdi
0x180057505  push    r12
0x180057507  push    r13
0x180057509  push    r14
0x18005750b  push    r15
0x18005750d  lea     rbp, [rsp-1F8h]
0x180057515  sub     rsp, 2F8h
0x18005751c  mov     rax, cs:__security_cookie
0x180057523  xor     rax, rsp
0x180057526  mov     [rbp+230h+var_50], rax
0x18005752d  mov     rsi, r9
0x180057530  mov     r12, r8
0x180057533  mov     [rbp+230h+var_2A8], r8
0x180057537  mov     [rsp+330h+var_2E8], rdx
0x18005753c  mov     r15, rcx
0x18005753f  mov     [rsp+330h+ppbc], rcx
0x180057544  mov     r13, [rbp+230h+arg_28]
0x18005754b  mov     [rsp+330h+var_2F0], r13
0x180057550  mov     rax, [rbp+230h+arg_30]
0x180057557  mov     [rsp+330h+var_2E0], rax
0x18005755c  mov     edi, 80070057h
0x180057561  test    r13, r13
0x180057564  jz      loc_180057929
0x18005756a  xorps   xmm0, xmm0
0x18005756d  xor     eax, eax
0x18005756f  movups  xmmword ptr [rbp+230h+pszRoot], xmm0
0x180057573  movups  xmmword ptr [rbp+230h+var_280], xmm0
0x180057577  movups  xmmword ptr [rbp+230h+var_280+0Bh], xmm0
0x18005757b  mov     [r13+0], rax
0x18005757f  test    r9, r9
0x180057582  jz      loc_180057912
0x180057588  mov     [rbp+230h+value], eax
0x18005758b  mov     [rsp+330h+propBag], rax
0x180057590  mov     [rsp+330h+ppidl], rax
0x180057595  test    r8, r8
0x180057598  jz      short loc_180057619
0x18005759a  mov     rax, [r8]
0x18005759d  lea     r8, [rsp+330h+ppidl]
0x1800575a2  lea     rdx, aShbindctxprope; "SHBindCtxPropertyBag"
0x1800575a9  mov     rcx, r12
0x1800575ac  mov     rax, [rax+50h]
0x1800575b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800575b5  test    eax, eax
0x1800575b7  js      short loc_180057619
0x1800575b9  mov     rcx, [rsp+330h+ppidl]
0x1800575be  mov     rax, [rcx]
0x1800575c1  lea     r8, [rsp+330h+propBag]
0x1800575c6  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x1800575cd  mov     rax, [rax]
0x1800575d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800575d5  mov     ebx, eax
0x1800575d7  mov     rcx, [rsp+330h+ppidl]
0x1800575dc  mov     rax, [rcx]
0x1800575df  mov     rax, [rax+10h]
0x1800575e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800575e8  test    ebx, ebx
0x1800575ea  js      short loc_180057619
0x1800575ec  lea     r8, [rbp+230h+value]; value
0x1800575f0  lea     rdx, aShbindctxpatht; "SHBindCtxPathType"
0x1800575f7  mov     rcx, [rsp+330h+propBag]; propBag
0x1800575fc  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180057603  nop     dword ptr [rax+rax+00h]
0x180057608  mov     rcx, [rsp+330h+propBag]
0x18005760d  mov     rax, [rcx]
0x180057610  mov     rax, [rax+10h]
0x180057614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057619  mov     rcx, rsi; pszPath
0x18005761c  call    cs:__imp_PathGetDriveNumberW
0x180057623  nop     dword ptr [rax+rax+00h]
0x180057628  mov     r14d, eax
0x18005762b  mov     ebx, 4
0x180057630  cmp     eax, 0FFFFFFFFh
0x180057633  jz      loc_180057978
0x180057639  xor     edi, edi
0x18005763b  mov     r15d, edi
0x18005763e  test    r12, r12
0x180057641  jz      short loc_180057675
0x180057643  mov     qword ptr [rbp+230h+var_2A0.Data1], 10h
0x18005764b  xor     eax, eax
0x18005764d  mov     qword ptr [rbp+230h+var_2A0.Data4], rax
0x180057651  mov     rax, [r12]
0x180057655  lea     rdx, [rbp+230h+var_2A0]
0x180057659  mov     rcx, r12
0x18005765c  mov     rax, [rax+38h]
0x180057660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057665  test    eax, eax
0x180057667  js      short loc_180057675
0x180057669  cmp     dword ptr [rbp+230h+var_2A0.Data2], 2
0x18005766d  jnz     short loc_180057675
0x18005766f  mov     r15d, 1
0x180057675  xorps   xmm0, xmm0
0x180057678  movups  xmmword ptr [rbp+230h+pszRoot], xmm0
0x18005767c  movups  xmmword ptr [rbp+230h+var_280], xmm0
0x180057680  movups  xmmword ptr [rbp+230h+var_280+0Bh], xmm0
0x180057684  mov     edx, r14d; iDrive
0x180057687  lea     rcx, [rbp+230h+pszRoot+3]; pszRoot
0x18005768b  call    cs:__imp_PathBuildRootA
0x180057692  nop     dword ptr [rax+rax+00h]
0x180057697  mov     [rsp+330h+var_2C8], rdi
0x18005769c  test    r12, r12
0x18005769f  jz      loc_180057878
0x1800576a5  mov     rax, [r12]
0x1800576a9  lea     r8, [rsp+330h+var_2C8]
0x1800576ae  lea     rdx, aFileSystemBind; "File System Bind Data"
0x1800576b5  mov     rcx, r12
0x1800576b8  mov     rax, [rax+50h]
0x1800576bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576c1  test    eax, eax
0x1800576c3  js      loc_180057843
0x1800576c9  mov     rcx, [rsp+330h+var_2C8]
0x1800576ce  mov     rax, [rcx]
0x1800576d1  mov     rax, [rax+10h]
0x1800576d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576da  mov     eax, 19h
0x1800576df  mov     word ptr [rbp+230h+pszRoot], ax
0x1800576e3  mov     [rbp+230h+pszRoot+2], 2Fh ; '/'
0x1800576e7  xorps   xmm0, xmm0
0x1800576ea  movups  xmmword ptr [rbp+230h+var_2A0.Data1], xmm0
0x1800576ee  test    r15d, r15d
0x1800576f1  jnz     short loc_180057707
0x1800576f3  lea     rdx, [rbp+230h+var_2A0]; struct _GUID *
0x1800576f7  mov     ecx, r14d; iDrive
0x1800576fa  call    ?GetDriveJunctionCLSID@CMountPoint@@SAJHPEAU_GUID@@@Z; CMountPoint::GetDriveJunctionCLSID(int,_GUID *)
0x1800576ff  test    eax, eax
0x180057701  jns     loc_180057FDE
0x180057707  mov     [rsp+330h+var_2C8], 0
0x180057710  test    r12, r12
0x180057713  jz      short loc_180057739
0x180057715  mov     rax, [r12]
0x180057719  lea     r8, [rsp+330h+var_2C8]
0x18005771e  lea     rdx, aFailifdrivehas; "FailIfDriveHasNoMedia"
0x180057725  mov     rcx, r12
0x180057728  mov     rax, [rax+50h]
0x18005772c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057731  test    eax, eax
0x180057733  jns     loc_180057F31
0x180057739  mov     r15, [rsp+330h+ppbc]
0x18005773e  cmp     [rbp+230h+value], 12h
0x180057742  jz      loc_180057963
0x180057748  mov     r8d, ebx; nChar
0x18005774b  lea     rdx, pszStr2; "\\\\?\\"
0x180057752  mov     rcx, rsi; pszStr1
0x180057755  call    cs:__imp_StrCmpNICW
0x18005775c  nop     dword ptr [rax+rax+00h]
0x180057761  test    eax, eax
0x180057763  jz      loc_180057FFD
0x180057769  add     rsi, 4
0x18005776d  test    edi, edi
0x18005776f  js      loc_180057912
0x180057775  lea     rax, [r15-30h]
0x180057779  mov     [rsp+330h+Src], rax
0x18005777e  cmp     dword ptr [rax+0E4h], 1
0x180057785  jz      loc_180057DFC
0x18005778b  xor     edi, edi
0x18005778d  mov     [rsp+330h+ppbc], rdi
0x180057792  mov     [r13+0], rdi
0x180057796  mov     rcx, [r15+0A8h]
0x18005779d  test    rcx, rcx
0x1800577a0  jnz     loc_180057A91
0x1800577a6  mov     ecx, 2Fh ; '/'; cb
0x1800577ab  call    cs:__imp_CoTaskMemAlloc
0x1800577b2  nop     dword ptr [rax+rax+00h]
0x1800577b7  test    rax, rax
0x1800577ba  jz      loc_1800579E7
0x1800577c0  movups  xmm0, xmmword ptr [rbp+230h+pszRoot]
0x1800577c4  movups  xmmword ptr [rax], xmm0
0x1800577c7  movups  xmm1, xmmword ptr [rbp+230h+var_280]
0x1800577cb  movups  xmmword ptr [rax+10h], xmm1
0x1800577cf  movups  xmm0, xmmword ptr [rbp+230h+var_280+0Bh]
0x1800577d3  movups  xmmword ptr [rax+1Bh], xmm0
0x1800577d7  mov     r12, rax
0x1800577da  mov     [rsp+330h+ppbc], rax
0x1800577df  mov     [r13+0], rax
0x1800577e3  movzx   eax, word ptr [rsi]
0x1800577e6  cmp     ax, 5Ch ; '\'
0x1800577ea  jnz     loc_18005796C
0x1800577f0  lea     rax, [rsi+2]
0x1800577f4  mov     qword ptr [rbp+230h+var_2A0.Data1], rax
0x1800577f8  cmp     [rax], di
0x1800577fb  jz      loc_18005794F
0x180057801  mov     [rsp+330h+propBag], rdi
0x180057806  movzx   r8d, word ptr [r12]
0x18005780b  cmp     r8d, 19h
0x18005780f  jb      short loc_180057839
0x180057811  movzx   eax, byte ptr [r12+2]
0x180057817  and     al, 70h
0x180057819  cmp     al, 20h ; ' '
0x18005781b  jz      loc_180057ACF
0x180057821  cmp     word ptr [r12+4], 2Fh ; '/'
0x180057828  jnz     short loc_180057839
0x18005782a  cmp     dword ptr [r12+6], 0F5A6B710h
0x180057833  jz      loc_180058063
0x180057839  mov     edi, 80070057h
0x18005783e  jmp     loc_180057A63
0x180057843  mov     [rbp+230h+var_2A0.Data1], 10h
0x18005784a  xor     eax, eax
0x18005784c  mov     qword ptr [rbp+230h+var_2A0.Data2], rax
0x180057850  mov     dword ptr [rbp+230h+var_2A0.Data4+4], eax
0x180057853  mov     rax, [r12]
0x180057857  lea     rdx, [rbp+230h+var_2A0]
0x18005785b  mov     rcx, r12
0x18005785e  mov     rax, [rax+38h]
0x180057862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057867  test    eax, eax
0x180057869  js      short loc_180057878
0x18005786b  test    dword ptr [rbp+230h+var_2A0.Data4], 1000h
0x180057872  jnz     loc_1800576DA
0x180057878  mov     edi, 8007000Fh
0x18005787d  mov     [rsp+330h+propBag], 0
0x180057886  lea     rcx, [rsp+330h+propBag]
0x18005788b  call    ?InternalRelease@?$ComPtr@VCMtPtLocal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMtPtLocal>::InternalRelease(void)
0x180057890  xor     ecx, ecx
0x180057892  mov     [rsp+330h+propBag], rcx
0x180057897  mov     r12d, 80070057h
0x18005789d  cmp     r14d, 19h
0x1800578a1  ja      short loc_1800578E6
0x1800578a3  lea     rcx, Parameter; Parameter
0x1800578aa  call    ?Enter@CCritSecDelayInitBase@@QEAAXXZ; CCritSecDelayInitBase::Enter(void)
0x1800578af  mov     r12d, 80004004h
0x1800578b5  cmp     dword ptr cs:qword_180828300+4, 0
0x1800578bc  jnz     short loc_1800578CE
0x1800578be  lea     rdx, [rsp+330h+propBag]; struct CMountPoint **
0x1800578c3  mov     ecx, r14d; int
0x1800578c6  call    ?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z; CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)
0x1800578cb  mov     r12d, eax
0x1800578ce  lea     rcx, Parameter; lpCriticalSection
0x1800578d5  call    cs:__imp_LeaveCriticalSection
0x1800578dc  nop     dword ptr [rax+rax+00h]
0x1800578e1  mov     rcx, [rsp+330h+propBag]; this
0x1800578e6  test    rcx, rcx
0x1800578e9  jz      short loc_1800578F9
0x1800578eb  mov     [rsp+330h+propBag], 0
0x1800578f4  call    ?Release@CMountPoint@@QEAAKXZ; CMountPoint::Release(void)
0x1800578f9  test    r12d, r12d
0x1800578fc  mov     r12, [rbp+230h+var_2A8]
0x180057900  js      loc_180057739
0x180057906  xor     edi, edi
0x180057908  jmp     loc_1800576DA
0x18005790d  mov     r13, [rsp+330h+var_2F0]
0x180057912  xor     ecx, ecx
0x180057914  xchg    rcx, [r13+0]; pv
0x180057918  test    rcx, rcx
0x18005791b  jz      short loc_180057929
0x18005791d  call    cs:__imp_CoTaskMemFree
0x180057924  nop     dword ptr [rax+rax+00h]
0x180057929  mov     eax, edi
0x18005792b  mov     rcx, [rbp+230h+var_50]
0x180057932  xor     rcx, rsp; StackCookie
0x180057935  call    __security_check_cookie
0x18005793a  add     rsp, 2F8h
0x180057941  pop     r15
0x180057943  pop     r14
0x180057945  pop     r13
0x180057947  pop     r12
0x180057949  pop     rdi
0x18005794a  pop     rsi
0x18005794b  pop     rbx
0x18005794c  pop     rbp
0x18005794d  retn
0x18005794f  mov     ebx, edi
0x180057951  mov     r9, [rsp+330h+var_2E0]; unsigned int *
0x180057956  test    r9, r9
0x180057959  jnz     loc_180058077
0x18005795f  mov     eax, ebx
0x180057961  jmp     short loc_18005792B
0x180057963  add     rsi, 0Ch
0x180057967  jmp     loc_18005776D
0x18005796c  test    ax, ax
0x18005796f  jz      short loc_18005794F
0x180057971  mov     edi, 80070057h
0x180057976  jmp     short loc_180057912
0x180057978  cmp     [rbp+230h+value], 16h
0x18005797c  jnz     short loc_180057912
0x18005797e  xorps   xmm0, xmm0
0x180057981  movups  xmmword ptr [rbp+230h+var_2A0.Data1], xmm0
0x180057985  lea     rcx, [rsi+14h]
0x180057989  lea     rdx, [rbp+230h+var_2A0]
0x18005798d  call    cs:__imp_GUIDFromStringW
0x180057994  nop     dword ptr [rax+rax+00h]
0x180057999  test    eax, eax
0x18005799b  jz      loc_180057912
0x1800579a1  xorps   xmm0, xmm0
0x1800579a4  movups  xmmword ptr [rbp+230h+pszRoot], xmm0
0x1800579a8  movups  xmmword ptr [rbp+230h+var_280], xmm0
0x1800579ac  movups  xmmword ptr [rbp+230h+var_280+0Bh], xmm0
0x1800579b0  lea     rdx, aFileSystemBind; "File System Bind Data"
0x1800579b7  mov     rcx, r12; struct IBindCtx *
0x1800579ba  call    ?BindCtx_ContainsObject@@YAHPEAUIBindCtx@@PEBG@Z; BindCtx_ContainsObject(IBindCtx *,ushort const *)
0x1800579bf  test    eax, eax
0x1800579c1  jz      loc_18005801D
0x1800579c7  mov     eax, 29h ; ')'
0x1800579cc  mov     word ptr [rbp+230h+pszRoot], ax
0x1800579d0  mov     [rbp+230h+pszRoot+2], 21h ; '!'
0x1800579d4  movups  xmm0, xmmword ptr [rbp+230h+var_2A0.Data1]
0x1800579d8  movups  xmmword ptr [rbp+230h+var_280+9], xmm0
0x1800579dc  xor     edi, edi
0x1800579de  add     rsi, 60h ; '`'
  ... truncated ...
```
