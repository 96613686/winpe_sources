# CFSFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180091920`
- end: `0x18009218e`
- name: `?CreateViewObject@CFSFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `2158`
- prototype: `int(CFSFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180040290`
- `0x180041b00`
- `0x180047ec0`
- `0x180048fb0`
- `0x1800495e0`
- `0x180091920`
- `0x180093c20`
- `0x1800d13a0`
- `0x1800d7650`
- `0x180107be0`
- `0x1801cfffc`
- `0x18021dbd0`
- `0x1802e28c0`
- `0x18031afec`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a518c`
- `0x18050dd44`
- `0x180517614`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800920db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800920db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009202a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009202a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091ff4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091ff4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180641eff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180641eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800920f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092161`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091aa6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800920f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092161`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180091b21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180091b21`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180641f79`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180641f79`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180641fa5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180641fa5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180641f53`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!ShellMessageBoxW` at `0x180641f53`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHCreateShellFolderView` at `0x180091cc5`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHCreateShellFolderView` at `0x180091cc5`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateSharePointView` at `0x18064200e`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateSharePointView` at `0x18064200e`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSDropTarget_CreateInstance` at `0x180091fc3`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSDropTarget_CreateInstance` at `0x180091fc3`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSFolderCallback_Create` at `0x180091cb8`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CFSFolderCallback_Create` at `0x180091cb8`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateFileFolderContextMenu` at `0x180091fa6`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CreateFileFolderContextMenu` at `0x180091fa6`

## string_xrefs

- `0x180091fe6`: `Directory\shellex\Category`

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
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  LPVOID *p_pv; // r14
  char v24; // r12
  void *v25; // rdx
  struct _GUID *v26; // rcx
  __int64 v27; // rax
  int v28; // esi
  char *v29; // rcx
  CFSFolder *v30; // rsi
  __int64 v31; // rax
  char *v32; // rcx
  const ITEMIDLIST *v33; // rcx
  bool v34; // si
  void *v35; // rcx
  unsigned int i; // ecx
  _QWORD *v37; // rdx
  __int64 v38; // rax
  LPVOID v39; // r12
  int inited; // esi
  CShellItem *v41; // rax
  CShellItem *v42; // rax
  CShellItem *v43; // r14
  void *v44; // r14
  volatile signed __int32 *v45; // rax
  volatile signed __int32 *v46; // rsi
  __int64 v47; // rax
  void *v48; // rcx
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
    goto LABEL_48;
  v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
    v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
  if ( !v9 )
  {
LABEL_48:
    v30 = (CFSFolder *)((char *)this - 48);
    if ( *((_DWORD *)this + 130) )
      goto LABEL_49;
    v60 = SHRestricted(REST_NOVIEWONDRIVE);
    if ( !v60 )
    {
      v58 = *(_QWORD *)IID_IDropTarget.Data4;
      v57 = *(_QWORD *)&IID_IDropTarget.Data1;
LABEL_126:
      v59 = *(_QWORD *)&a3->Data1 - v57;
      if ( *(_QWORD *)&a3->Data1 == v57 )
        v59 = *(_QWORD *)a3->Data4 - v58;
      if ( !v59 && SHRestricted(REST_NOCDBURNING) && (unsigned int)CFSFolder::_IsCDRomFolder(v30) )
        return (unsigned int)-2147024891;
LABEL_49:
      UIHandler = CFSFolder::_CreateUIHandler(v30, a3, a4);
      if ( UIHandler >= 0 )
        return (unsigned int)UIHandler;
      v31 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IDropTarget.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IDropTarget.Data1 )
        v31 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IDropTarget.Data4;
      if ( !v31 )
      {
        if ( !v30 )
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
            UIHandler = CFSFolder::GetFolderPath(v30, v64);
            if ( UIHandler >= 0 )
              UIHandler = SHELL32_CreateSharePointView(ppv, a3, a4);
            if ( ppv )
              CoTaskMemFree(ppv);
LABEL_134:
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
            if ( UIHandler >= 0 )
              return (unsigned int)UIHandler;
            goto LABEL_54;
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        }
      }
LABEL_54:
      v66 = 32;
      TokenHandle = 0;
      v68 = 0;
      UIHandler = (**(__int64 (__fastcall ***)(CFSFolder *, GUID *, struct _ITEMIDLIST_ABSOLUTE **))v30)(
                    v30,
                    &GUID_000214e6_0000_0000_c000_000000000046,
                    &TokenHandle);
      if ( UIHandler >= 0 )
      {
        if ( v30 )
          v32 = (char *)v7 + 264;
        else
          v32 = 0;
        SHELL32_CFSFolderCallback_Create(v32, (char *)&v68 + 8);
        UIHandler = SHELL32_SHCreateShellFolderView(&v66, a4);
        if ( *((_QWORD *)&v68 + 1) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v68 + 1) + 16LL))(*((_QWORD *)&v68 + 1));
        (*(void (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE *))(*(_QWORD *)TokenHandle + 16LL))(TokenHandle);
      }
      return (unsigned int)UIHandler;
    }
    pv = 0;
    v61 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
    UIHandler = CFSFolder::GetFolderPath(v30, v61);
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
      v17 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferDestination.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferDestination.Data1 )
        v17 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferDestination.Data4;
      if ( !v17 )
        goto LABEL_19;
      v18 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferHelper.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferHelper.Data1 )
        v18 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferHelper.Data4;
      if ( v18 )
      {
        v19 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1;
        if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1 )
          v19 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data4;
        if ( v19 )
        {
          v21 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1 )
            v21 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data4;
          if ( v21 )
          {
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
                v33 = (const ITEMIDLIST *)*((_QWORD *)v7 + 49);
                if ( v33 )
                {
                  v25 = ILClone(v33);
                  v28 = 0;
                  if ( !v25 )
                    v28 = -2147024882;
                }
              }
              v34 = v28 >= 0;
              if ( v24 )
              {
                v35 = *p_pv;
                *p_pv = v25;
                if ( v35 )
                  CoTaskMemFree(v35);
              }
              if ( v34 )
              {
                *a4 = 0;
                for ( i = 0; ; ++i )
                {
                  if ( i >= 9 )
                  {
                    UIHandler = -2147024809;
                    goto LABEL_88;
                  }
                  v37 = (_QWORD *)*((_QWORD *)&off_18067B650 + (int)i);
                  v38 = *v37 - *(_QWORD *)&a3->Data1;
                  if ( *v37 == *(_QWORD *)&a3->Data1 )
                    v38 = v37[1] - *(_QWORD *)a3->Data4;
                  if ( !v38 )
                    break;
                }
                v39 = pv;
                ppv = 0;
                v65 = 0;
                inited = -2147024882;
                v41 = (CShellItem *)operator new(0xD8u, (const struct std::nothrow_t *)&std::nothrow);
                if ( !v41 )
                  goto LABEL_80;
                v42 = CShellItem::CShellItem(v41);
                v43 = v42;
                if ( !v42 )
                  goto LABEL_80;
                inited = CObjectWithThreadUseDetection::InitApartmentId((CShellItem *)((char *)v42 + 80));
                if ( inited >= 0 )
                  inited = (**(__int64 (__fastcall ***)(CShellItem *, GUID *, volatile signed __int32 **))v43)(
                             v43,
                             &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
                             &v65);
                (*(void (__fastcall **)(CShellItem *))(*(_QWORD *)v43 + 16LL))(v43);
                if ( inited < 0 )
                  goto LABEL_101;
                inited = (*(__int64 (__fastcall **)(volatile signed __int32 *, LPVOID))(*(_QWORD *)v65 + 32LL))(
                           v65,
                           v39);
                if ( inited >= 0 )
                  inited = (**(__int64 (__fastcall ***)(volatile signed __int32 *, GUID *, void **))v65)(
                             v65,
                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                             &ppv);
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 16LL))(v65);
LABEL_80:
                if ( inited < 0 )
                {
LABEL_101:
                  UIHandler = inited;
                  goto LABEL_88;
                }
                v44 = ppv;
                *a4 = 0;
                v45 = (volatile signed __int32 *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
                v46 = v45;
                v65 = v45;
                if ( v45 )
                {
                  *(_QWORD *)v45 = &CRelatedItem::`vftable';
                  *((_DWORD *)v45 + 2) = 1;
                  *((_QWORD *)v45 + 2) = v44;
                  *((_QWORD *)v45 + 3) = a3;
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v44 + 8LL))(v44);
                  *a4 = 0;
                  v47 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
                  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
                    v47 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
                  if ( !v47 )
                    goto LABEL_85;
                  v49 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IRelatedItem.Data1;
                  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IRelatedItem.Data1 )
                    v49 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IRelatedItem.Data4;
                  if ( !v49 )
                    goto LABEL_85;
                  v50 = (_QWORD *)*((_QWORD *)v46 + 3);
                  v51 = *(_QWORD *)&a3->Data1 - *v50;
                  if ( *(_QWORD *)&a3->Data1 == *v50 )
                    v51 = *(_QWORD *)a3->Data4 - v50[1];
                  if ( !v51 )
                  {
LABEL_85:
                    UIHandler = 0;
                    *a4 = (void *)v46;
                    _InterlockedIncrement(v46 + 2);
                  }
                  if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
                  {
                    *(_QWORD *)v46 = &CRelatedItem::`vftable';
                    v52 = *((_QWORD *)v46 + 2);
                    *((_QWORD *)v46 + 2) = 0;
                    if ( v52 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                    operator delete((void *)v46, (const struct std::nothrow_t *)0x20);
                  }
                }
                else
                {
                  UIHandler = -2147024882;
                }
                (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
              }
LABEL_88:
              v48 = pv;
              pv = 0;
              if ( v48 )
                CoTaskMemFree(v48);
            }
          }
          else
          {
            v29 = (char *)this - 48;
            if ( (*((_DWORD *)v29 + 134) & 0x200) != 0 )
              return (unsigned int)(**(__int64 (__fastcall ***)(char *, struct _GUID *, void **))v29)(v29, a3, a4);
            else
              return (unsigned int)-2147467262;
          }
        }
        else
        {
          return (unsigned int)CoCreateInstance(&GUID_1c0f439d_7c29_4bde_8952_4eeb6a49e048, 0, 1u, a3, a4);
        }
      }
      else
      {
LABEL_19:
        ppv = 0;
        v14 = (const ITEMIDLIST *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 33) + 144LL))((char *)this + 264);
        UIHandler = SHCreateItemFromIDList(v14, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
        if ( UIHandler >= 0 )
        {
          pv = 0;
          v16 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
          UIHandler = CFSFolder::GetFolderPath((CFSFolder *)((char *)v7 - 48), v16);
          if ( UIHandler >= 0 )
            UIHandler = CFSTransfer::s_CreateInstance((IUnknown *)ppv, a2, (LPCWSTR)pv, a3, a4);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          if ( pv )
            CoTaskMemFree(pv);
        }
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
0x180091920  push    rbp
0x180091922  push    rbx
0x180091923  push    rsi
0x180091924  push    rdi
0x180091925  push    r12
0x180091927  push    r13
0x180091929  push    r14
0x18009192b  push    r15
0x18009192d  lea     rbp, [rsp-1Fh]
0x180091932  sub     rsp, 88h
0x180091939  mov     rax, cs:__security_cookie
0x180091940  xor     rax, rsp
0x180091943  mov     [rbp+57h+var_48], rax
0x180091947  mov     r15, r9
0x18009194a  mov     rbx, r8
0x18009194d  mov     r14, rdx
0x180091950  mov     r13, rcx
0x180091953  xor     esi, esi
0x180091955  mov     [r9], rsi
0x180091958  mov     rax, [r8]
0x18009195b  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180091962  jnz     short loc_18009196F
0x180091964  mov     rax, [r8+8]
0x180091968  sub     rax, qword ptr cs:IID_IShellView.Data4
0x18009196f  test    rax, rax
0x180091972  jz      loc_180091C13
0x180091978  mov     rax, [r8]
0x18009197b  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x180091982  jnz     short loc_18009198F
0x180091984  mov     rax, [r8+8]
0x180091988  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x18009198f  test    rax, rax
0x180091992  jz      loc_180091C13
0x180091998  mov     rax, [r8]
0x18009199b  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800919a2  jnz     short loc_1800919AF
0x1800919a4  mov     rax, [r8+8]
0x1800919a8  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800919af  test    rax, rax
0x1800919b2  jz      loc_180091F71
0x1800919b8  mov     rax, [r8]
0x1800919bb  sub     rax, qword ptr cs:IID_ICategoryProvider.Data1
0x1800919c2  jnz     short loc_1800919CF
0x1800919c4  mov     rax, [r8+8]
0x1800919c8  sub     rax, qword ptr cs:IID_ICategoryProvider.Data4
0x1800919cf  test    rax, rax
0x1800919d2  jz      loc_180091FD0
0x1800919d8  mov     rax, [r8]
0x1800919db  sub     rax, qword ptr cs:IID_ITransferSource.Data1
0x1800919e2  jnz     short loc_1800919EF
0x1800919e4  mov     rax, [r8+8]
0x1800919e8  sub     rax, qword ptr cs:IID_ITransferSource.Data4
0x1800919ef  test    rax, rax
0x1800919f2  jz      short loc_180091A14
0x1800919f4  mov     rax, [r8]
0x1800919f7  sub     rax, qword ptr cs:IID_ITransferSource2.Data1
0x1800919fe  jnz     short loc_180091A0B
0x180091a00  mov     rax, [r8+8]
0x180091a04  sub     rax, qword ptr cs:IID_ITransferSource2.Data4
0x180091a0b  test    rax, rax
0x180091a0e  jnz     loc_180091AAE
0x180091a14  mov     [rbp+57h+ppv], rsi
0x180091a18  mov     rax, [rcx+108h]
0x180091a1f  add     rcx, 108h
0x180091a26  mov     rax, [rax+90h]
0x180091a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a32  lea     r8, [rbp+57h+ppv]; ppv
0x180091a36  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180091a3d  mov     rcx, rax; pidl
0x180091a40  call    SHCreateItemFromIDList
0x180091a45  mov     edi, eax
0x180091a47  test    eax, eax
0x180091a49  js      loc_180091B29
0x180091a4f  mov     [rbp+57h+pv], rsi
0x180091a53  lea     rcx, [rbp+57h+pv]
0x180091a57  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180091a5c  mov     rdx, rax; unsigned __int16 **
0x180091a5f  lea     rcx, [r13-30h]; this
0x180091a63  call    ?GetFolderPath@CFSFolder@@QEAAJPEAPEAG@Z; CFSFolder::GetFolderPath(ushort * *)
0x180091a68  mov     edi, eax
0x180091a6a  test    eax, eax
0x180091a6c  js      short loc_180091A88
0x180091a6e  mov     [rsp+0C0h+phkResult], r15; ppv
0x180091a73  mov     r9, rbx; riid
0x180091a76  mov     r8, [rbp+57h+pv]; psz
0x180091a7a  mov     rdx, r14; HWND
0x180091a7d  mov     rcx, [rbp+57h+ppv]; punk
0x180091a81  call    ?s_CreateInstance@CFSTransfer@@SAJPEAUIShellItem@@PEAUHWND__@@PEBGAEBU_GUID@@PEAPEAX@Z; CFSTransfer::s_CreateInstance(IShellItem *,HWND__ *,ushort const *,_GUID const &,void * *)
0x180091a86  mov     edi, eax
0x180091a88  mov     rcx, [rbp+57h+ppv]
0x180091a8c  mov     rax, [rcx]
0x180091a8f  mov     rax, [rax+10h]
0x180091a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091a98  nop
0x180091a99  mov     rcx, [rbp+57h+pv]; pv
0x180091a9d  test    rcx, rcx
0x180091aa0  jz      loc_180091B29
0x180091aa6  call    cs:__imp_CoTaskMemFree
0x180091aac  jmp     short loc_180091B29
0x180091aae  mov     rax, [r8]
0x180091ab1  sub     rax, qword ptr cs:IID_ITransferDestination.Data1
0x180091ab8  jnz     short loc_180091AC5
0x180091aba  mov     rax, [r8+8]
0x180091abe  sub     rax, qword ptr cs:IID_ITransferDestination.Data4
0x180091ac5  test    rax, rax
0x180091ac8  jz      loc_180091A14
0x180091ace  mov     rax, [r8]
0x180091ad1  sub     rax, qword ptr cs:IID_ITransferHelper.Data1
0x180091ad8  jnz     short loc_180091AE5
0x180091ada  mov     rax, [r8+8]
0x180091ade  sub     rax, qword ptr cs:IID_ITransferHelper.Data4
0x180091ae5  test    rax, rax
0x180091ae8  jz      loc_180091A14
0x180091aee  mov     rax, [r8]
0x180091af1  sub     rax, qword ptr cs:_GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1
0x180091af8  jnz     short loc_180091B05
0x180091afa  mov     rax, [r8+8]
0x180091afe  sub     rax, qword ptr cs:_GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data4
0x180091b05  test    rax, rax
0x180091b08  jnz     short loc_180091B4B
0x180091b0a  mov     [rsp+0C0h+phkResult], r15; ppv
0x180091b0f  mov     r9, rbx; riid
0x180091b12  xor     edx, edx; pUnkOuter
0x180091b14  mov     r8d, 1; dwClsContext
0x180091b1a  lea     rcx, _GUID_1c0f439d_7c29_4bde_8952_4eeb6a49e048; rclsid
0x180091b21  call    cs:__imp_CoCreateInstance
0x180091b27  mov     edi, eax
0x180091b29  mov     eax, edi
0x180091b2b  mov     rcx, [rbp+57h+var_48]
0x180091b2f  xor     rcx, rsp; StackCookie
0x180091b32  call    __security_check_cookie
0x180091b37  add     rsp, 88h
0x180091b3e  pop     r15
0x180091b40  pop     r14
0x180091b42  pop     r13
0x180091b44  pop     r12
0x180091b46  pop     rdi
0x180091b47  pop     rsi
0x180091b48  pop     rbx
0x180091b49  pop     rbp
0x180091b4a  retn
0x180091b4b  mov     rax, [r8]
0x180091b4e  sub     rax, qword ptr cs:_GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data1
0x180091b55  jnz     short loc_180091B62
0x180091b57  mov     rax, [r8+8]
0x180091b5b  sub     rax, qword ptr cs:_GUID_dc0ac42a_141e_4876_9c43_824829440de0.Data4
0x180091b62  test    rax, rax
0x180091b65  jz      loc_180091BF5
0x180091b6b  mov     rax, [r8]
0x180091b6e  sub     rax, qword ptr cs:IID_IIdentityName.Data1
0x180091b75  jnz     short loc_180091B82
0x180091b77  mov     rax, [r8+8]
0x180091b7b  sub     rax, qword ptr cs:IID_IIdentityName.Data4
0x180091b82  mov     edi, 80004002h
0x180091b87  test    rax, rax
0x180091b8a  jnz     short loc_180091B29
0x180091b8c  mov     [rbp+57h+pv], rsi
0x180091b90  lea     r14, [rbp+57h+pv]
0x180091b94  mov     [rbp+57h+var_78], r14
0x180091b98  mov     r12b, 1
0x180091b9b  mov     byte ptr [rbp+57h+var_68], r12b
0x180091b9f  mov     rdx, rsi
0x180091ba2  mov     [rbp+57h+TokenHandle], rdx
0x180091ba6  add     rcx, 1C0h; struct _GUID *
0x180091bad  mov     rax, [rcx]
0x180091bb0  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180091bb7  jnz     short loc_180091BC4
0x180091bb9  mov     rax, [rcx+8]
0x180091bbd  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180091bc4  test    rax, rax
0x180091bc7  jz      loc_180091CEF
0x180091bcd  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180091bd1  xor     r8d, r8d; void *
0x180091bd4  mov     edx, 1000h; unsigned int
0x180091bd9  call    SHGetKnownFolderIDList_Internal
0x180091bde  mov     esi, eax
0x180091be0  movzx   r12d, byte ptr [rbp+57h+var_68]
0x180091be5  mov     rdx, [rbp+57h+TokenHandle]
0x180091be9  mov     r14, [rbp+57h+var_78]
0x180091bed  xor     r13d, r13d
0x180091bf0  jmp     loc_180091D1D
0x180091bf5  add     rcx, 0FFFFFFFFFFFFFFD0h
0x180091bf9  test    dword ptr [rcx+218h], 200h
0x180091c03  jnz     loc_180092035
0x180091c09  mov     edi, 80004002h
0x180091c0e  jmp     loc_180091B29
0x180091c13  lea     rsi, [rcx-30h]
0x180091c17  cmp     dword ptr [rsi+238h], 0
0x180091c1e  jz      loc_180641EC0
0x180091c24  mov     r8, r15; void **
0x180091c27  mov     rdx, rbx; struct _GUID *
0x180091c2a  mov     rcx, rsi; this
0x180091c2d  call    ?_CreateUIHandler@CFSFolder@@IEAAJAEBU_GUID@@PEAPEAX@Z; CFSFolder::_CreateUIHandler(_GUID const &,void * *)
0x180091c32  mov     edi, eax
0x180091c34  test    eax, eax
0x180091c36  jns     loc_180091B29
0x180091c3c  mov     rax, [rbx]
0x180091c3f  sub     rax, qword ptr cs:IID_IDropTarget.Data1
0x180091c46  jnz     short loc_180091C53
0x180091c48  mov     rax, [rbx+8]
0x180091c4c  sub     rax, qword ptr cs:IID_IDropTarget.Data4
0x180091c53  test    rax, rax
0x180091c56  jz      loc_180091FB3
0x180091c5c  test    byte ptr [r13+1E8h], 20h
0x180091c64  jnz     loc_180641F72
0x180091c6a  mov     [rbp+57h+var_78], 20h ; ' '
0x180091c72  mov     [rbp+57h+TokenHandle], 0
0x180091c7a  xorps   xmm0, xmm0
0x180091c7d  movups  [rbp+57h+var_68], xmm0
0x180091c81  mov     rax, [rsi]
0x180091c84  lea     r8, [rbp+57h+TokenHandle]
0x180091c88  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180091c8f  mov     rcx, rsi
0x180091c92  mov     rax, [rax]
0x180091c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091c9a  mov     edi, eax
0x180091c9c  test    eax, eax
0x180091c9e  js      loc_180091B29
0x180091ca4  test    rsi, rsi
0x180091ca7  jz      loc_180092072
0x180091cad  lea     rcx, [r13+108h]
0x180091cb4  lea     rdx, [rbp+57h+var_68+8]
0x180091cb8  call    cs:__imp_SHELL32_CFSFolderCallback_Create
0x180091cbe  mov     rdx, r15
0x180091cc1  lea     rcx, [rbp+57h+var_78]
0x180091cc5  call    cs:__imp_SHELL32_SHCreateShellFolderView
0x180091ccb  mov     edi, eax
0x180091ccd  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x180091cd1  test    rcx, rcx
0x180091cd4  jnz     loc_180092061
0x180091cda  mov     rcx, [rbp+57h+TokenHandle]
0x180091cde  mov     rax, [rcx]
0x180091ce1  mov     rax, [rax+10h]
0x180091ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091cea  jmp     loc_180091B29
0x180091cef  mov     esi, 80004005h
0x180091cf4  mov     rcx, [r13+188h]; pidl
0x180091cfb  test    rcx, rcx
0x180091cfe  jz      loc_180091BED
0x180091d04  call    ILClone
0x180091d09  mov     rdx, rax
0x180091d0c  xor     r13d, r13d
0x180091d0f  mov     esi, r13d
0x180091d12  test    rax, rax
0x180091d15  mov     eax, 8007000Eh
0x180091d1a  cmovz   esi, eax
0x180091d1d  shr     esi, 1Fh
0x180091d20  xor     sil, 1
0x180091d24  test    r12b, r12b
0x180091d27  jz      short loc_180091D3A
0x180091d29  mov     rcx, [r14]; pv
0x180091d2c  mov     [r14], rdx
0x180091d2f  test    rcx, rcx
0x180091d32  jz      short loc_180091D3A
0x180091d34  call    cs:__imp_CoTaskMemFree
0x180091d3a  test    sil, sil
0x180091d3d  jz      loc_180091EDE
0x180091d43  mov     [r15], r13
0x180091d46  mov     ecx, r13d
0x180091d49  lea     r8, off_18067B650
0x180091d50  cmp     ecx, 9
0x180091d53  jnb     loc_180092057
0x180091d59  movsxd  rax, ecx
0x180091d5c  mov     rdx, [r8+rax*8]
0x180091d60  mov     rax, [rdx]
0x180091d63  sub     rax, [rbx]
0x180091d66  jnz     short loc_180091D70
0x180091d68  mov     rax, [rdx+8]
0x180091d6c  sub     rax, [rbx+8]
0x180091d70  test    rax, rax
0x180091d73  jnz     loc_180091EFA
0x180091d79  mov     r12, [rbp+57h+pv]
0x180091d7d  mov     [rbp+57h+ppv], r13
0x180091d81  mov     [rbp+57h+var_80], r13
0x180091d85  mov     esi, 8007000Eh
0x180091d8a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180091d91  mov     ecx, 0D8h; unsigned __int64
0x180091d96  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180091d9b  test    rax, rax
0x180091d9e  jz      loc_180091E3E
0x180091da4  mov     rcx, rax; this
0x180091da7  call    ??0CShellItem@@QEAA@XZ; CShellItem::CShellItem(void)
0x180091dac  mov     r14, rax
0x180091daf  test    rax, rax
0x180091db2  jz      loc_180091E3E
0x180091db8  lea     rcx, [rax+50h]; this
0x180091dbc  call    ?InitApartmentId@CObjectWithThreadUseDetection@@QEAAJXZ; CObjectWithThreadUseDetection::InitApartmentId(void)
0x180091dc1  mov     esi, eax
0x180091dc3  test    eax, eax
0x180091dc5  js      short loc_180091DE2
0x180091dc7  mov     rcx, [r14]
0x180091dca  mov     rax, [rcx]
0x180091dcd  lea     r8, [rbp+57h+var_80]
0x180091dd1  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x180091dd8  mov     rcx, r14
0x180091ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091de0  mov     esi, eax
0x180091de2  mov     rax, [r14]
0x180091de5  mov     rcx, r14
0x180091de8  mov     rax, [rax+10h]
  ... truncated ...
```
