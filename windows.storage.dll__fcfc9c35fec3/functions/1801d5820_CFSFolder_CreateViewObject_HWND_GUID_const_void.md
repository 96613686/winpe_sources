# CFSFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x1801d5820`
- end: `0x1801d60cc`
- name: `?CreateViewObject@CFSFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `2220`
- prototype: `int(CFSFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180035d30`
- `0x1800376a0`
- `0x18003df10`
- `0x18003e0a0`
- `0x18003e730`
- `0x180045230`
- `0x180063050`
- `0x1800693a0`
- `0x180117f6c`
- `0x1801d5820`
- `0x1801d60d4`
- `0x1801d6478`
- `0x1801d6880`
- `0x1801e8990`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1803b243c`
- `0x180524200`
- `0x18052dc04`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801d6007`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801d6007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d5f50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801d5f50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801d5f14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801d5f14`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1806718ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1806718ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d5c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d5dfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d602a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d6099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d5c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d5dfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d602a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801d6099`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801d5ac7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801d5ac7`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180671973`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180671973`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1806719a5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1806719a5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180671947`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180671947`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHCreateShellFolderView` at `0x1801d5bc7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHCreateShellFolderView` at `0x1801d5bc7`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateSharePointView` at `0x180671a14`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateSharePointView` at `0x180671a14`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSDropTarget_CreateInstance` at `0x1801d5edd`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSDropTarget_CreateInstance` at `0x1801d5edd`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSFolderCallback_Create` at `0x1801d5bb4`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSFolderCallback_Create` at `0x1801d5bb4`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateFileFolderContextMenu` at `0x1801d5eba`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateFileFolderContextMenu` at `0x1801d5eba`

## string_xrefs

- `0x1801d5f06`: `Directory\shellex\Category`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFSFolder::CreateViewObject(CFSFolder *this, HWND a2, struct _GUID *a3, void **a4)
{
  CFSFolder *v7; // r13
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  const ITEMIDLIST *v14; // rax
  HRESULT UIHandler; // edi
  unsigned __int16 **v16; // rax
  void *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  LPVOID *p_pv; // r14
  char v24; // r12
  void *v25; // rdx
  struct _GUID *v26; // rcx
  __int64 v27; // rax
  int v28; // esi
  char *v30; // rcx
  CFSFolder *v31; // rsi
  __int64 v32; // rax
  char *v33; // rcx
  const ITEMIDLIST *v34; // rcx
  bool v35; // si
  void *v36; // rcx
  unsigned int i; // ecx
  _QWORD *v38; // rdx
  __int64 v39; // rax
  LPVOID v40; // r12
  int inited; // esi
  CShellItem *v42; // rax
  CShellItem *v43; // rax
  CShellItem *v44; // r14
  void *v45; // r14
  volatile signed __int32 *v46; // rax
  volatile signed __int32 *v47; // rsi
  __int64 v48; // rax
  __int64 v49; // rax
  _QWORD *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rcx
  char *v53; // rdi
  __int64 v54; // rax
  __int64 v55; // rax
  HINSTANCE v56; // rax
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rax
  DWORD v60; // r12d
  unsigned __int16 **v61; // rax
  unsigned int DriveNumberW; // eax
  HINSTANCE v63; // rax
  unsigned __int16 **v64; // rax
  volatile signed __int32 *v65; // [rsp+40h] [rbp-29h] BYREF
  __int64 v66; // [rsp+48h] [rbp-21h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *TokenHandle; // [rsp+50h] [rbp-19h] BYREF
  __int128 v68; // [rsp+58h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1h] BYREF
  void *ppv; // [rsp+70h] [rbp+7h] BYREF

  v7 = this;
  *a4 = 0;
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( !v8 )
    goto LABEL_47;
  v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
    v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
  if ( !v9 )
  {
LABEL_47:
    v31 = (CFSFolder *)((char *)this - 48);
    if ( *((_DWORD *)this + 130) )
      goto LABEL_48;
    v60 = SHRestricted(REST_NOVIEWONDRIVE);
    if ( !v60 )
    {
      v58 = *(_QWORD *)IID_IDropTarget.Data4;
      v57 = *(_QWORD *)&IID_IDropTarget.Data1;
LABEL_126:
      v59 = *(_QWORD *)&a3->Data1 - v57;
      if ( *(_QWORD *)&a3->Data1 == v57 )
        v59 = *(_QWORD *)a3->Data4 - v58;
      if ( !v59 && SHRestricted(REST_NOCDBURNING) && (unsigned int)CFSFolder::_IsCDRomFolder(v31) )
        return (unsigned int)-2147024891;
LABEL_48:
      UIHandler = CFSFolder::_CreateUIHandler(v31, a3, a4);
      if ( UIHandler >= 0 )
        return (unsigned int)UIHandler;
      v32 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
        v32 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
      if ( !v32 )
      {
        if ( !v31 )
          v7 = 0;
        return (unsigned int)SHELL32_CFSDropTarget_CreateInstance(v7, a2, a4);
      }
      if ( (*((_BYTE *)v7 + 488) & 0x20) != 0 && !(unsigned int)SHWindowsPolicy(POLID_NoHTMLViewForWebDAV) )
      {
        pv = 0;
        if ( IUnknown_QueryService(
               *((IUnknown **)v7 - 1),
               (const GUID *const)&SID_STopLevelBrowser,
               &GUID_dfd3b6b5_c10c_4be9_85f6_a66969f402f6,
               &pv) >= 0 )
        {
          LODWORD(v65) = 0;
          UIHandler = (*(__int64 (__fastcall **)(LPVOID, volatile signed __int32 **))(*(_QWORD *)pv + 96LL))(pv, &v65);
          if ( UIHandler < 0 )
            goto LABEL_134;
          if ( ((unsigned __int8)v65 & 0x20) != 0 )
          {
            ppv = 0;
            v64 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&ppv);
            UIHandler = CFSFolder::GetFolderPath(v31, v64);
            if ( UIHandler >= 0 )
              UIHandler = SHELL32_CreateSharePointView(ppv, a3, a4);
            if ( ppv )
              CoTaskMemFree(ppv);
LABEL_134:
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            if ( UIHandler >= 0 )
              return (unsigned int)UIHandler;
            goto LABEL_53;
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        }
      }
LABEL_53:
      v66 = 32;
      TokenHandle = 0;
      v68 = 0;
      UIHandler = (**(__int64 (__fastcall ***)(CFSFolder *, GUID *, struct _ITEMIDLIST_ABSOLUTE **))v31)(
                    v31,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    &TokenHandle);
      if ( UIHandler >= 0 )
      {
        if ( v31 )
          v33 = (char *)v7 + 264;
        else
          v33 = 0;
        SHELL32_CFSFolderCallback_Create(v33, (char *)&v68 + 8);
        UIHandler = SHELL32_SHCreateShellFolderView(&v66, a4);
        if ( *((_QWORD *)&v68 + 1) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v68 + 1) + 16LL))(*((_QWORD *)&v68 + 1));
        (*(void (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
      }
      return (unsigned int)UIHandler;
    }
    pv = 0;
    v61 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    UIHandler = CFSFolder::GetFolderPath(v31, v61);
    if ( UIHandler >= 0 )
    {
      DriveNumberW = PathGetDriveNumberW((LPCWSTR)pv);
      if ( DriveNumberW != -1 )
      {
        if ( _bittest((const int *)&v60, DriveNumberW) )
        {
          v58 = *(_QWORD *)IID_IDropTarget.Data4;
          v57 = *(_QWORD *)&IID_IDropTarget.Data1;
          if ( !a2 )
            goto LABEL_136;
          v55 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
            v55 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
          if ( !v55 )
          {
LABEL_136:
            UIHandler = -2147024891;
LABEL_123:
            if ( pv )
            {
              CoTaskMemFree(pv);
              v58 = *(_QWORD *)IID_IDropTarget.Data4;
              v57 = *(_QWORD *)&IID_IDropTarget.Data1;
            }
            if ( UIHandler < 0 )
              return (unsigned int)UIHandler;
            goto LABEL_126;
          }
          ppv = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID53375151>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID53375151>::GetImpl'::`2'::impl) )
          {
            v56 = Shell32Instance::get((Shell32Instance *)&ppv);
            MessageBoxHelper::ShellMessageBoxTextScaled__(v56, a2, (LPCWSTR)0x2601, (LPCWSTR)0x2600);
          }
          else
          {
            v63 = Shell32Instance::get((Shell32Instance *)&ppv);
            ShellMessageBoxW(v63, a2, (LPCWSTR)0x2601, (LPCWSTR)0x2600, 0x10u);
          }
          UIHandler = -2147023673;
          if ( ppv )
            FreeLibrary((HMODULE)ppv);
        }
      }
    }
    v57 = *(_QWORD *)&IID_IDropTarget.Data1;
    v58 = *(_QWORD *)IID_IDropTarget.Data4;
    goto LABEL_123;
  }
  v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( v10 )
  {
    v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICategoryProvider.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICategoryProvider.Data1 )
      v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICategoryProvider.Data4;
    if ( v11 )
    {
      v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferSource.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource.Data1 )
        v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferSource.Data4;
      if ( !v12 )
        goto LABEL_19;
      v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferSource2.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource2.Data1 )
        v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferSource2.Data4;
      if ( !v13 )
        goto LABEL_19;
      v18 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferDestination.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferDestination.Data1 )
        v18 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferDestination.Data4;
      if ( !v18 )
        goto LABEL_19;
      v19 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferHelper.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferHelper.Data1 )
        v19 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferHelper.Data4;
      if ( !v19 )
      {
LABEL_19:
        ppv = 0;
        v14 = (const ITEMIDLIST *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 33) + 144LL))((char *)this + 264);
        UIHandler = SHCreateItemFromIDList(v14, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
        if ( UIHandler < 0 )
          return (unsigned int)UIHandler;
        pv = 0;
        v16 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
        UIHandler = CFSFolder::GetFolderPath((CFSFolder *)((char *)v7 - 48), v16);
        if ( UIHandler >= 0 )
          UIHandler = CFSTransfer::s_CreateInstance((IUnknown *)ppv, a2, (LPCWSTR)pv, a3, a4);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        v17 = pv;
        goto LABEL_88;
      }
      v20 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1 )
        v20 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data4;
      if ( !v20 )
        return (unsigned int)CoCreateInstance(&GUID_1c0f439d_7c29_4bde_8952_4eeb6a49e048, 0, 1u, a3, a4);
      v21 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1 )
        v21 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data4;
      if ( !v21 )
      {
        v30 = (char *)this - 48;
        if ( (*((_DWORD *)v30 + 134) & 0x200) != 0 )
          return (unsigned int)(**(__int64 (__fastcall ***)(char *, struct _GUID *, void **))v30)(v30, a3, a4);
        else
          return (unsigned int)-2147467262;
      }
      v22 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IIdentityName.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IIdentityName.Data1 )
        v22 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IIdentityName.Data4;
      UIHandler = -2147467262;
      if ( !v22 )
      {
        pv = 0;
        p_pv = &pv;
        v66 = (__int64)&pv;
        v24 = 1;
        LOBYTE(v68) = 1;
        v25 = 0;
        TokenHandle = 0;
        v26 = (struct _GUID *)((char *)this + 448);
        v27 = *(_QWORD *)&v26->Data1 - *(_QWORD *)&GUID_NULL.Data1;
        if ( *(_QWORD *)&v26->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
          v27 = *(_QWORD *)v26->Data4 - *(_QWORD *)GUID_NULL.Data4;
        if ( v27 )
        {
          v28 = SHGetKnownFolderIDList_Internal(v26, 0x1000u, 0, &TokenHandle);
          v24 = v68;
          v25 = TokenHandle;
          p_pv = (LPVOID *)v66;
        }
        else
        {
          v28 = -2147467259;
          v34 = (const ITEMIDLIST *)*((_QWORD *)v7 + 49);
          if ( v34 )
          {
            v25 = ILClone(v34);
            v28 = 0;
            if ( !v25 )
              v28 = -2147024882;
          }
        }
        v35 = v28 >= 0;
        if ( v24 )
        {
          v36 = *p_pv;
          *p_pv = v25;
          if ( v36 )
            CoTaskMemFree(v36);
        }
        if ( v35 )
        {
          *a4 = 0;
          for ( i = 0; ; ++i )
          {
            if ( i >= 9 )
            {
              UIHandler = -2147024809;
              goto LABEL_87;
            }
            v38 = (_QWORD *)*((_QWORD *)&off_180682360 + (int)i);
            v39 = *v38 - *(_QWORD *)&a3->Data1;
            if ( *v38 == *(_QWORD *)&a3->Data1 )
              v39 = v38[1] - *(_QWORD *)a3->Data4;
            if ( !v39 )
              break;
          }
          v40 = pv;
          ppv = 0;
          v65 = 0;
          inited = -2147024882;
          v42 = (CShellItem *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v42 )
            goto LABEL_79;
          v43 = CShellItem::CShellItem(v42);
          v44 = v43;
          if ( !v43 )
            goto LABEL_79;
          inited = CObjectWithThreadUseDetection::InitApartmentId((CShellItem *)((char *)v43 + 80));
          if ( inited >= 0 )
            inited = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, volatile signed __int32 **))v44)(
                       v44,
                       &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
                       &v65);
          (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v44 + 16LL))(v44);
          if ( inited < 0 )
            goto LABEL_101;
          inited = (*(__int64 (__fastcall **)(volatile signed __int32 *, LPVOID))(*(_QWORD *)v65 + 32LL))(v65, v40);
          if ( inited >= 0 )
            inited = (**(__int64 (__fastcall ***)(volatile signed __int32 *, GUID *, void **))v65)(
                       v65,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &ppv);
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 16LL))(v65);
LABEL_79:
          if ( inited < 0 )
          {
LABEL_101:
            UIHandler = inited;
            goto LABEL_87;
          }
          v45 = ppv;
          *a4 = 0;
          v46 = (volatile signed __int32 *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          v47 = v46;
          v65 = v46;
          if ( v46 )
          {
            *(_QWORD *)v46 = &CRelatedItem::`vftable';
            *((_DWORD *)v46 + 2) = 1;
            *((_QWORD *)v46 + 2) = v45;
            *((_QWORD *)v46 + 3) = a3;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 8LL))(v45);
            *a4 = 0;
            v48 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
            if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
              v48 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
            if ( !v48 )
              goto LABEL_84;
            v49 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IRelatedItem.Data1;
            if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IRelatedItem.Data1 )
              v49 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IRelatedItem.Data4;
            if ( !v49 )
              goto LABEL_84;
            v50 = (_QWORD *)*((_QWORD *)v47 + 3);
            v51 = *(_QWORD *)&a3->Data1 - *v50;
            if ( *(_QWORD *)&a3->Data1 == *v50 )
              v51 = *(_QWORD *)a3->Data4 - v50[1];
            if ( !v51 )
            {
LABEL_84:
              UIHandler = 0;
              *a4 = (void *)v47;
              _InterlockedIncrement(v47 + 2);
            }
            if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
            {
              *(_QWORD *)v47 = &CRelatedItem::`vftable';
              v52 = *((_QWORD *)v47 + 2);
              *((_QWORD *)v47 + 2) = 0;
              if ( v52 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              operator delete((void *)v47, (const struct std::nothrow_t *)0x20);
            }
          }
          else
          {
            UIHandler = -2147024882;
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
LABEL_87:
        v17 = pv;
        pv = 0;
LABEL_88:
        if ( v17 )
          CoTaskMemFree(v17);
      }
    }
    else
    {
      pv = 0;
      RegOpenKeyExW(HKEY_CLASSES_ROOT, L"Directory\\shellex\\Category", 0, 0x20019u, (PHKEY)&pv);
      if ( v7 == (CFSFolder *)48 )
        v7 = 0;
      UIHandler = CCategoryProvider_CreateWithParams(0, 0, (HKEY)pv, 0, (IUnknown *)v7, a3, a4);
      RegCloseKey((HKEY)pv);
    }
  }
  else
  {
    v53 = (char *)this + 264;
    v54 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 33) + 144LL))((char *)this + 264);
    if ( v7 == (CFSFolder *)48 )
      v53 = 0;
    return (unsigned int)SHELL32_CreateFileFolderContextMenu(v53, v54, a2, a3, a4);
  }
  return (unsigned int)UIHandler;
}

```

## disassembly

```asm
0x1801d5820  push    rbp
0x1801d5822  push    rbx
0x1801d5823  push    rsi
0x1801d5824  push    rdi
0x1801d5825  push    r12
0x1801d5827  push    r13
0x1801d5829  push    r14
0x1801d582b  push    r15
0x1801d582d  lea     rbp, [rsp-1Fh]
0x1801d5832  sub     rsp, 88h
0x1801d5839  mov     rax, cs:__security_cookie
0x1801d5840  xor     rax, rsp
0x1801d5843  mov     [rbp+57h+var_48], rax
0x1801d5847  mov     r15, r9
0x1801d584a  mov     rbx, r8
0x1801d584d  mov     r14, rdx
0x1801d5850  mov     r13, rcx
0x1801d5853  xor     esi, esi
0x1801d5855  mov     [r9], rsi
0x1801d5858  mov     rax, [r8]
0x1801d585b  sub     rax, qword ptr cs:IID_IShellView.Data1
0x1801d5862  jnz     short loc_1801D586F
0x1801d5864  mov     rax, [r8+8]
0x1801d5868  sub     rax, qword ptr cs:IID_IShellView.Data4
0x1801d586f  test    rax, rax
0x1801d5872  jz      loc_1801D5B13
0x1801d5878  mov     rax, [r8]
0x1801d587b  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x1801d5882  jnz     short loc_1801D588F
0x1801d5884  mov     rax, [r8+8]
0x1801d5888  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x1801d588f  test    rax, rax
0x1801d5892  jz      loc_1801D5B13
0x1801d5898  mov     rax, [r8]
0x1801d589b  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1801d58a2  jnz     short loc_1801D58AF
0x1801d58a4  mov     rax, [r8+8]
0x1801d58a8  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1801d58af  test    rax, rax
0x1801d58b2  jz      loc_1801D5E85
0x1801d58b8  mov     rax, [r8]
0x1801d58bb  sub     rax, qword ptr cs:IID_ICategoryProvider.Data1
0x1801d58c2  jnz     short loc_1801D58CF
0x1801d58c4  mov     rax, [r8+8]
0x1801d58c8  sub     rax, qword ptr cs:IID_ICategoryProvider.Data4
0x1801d58cf  test    rax, rax
0x1801d58d2  jz      loc_1801D5EF0
0x1801d58d8  mov     rax, [r8]
0x1801d58db  sub     rax, qword ptr cs:IID_ITransferSource.Data1
0x1801d58e2  jnz     short loc_1801D58EF
0x1801d58e4  mov     rax, [r8+8]
0x1801d58e8  sub     rax, qword ptr cs:IID_ITransferSource.Data4
0x1801d58ef  test    rax, rax
0x1801d58f2  jz      short loc_1801D5914
0x1801d58f4  mov     rax, [r8]
0x1801d58f7  sub     rax, qword ptr cs:IID_ITransferSource2.Data1
0x1801d58fe  jnz     short loc_1801D590B
0x1801d5900  mov     rax, [r8+8]
0x1801d5904  sub     rax, qword ptr cs:IID_ITransferSource2.Data4
0x1801d590b  test    rax, rax
0x1801d590e  jnz     loc_1801D59A2
0x1801d5914  mov     [rbp+57h+ppv], rsi
0x1801d5918  mov     rax, [rcx+108h]
0x1801d591f  add     rcx, 108h
0x1801d5926  mov     rax, [rax+90h]
0x1801d592d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d5932  lea     r8, [rbp+57h+ppv]; ppv
0x1801d5936  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1801d593d  mov     rcx, rax; pidl
0x1801d5940  call    SHCreateItemFromIDList
0x1801d5945  mov     edi, eax
0x1801d5947  test    eax, eax
0x1801d5949  js      loc_1801D5AD5
0x1801d594f  mov     [rbp+57h+pv], rsi
0x1801d5953  lea     rcx, [rbp+57h+pv]
0x1801d5957  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1801d595c  mov     rdx, rax; unsigned __int16 **
0x1801d595f  lea     rcx, [r13-30h]; this
0x1801d5963  call    ?GetFolderPath@CFSFolder@@QEAAJPEAPEAG@Z; CFSFolder::GetFolderPath(ushort * *)
0x1801d5968  mov     edi, eax
0x1801d596a  test    eax, eax
0x1801d596c  js      short loc_1801D5988
0x1801d596e  mov     [rsp+0C0h+phkResult], r15; ppv
0x1801d5973  mov     r9, rbx; riid
0x1801d5976  mov     r8, [rbp+57h+pv]; psz
0x1801d597a  mov     rdx, r14; HWND
0x1801d597d  mov     rcx, [rbp+57h+ppv]; punk
0x1801d5981  call    ?s_CreateInstance@CFSTransfer@@SAJPEAUIShellItem@@PEAUHWND__@@PEBGAEBU_GUID@@PEAPEAX@Z; CFSTransfer::s_CreateInstance(IShellItem *,HWND__ *,ushort const *,_GUID const &,void * *)
0x1801d5986  mov     edi, eax
0x1801d5988  mov     rcx, [rbp+57h+ppv]
0x1801d598c  mov     rax, [rcx]
0x1801d598f  mov     rax, [rax+10h]
0x1801d5993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d5998  nop
0x1801d5999  mov     rcx, [rbp+57h+pv]
0x1801d599d  jmp     loc_1801D5DF4
0x1801d59a2  mov     rax, [r8]
0x1801d59a5  sub     rax, qword ptr cs:IID_ITransferDestination.Data1
0x1801d59ac  jnz     short loc_1801D59B9
0x1801d59ae  mov     rax, [r8+8]
0x1801d59b2  sub     rax, qword ptr cs:IID_ITransferDestination.Data4
0x1801d59b9  test    rax, rax
0x1801d59bc  jz      loc_1801D5914
0x1801d59c2  mov     rax, [r8]
0x1801d59c5  sub     rax, qword ptr cs:IID_ITransferHelper.Data1
0x1801d59cc  jnz     short loc_1801D59D9
0x1801d59ce  mov     rax, [r8+8]
0x1801d59d2  sub     rax, qword ptr cs:IID_ITransferHelper.Data4
0x1801d59d9  test    rax, rax
0x1801d59dc  jz      loc_1801D5914
0x1801d59e2  mov     rax, [r8]
0x1801d59e5  sub     rax, qword ptr cs:_GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1
0x1801d59ec  jnz     short loc_1801D59F9
0x1801d59ee  mov     rax, [r8+8]
0x1801d59f2  sub     rax, qword ptr cs:_GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data4
0x1801d59f9  test    rax, rax
0x1801d59fc  jz      loc_1801D5AB0
0x1801d5a02  mov     rax, [r8]
0x1801d5a05  sub     rax, qword ptr cs:_GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1
0x1801d5a0c  jnz     short loc_1801D5A19
0x1801d5a0e  mov     rax, [r8+8]
0x1801d5a12  sub     rax, qword ptr cs:_GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data4
0x1801d5a19  test    rax, rax
0x1801d5a1c  jz      loc_1801D5AF8
0x1801d5a22  mov     rax, [r8]
0x1801d5a25  sub     rax, qword ptr cs:IID_IIdentityName.Data1
0x1801d5a2c  jnz     short loc_1801D5A39
0x1801d5a2e  mov     rax, [r8+8]
0x1801d5a32  sub     rax, qword ptr cs:IID_IIdentityName.Data4
0x1801d5a39  mov     edi, 80004002h
0x1801d5a3e  test    rax, rax
0x1801d5a41  jnz     loc_1801D5AD5
0x1801d5a47  mov     [rbp+57h+pv], rsi
0x1801d5a4b  lea     r14, [rbp+57h+pv]
0x1801d5a4f  mov     [rbp+57h+var_78], r14
0x1801d5a53  mov     r12b, 1
0x1801d5a56  mov     byte ptr [rbp+57h+var_68], r12b
0x1801d5a5a  mov     rdx, rsi
0x1801d5a5d  mov     [rbp+57h+TokenHandle], rdx
0x1801d5a61  add     rcx, 1C0h; struct _GUID *
0x1801d5a68  mov     rax, [rcx]
0x1801d5a6b  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1801d5a72  jnz     short loc_1801D5A7F
0x1801d5a74  mov     rax, [rcx+8]
0x1801d5a78  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1801d5a7f  test    rax, rax
0x1801d5a82  jz      loc_1801D5BF7
0x1801d5a88  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1801d5a8c  xor     r8d, r8d; void *
0x1801d5a8f  mov     edx, 1000h; unsigned int
0x1801d5a94  call    SHGetKnownFolderIDList_Internal
0x1801d5a99  mov     esi, eax
0x1801d5a9b  movzx   r12d, byte ptr [rbp+57h+var_68]
0x1801d5aa0  mov     rdx, [rbp+57h+TokenHandle]
0x1801d5aa4  mov     r14, [rbp+57h+var_78]
0x1801d5aa8  xor     r13d, r13d
0x1801d5aab  jmp     loc_1801D5C25
0x1801d5ab0  mov     [rsp+0C0h+phkResult], r15; ppv
0x1801d5ab5  mov     r9, rbx; riid
0x1801d5ab8  xor     edx, edx; pUnkOuter
0x1801d5aba  mov     r8d, 1; dwClsContext
0x1801d5ac0  lea     rcx, _GUID_1c0f439d_7c29_4bde_8952_4eeb6a49e048; rclsid
0x1801d5ac7  call    cs:__imp_CoCreateInstance
0x1801d5ace  nop     dword ptr [rax+rax+00h]
0x1801d5ad3  mov     edi, eax
0x1801d5ad5  mov     eax, edi
0x1801d5ad7  mov     rcx, [rbp+57h+var_48]
0x1801d5adb  xor     rcx, rsp; StackCookie
0x1801d5ade  call    __security_check_cookie
0x1801d5ae3  add     rsp, 88h
0x1801d5aea  pop     r15
0x1801d5aec  pop     r14
0x1801d5aee  pop     r13
0x1801d5af0  pop     r12
0x1801d5af2  pop     rdi
0x1801d5af3  pop     rsi
0x1801d5af4  pop     rbx
0x1801d5af5  pop     rbp
0x1801d5af6  retn
0x1801d5af8  add     rcx, 0FFFFFFFFFFFFFFD0h
0x1801d5afc  test    dword ptr [rcx+218h], 200h
0x1801d5b06  jnz     loc_1801D5F61
0x1801d5b0c  mov     edi, 80004002h
0x1801d5b11  jmp     short loc_1801D5AD5
0x1801d5b13  lea     rsi, [rcx-30h]
0x1801d5b17  cmp     dword ptr [rsi+238h], 0
0x1801d5b1e  jz      loc_1806718AE
0x1801d5b24  mov     r8, r15; void **
0x1801d5b27  mov     rdx, rbx; struct _GUID *
0x1801d5b2a  mov     rcx, rsi; this
0x1801d5b2d  call    ?_CreateUIHandler@CFSFolder@@IEAAJAEBU_GUID@@PEAPEAX@Z; CFSFolder::_CreateUIHandler(_GUID const &,void * *)
0x1801d5b32  mov     edi, eax
0x1801d5b34  test    eax, eax
0x1801d5b36  jns     short loc_1801D5AD5
0x1801d5b38  mov     rax, [rbx]
0x1801d5b3b  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x1801d5b42  jnz     short loc_1801D5B4F
0x1801d5b44  mov     rax, [rbx+8]
0x1801d5b48  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x1801d5b4f  test    rax, rax
0x1801d5b52  jz      loc_1801D5ECD
0x1801d5b58  test    byte ptr [r13+1E8h], 20h
0x1801d5b60  jnz     loc_18067196C
0x1801d5b66  mov     [rbp+57h+var_78], 20h ; ' '
0x1801d5b6e  mov     [rbp+57h+TokenHandle], 0
0x1801d5b76  xorps   xmm0, xmm0
0x1801d5b79  movups  [rbp+57h+var_68], xmm0
0x1801d5b7d  mov     rax, [rsi]
0x1801d5b80  lea     r8, [rbp+57h+TokenHandle]
0x1801d5b84  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1801d5b8b  mov     rcx, rsi
0x1801d5b8e  mov     rax, [rax]
0x1801d5b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d5b96  mov     edi, eax
0x1801d5b98  test    eax, eax
0x1801d5b9a  js      loc_1801D5AD5
0x1801d5ba0  test    rsi, rsi
0x1801d5ba3  jz      loc_1801D5F9E
0x1801d5ba9  lea     rcx, [r13+108h]
0x1801d5bb0  lea     rdx, [rbp+57h+var_68+8]
0x1801d5bb4  call    cs:__imp_SHELL32_CFSFolderCallback_Create
0x1801d5bbb  nop     dword ptr [rax+rax+00h]
0x1801d5bc0  mov     rdx, r15
0x1801d5bc3  lea     rcx, [rbp+57h+var_78]
0x1801d5bc7  call    cs:__imp_SHELL32_SHCreateShellFolderView
0x1801d5bce  nop     dword ptr [rax+rax+00h]
0x1801d5bd3  mov     edi, eax
0x1801d5bd5  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x1801d5bd9  test    rcx, rcx
0x1801d5bdc  jnz     loc_1801D5F8D
0x1801d5be2  mov     rcx, [rbp+57h+TokenHandle]
0x1801d5be6  mov     rax, [rcx]
0x1801d5be9  mov     rax, [rax+10h]
0x1801d5bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d5bf2  jmp     loc_1801D5AD5
0x1801d5bf7  mov     esi, 80004005h
0x1801d5bfc  mov     rcx, [r13+188h]; pidl
0x1801d5c03  test    rcx, rcx
0x1801d5c06  jz      loc_1801D5AA8
0x1801d5c0c  call    ILClone
0x1801d5c11  mov     rdx, rax
0x1801d5c14  xor     r13d, r13d
0x1801d5c17  mov     esi, r13d
0x1801d5c1a  test    rax, rax
0x1801d5c1d  mov     eax, 8007000Eh
0x1801d5c22  cmovz   esi, eax
0x1801d5c25  shr     esi, 1Fh
0x1801d5c28  xor     sil, 1
0x1801d5c2c  test    r12b, r12b
0x1801d5c2f  jz      short loc_1801D5C48
0x1801d5c31  mov     rcx, [r14]; pv
0x1801d5c34  mov     [r14], rdx
0x1801d5c37  test    rcx, rcx
0x1801d5c3a  jz      short loc_1801D5C48
0x1801d5c3c  call    cs:__imp_CoTaskMemFree
0x1801d5c43  nop     dword ptr [rax+rax+00h]
0x1801d5c48  test    sil, sil
0x1801d5c4b  jz      loc_1801D5DEC
0x1801d5c51  mov     [r15], r13
0x1801d5c54  mov     ecx, r13d
0x1801d5c57  lea     r8, off_180682360
0x1801d5c5e  cmp     ecx, 9
0x1801d5c61  jnb     loc_1801D5F83
0x1801d5c67  movsxd  rax, ecx
0x1801d5c6a  mov     rdx, [r8+rax*8]
0x1801d5c6e  mov     rax, [rdx]
0x1801d5c71  sub     rax, [rbx]
0x1801d5c74  jnz     short loc_1801D5C7E
0x1801d5c76  mov     rax, [rdx+8]
0x1801d5c7a  sub     rax, [rbx+8]
0x1801d5c7e  test    rax, rax
0x1801d5c81  jnz     loc_1801D5E0E
0x1801d5c87  mov     r12, [rbp+57h+pv]
0x1801d5c8b  mov     [rbp+57h+ppv], r13
0x1801d5c8f  mov     [rbp+57h+var_80], r13
0x1801d5c93  mov     esi, 8007000Eh
0x1801d5c98  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801d5c9f  mov     ecx, 0D8h; unsigned __int64
0x1801d5ca4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801d5ca9  test    rax, rax
0x1801d5cac  jz      loc_1801D5D4C
0x1801d5cb2  mov     rcx, rax; this
0x1801d5cb5  call    ??0CShellItem@@QEAA@XZ; CShellItem::CShellItem(void)
0x1801d5cba  mov     r14, rax
0x1801d5cbd  test    rax, rax
0x1801d5cc0  jz      loc_1801D5D4C
0x1801d5cc6  lea     rcx, [rax+50h]; this
0x1801d5cca  call    ?InitApartmentId@CObjectWithThreadUseDetection@@QEAAJXZ; CObjectWithThreadUseDetection::InitApartmentId(void)
0x1801d5ccf  mov     esi, eax
0x1801d5cd1  test    eax, eax
0x1801d5cd3  js      short loc_1801D5CF0
0x1801d5cd5  mov     rcx, [r14]
0x1801d5cd8  mov     rax, [rcx]
0x1801d5cdb  lea     r8, [rbp+57h+var_80]
0x1801d5cdf  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x1801d5ce6  mov     rcx, r14
0x1801d5ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d5cee  mov     esi, eax
0x1801d5cf0  mov     rax, [r14]
0x1801d5cf3  mov     rcx, r14
  ... truncated ...
```
