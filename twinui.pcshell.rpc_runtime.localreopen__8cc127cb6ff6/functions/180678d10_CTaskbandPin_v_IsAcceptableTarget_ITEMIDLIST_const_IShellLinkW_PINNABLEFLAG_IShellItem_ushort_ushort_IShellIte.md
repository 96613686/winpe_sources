# CTaskbandPin::v_IsAcceptableTarget(_ITEMIDLIST const *,IShellLinkW *,PINNABLEFLAG,IShellItem * *,ushort * *,ushort * *,IShellItem * *)

- ea: `0x180678d10`
- end: `0x1806795b5`
- name: `?v_IsAcceptableTarget@CTaskbandPin@@MEAAHPEFBU_ITEMIDLIST@@PEAUIShellLinkW@@W4PINNABLEFLAG@@PEAPEAUIShellItem@@PEAPEAG43@Z`
- size: `2213`
- prototype: `int __high(const struct _ITEMIDLIST *, struct IShellLinkW *, enum PINNABLEFLAG, struct IShellItem **, unsigned __int16 **, unsigned __int16 **, struct IShellItem **)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800134f8`
- `0x18005a710`
- `0x18008a6f0`
- `0x180159450`
- `0x1802789e0`
- `0x1802cd974`
- `0x180356360`
- `0x180356edc`
- `0x1804ddf5c`
- `0x1805f565c`
- `0x180677a60`
- `0x180677b10`
- `0x1806780b0`
- `0x180678300`
- `0x1806785d0`
- `0x1806788c4`
- `0x180678d10`
- `0x18067c118`
- `0x180684990`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180678f54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180678f54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067910c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067919c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067955d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067910c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067919c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18067955d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180679471`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1806794aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180679471`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1806794aa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18067920c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18067920c`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180678e24`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1806790d3`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18067932d`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180678e24`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x1806790d3`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18067932d`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1806794f4`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1806794f4`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180679280`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180679342`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1806794bc`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180679280`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180679342`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1806794bc`
- `Windows.Storage!ILIsParent` at `0x1806790ad`
- `Windows.Storage!ILIsParent` at `0x1806790ad`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x180679086`
- `Windows.Storage!SHGetKnownFolderIDList` at `0x180679086`
- `Windows.Storage!SHBindToParent` at `0x180679051`
- `Windows.Storage!SHBindToParent` at `0x180679051`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CTaskbandPin::v_IsAcceptableTarget(
        CTaskbandPin *a1,
        const ITEMIDLIST *a2,
        struct IShellLinkW *a3,
        char a4,
        struct IShellItem **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        void **a8)
{
  unsigned int v11; // r14d
  unsigned int v12; // eax
  __int64 v13; // rdx
  CPinnedList *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  HRESULT Instance; // r14d
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  struct IShellItem2 *v24; // rsi
  HRESULT (__stdcall *GetString)(IShellItem2 *, const PROPERTYKEY *const, LPWSTR *); // rdi
  CTaskbandPin *v26; // rcx
  struct IShellItem **v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  const ITEMIDLIST *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  ITEMIDLIST *v35; // rsi
  void *v36; // rdi
  int (__fastcall *v37)(void *, _QWORD, const GUID *, GUID *); // rbx
  struct IShellLinkW v38; // rax
  unsigned int v39; // ebx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  struct IShellItem2 *v46; // rcx
  ITEMIDLIST *v47; // rcx
  CPinnedList *v48; // rcx
  char v49; // bl
  ITEMIDLIST *v50; // rcx
  unsigned __int16 *v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  int v54; // r13d
  unsigned int v55; // r9d
  const ITEMIDLIST *v56; // rbx
  void **v57; // rdi
  int v58; // eax
  CPinnedList *v59; // rcx
  const struct _tagpropertykey *v60; // rdx
  CTaskbandPin *v61; // rcx
  LPITEMIDLIST v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  LPITEMIDLIST v66; // rax
  struct IShellItem *v67; // rax
  struct IShellLinkW **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  char v70; // [rsp+40h] [rbp-C0h]
  char v71; // [rsp+41h] [rbp-BFh]
  unsigned int v72; // [rsp+44h] [rbp-BCh] BYREF
  int v73; // [rsp+48h] [rbp-B8h]
  int v74; // [rsp+4Ch] [rbp-B4h]
  CTaskbandPin *v75; // [rsp+50h] [rbp-B0h]
  LPCITEMIDLIST v76; // [rsp+58h] [rbp-A8h]
  const ITEMIDLIST *v77; // [rsp+60h] [rbp-A0h]
  void **v78; // [rsp+68h] [rbp-98h]
  unsigned __int16 **v79; // [rsp+70h] [rbp-90h]
  LPCITEMIDLIST ppidlLast; // [rsp+78h] [rbp-88h] BYREF
  void *ppv; // [rsp+80h] [rbp-80h] BYREF
  LPCITEMIDLIST pidl; // [rsp+88h] [rbp-78h] BYREF
  LPITEMIDLIST ppidl[3]; // [rsp+90h] [rbp-70h] BYREF
  struct IShellLinkW *v84; // [rsp+A8h] [rbp-58h] BYREF
  struct IShellItem2 *v85; // [rsp+B0h] [rbp-50h] BYREF
  struct IApplicationResolver *v86; // [rsp+B8h] [rbp-48h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+C0h] [rbp-40h] BYREF
  void *v88; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v89[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v90[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR pszStr1[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v77 = a2;
  v75 = a1;
  v79 = a7;
  v78 = a8;
  v11 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a5 )
    *a5 = 0;
  *a7 = 0;
  v73 = a4 & 4;
  v12 = 0x40000000;
  if ( (a4 & 4) != 0 )
    v12 = 1614807040;
  v72 = v12;
  if ( (int)SHGetNameAndFlagsW(a2, 0xC000u, v90, a4, &v72) >= 0 )
  {
    v74 = a4 & 2;
    if ( (a4 & 2) == 0 || (a4 & 4) != 0 || CPinnedList::_IsLocalHardDisk(v14, v90) || (v72 & 0x40000000) == 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&ppv, v13, v15, v16);
      Instance = SHCreateItemFromIDList(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( Instance < 0 )
        goto LABEL_119;
      v85 = 0;
      if ( (int)Microsoft::WRL::ComPtr<IShellItem>::As<IShellItem2>(&ppv, &v85) < 0 )
        goto LABEL_23;
      memset(ppidl, 0, sizeof(ppidl));
      v24 = v85;
      GetString = v85->lpVtbl->GetString;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      ppidl[1] = (LPITEMIDLIST)-1LL;
      ppidl[2] = (LPITEMIDLIST)-1LL;
      if ( ((int (__fastcall *)(struct IShellItem2 *, __int128 *, LPITEMIDLIST *))GetString)(
             v24,
             &PKEY_AppUserModel_ParentID,
             ppidl) >= 0
        && (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::HasLength(ppidl) )
      {
        Instance = -2147467259;
      }
      if ( (a4 & 0x10) == 0 && !CTaskbandPin::IsPinnable(v26, v85) )
        Instance = -2147467259;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      if ( Instance >= 0 )
      {
LABEL_23:
        pidl = 0;
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&pidl, v21, v22, v23);
        if ( TaskbarPinHelper::GetTaskbarPinnableItem((TaskbarPinHelper *)ppv, (struct IShellItem *)&pidl, v27) >= 0 )
        {
          v31 = (const ITEMIDLIST *)ppv;
          ppv = (void *)pidl;
          pidl = v31;
        }
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&pidl, v28, v29, v30);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v85);
      if ( Instance < 0 )
        goto LABEL_119;
      v86 = 0;
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v86, v17, v18, v19);
      Instance = CoCreateInstance(
                   &CLSID_StartMenuCacheAndAppResolver,
                   0,
                   3u,
                   &GUID_de25675a_72de_44b4_9373_05170450c140,
                   (LPVOID *)&v86);
      if ( Instance < 0 )
      {
LABEL_118:
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v86, v32, v33, v34);
LABEL_119:
        Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&ppv, v17, v18, v19);
        return Instance >= 0;
      }
      v71 = 0;
      v70 = 0;
      memset_0(v89, 0, 0x208u);
      v84 = a3;
      if ( a3 )
      {
        ((void (__fastcall *)(struct IShellLinkW *))a3->lpVtbl->AddRef)(a3);
        a3 = v84;
      }
      v35 = 0;
      v76 = 0;
      if ( !a3 )
      {
        v36 = ppv;
        v37 = *(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        bIgnoreCase = &v84;
        if ( v37(v36, 0, &BHID_SFUIObject, &GUID_000214f9_0000_0000_c000_000000000046) < 0 )
          goto LABEL_57;
        a3 = v84;
      }
      pidl = 0;
      v38.lpVtbl = a3->lpVtbl;
      ppidl[0] = (LPITEMIDLIST)&pidl;
      ppidl[1] = 0;
      LOBYTE(ppidl[2]) = 1;
      Instance = ((__int64 (__fastcall *)(struct IShellLinkW *, LPITEMIDLIST *))v38.lpVtbl->GetIDList)(a3, &ppidl[1]);
      wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
      if ( Instance >= 0 )
      {
        v88 = 0;
        ppidlLast = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
        if ( SHBindToParent(pidl, &GUID_000214e6_0000_0000_c000_000000000046, &v88, &ppidlLast) >= 0 )
        {
          pidl1 = 0;
          ppidl[0] = (LPITEMIDLIST)&pidl1;
          ppidl[1] = 0;
          LOBYTE(ppidl[2]) = 1;
          v39 = (unsigned int)SHGetKnownFolderIDList(&FOLDERID_AppsFolder, 0x4000u, 0, &ppidl[1]) >> 31;
          wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
          if ( (unsigned __int8)v39 != 1 && ILIsParent(pidl1, pidl, 1) )
          {
            v85 = 0;
            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v85, v40, v41, v42);
            if ( SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v85) >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
              v46 = (struct IShellItem2 *)ppv;
              ppv = v85;
              v85 = v46;
            }
            Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v85, v43, v44, v45);
          }
          v47 = (ITEMIDLIST *)pidl1;
          pidl1 = 0;
          if ( v47 )
            CoTaskMemFree(v47);
        }
        if ( v84 )
        {
          v71 = 1;
          if ( (int)CPinnedList::GetAppPathFromShortcut(v84, (struct IShellItem *)ppv, 0x8000u, v89, (int)bIgnoreCase) >= 0 )
          {
            if ( v74 )
            {
              if ( v89[0] != 58 || v89[1] != 58 || v89[2] != 123 || (v49 = 1, !v89[3]) )
                v49 = 0;
              v70 = v49;
              if ( v73 || CPinnedList::_IsLocalHardDisk(v48, v89) || v49 )
              {
                v35 = (ITEMIDLIST *)pidl;
                v76 = pidl;
                pidl = 0;
              }
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88);
      }
      v50 = (ITEMIDLIST *)pidl;
      pidl = 0;
      if ( v50 )
        CoTaskMemFree(v50);
LABEL_57:
      if ( Instance < 0 )
      {
LABEL_115:
        if ( v35 )
          CoTaskMemFree(v35);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        goto LABEL_118;
      }
      if ( !v71
        || (int)CPinnedList::GetAppPathFromShortcut(v84, (struct IShellItem *)ppv, 0x4000u, pszStr1, (int)bIgnoreCase) >= 0 )
      {
        *(_OWORD *)ppidl = *(_OWORD *)L"search-ms:";
        *(LPITEMIDLIST *)((char *)&ppidl[1] + 6) = *(LPITEMIDLIST *)L"ms:";
        v51 = v90;
        if ( v71 )
          v51 = pszStr1;
        if ( !StrCmpNICW(v51, (LPCWSTR)ppidl, 10) )
        {
LABEL_63:
          Instance = -2147467259;
          goto LABEL_115;
        }
      }
      v52 = *(_QWORD *)v86;
      if ( v84 )
        v53 = (*(__int64 (__fastcall **)(struct IApplicationResolver *, struct IShellLinkW *, void *))(v52 + 88))(
                v86,
                v84,
                ppv);
      else
        v53 = (*(__int64 (__fastcall **)(struct IApplicationResolver *, void *))(v52 + 80))(v86, ppv);
      Instance = v53;
      if ( v73 )
      {
        v54 = a4 & 8;
      }
      else
      {
        v54 = a4 & 8;
        if ( !v54 )
          goto LABEL_115;
      }
      if ( v53 < 0 )
      {
        if ( v54 == 8 )
          goto LABEL_115;
        if ( !(unsigned int)SHWindowsPolicy(POLID_NoPinningToDestinations) )
        {
          v56 = v77;
          if ( v35 )
            v56 = v35;
          if ( !v71 || v89[0] )
          {
            v57 = v78;
            if ( v78 )
            {
              if ( (v72 & 0x20000000) == 0 || (v72 & 0x400000) != 0 )
                v58 = CTaskbandPin::_ProcessDestinationFile(v75, v86, v56, v72, a5, a6, v79);
              else
                v58 = CTaskbandPin::_ProcessDestinationFolder(v75, v86, v56, v55, a5, a6);
              Instance = v58;
              if ( v58 >= 0 )
                Instance = SHCreateItemFromIDList(v56, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v57);
            }
            else
            {
              Instance = -2147418113;
            }
          }
          goto LABEL_115;
        }
LABEL_87:
        Instance = -2147024891;
        goto LABEL_115;
      }
      if ( (unsigned int)SHWindowsPolicy(POLID_NoPinningToTaskbar) )
        goto LABEL_87;
      if ( v71 )
      {
        if ( !a5 && !a6 )
          goto LABEL_115;
        if ( ((v72 & 0x40000000) == 0 || CPinnedList::_IsLocalHardDisk(v59, v90))
          && (CPinnedList::_IsLocalHardDisk(v59, v89) || v70) )
        {
          Instance = 0;
          if ( !a5
            || (Instance = (**(__int64 (__fastcall ***)(void *, GUID *, struct IShellItem **))ppv)(
                             ppv,
                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                             a5),
                Instance >= 0) )
          {
            if ( a6 )
            {
              Instance = (*(__int64 (__fastcall **)(struct IApplicationResolver *, struct IShellLinkW *, void *, unsigned __int16 **))(*(_QWORD *)v86 + 32LL))(
                           v86,
                           v84,
                           ppv,
                           a6);
              if ( Instance < 0 )
              {
                if ( a5 )
                  SafeRelease<IShellItemArray>(a5);
              }
            }
          }
          goto LABEL_115;
        }
        goto LABEL_63;
      }
      memset(ppidl, 0, sizeof(ppidl));
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      ppidl[1] = (LPITEMIDLIST)-1LL;
      ppidl[2] = (LPITEMIDLIST)-1LL;
      Instance = IShellItem_GetString((struct IShellItem *)ppv, v60, (unsigned __int16 **)ppidl);
      if ( Instance < 0 )
      {
        Instance = CTaskbandPin::_GetApplication(v61, v86, v90, a5, a6, 0);
        if ( Instance >= 0 )
        {
LABEL_112:
          if ( a5 )
          {
            v67 = (struct IShellItem *)ppv;
            ppv = 0;
            *a5 = v67;
          }
        }
      }
      else
      {
        if ( CompareStringOrdinal(&ppidl[0]->mkid.cb, -1, L"Microsoft.Windows.Cortana_cw5n1h2txyewy!CortanaUI", -1, 1) == 2 )
          goto LABEL_103;
        v62 = (LPITEMIDLIST)&pvData;
        if ( ppidl[0] )
          v62 = ppidl[0];
        if ( CompareStringOrdinal(&v62->mkid.cb, -1, L"Microsoft.WindowsStore_8wekyb3d8bbwe!App", -1, 1) == 2
          && (unsigned int)SHWindowsPolicy(POLID_NoPinningStoreToTaskbar) )
        {
LABEL_103:
          Instance = -2147467259;
        }
        else
        {
          if ( !a6 )
            goto LABEL_112;
          Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&ppv, v63, v64, v65);
          Instance = SHCreateItemInKnownFolder(
                       &FOLDERID_AppsFolder,
                       0x4000u,
                       &ppidl[0]->mkid.cb,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &ppv);
          if ( Instance >= 0 )
          {
            v66 = ppidl[0];
            memset(ppidl, 0, sizeof(ppidl));
            *a6 = &v66->mkid.cb;
            goto LABEL_112;
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      goto LABEL_115;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180678d10  mov     [rsp-8+arg_10], rbx
0x180678d15  push    rbp
0x180678d16  push    rsi
0x180678d17  push    rdi
0x180678d18  push    r12
0x180678d1a  push    r13
0x180678d1c  push    r14
0x180678d1e  push    r15
0x180678d20  lea     rbp, [rsp-610h]
0x180678d28  sub     rsp, 710h
0x180678d2f  mov     rax, cs:__security_cookie
0x180678d36  xor     rax, rsp
0x180678d39  mov     [rbp+640h+var_40], rax
0x180678d40  mov     r13d, r9d
0x180678d43  mov     rbx, r8
0x180678d46  mov     rdi, rdx
0x180678d49  mov     [rsp+740h+var_6E0], rdx
0x180678d4e  mov     [rsp+740h+var_6F0], rcx
0x180678d53  mov     r15, [rbp+640h+arg_20]
0x180678d5a  mov     r12, [rbp+640h+arg_28]
0x180678d61  mov     rcx, [rbp+640h+arg_30]
0x180678d68  mov     [rsp+740h+var_6D0], rcx
0x180678d6d  mov     rax, [rbp+640h+arg_38]
0x180678d74  mov     [rsp+740h+var_6D8], rax
0x180678d79  xor     edx, edx
0x180678d7b  mov     r14d, edx
0x180678d7e  test    rax, rax
0x180678d81  jz      short loc_180678D86
0x180678d83  mov     [rax], rdx
0x180678d86  test    r12, r12
0x180678d89  jz      short loc_180678D8F
0x180678d8b  mov     [r12], rdx
0x180678d8f  test    r15, r15
0x180678d92  jz      short loc_180678D97
0x180678d94  mov     [r15], rdx
0x180678d97  mov     [rcx], rdx
0x180678d9a  mov     esi, r13d
0x180678d9d  and     esi, 4
0x180678da0  mov     [rsp+740h+var_6F8], esi
0x180678da4  mov     eax, 40000000h
0x180678da9  mov     ecx, 60400000h
0x180678dae  cmovnz  eax, ecx
0x180678db1  mov     [rsp+740h+var_6FC], eax
0x180678db5  lea     rax, [rsp+740h+var_6FC]
0x180678dba  mov     qword ptr [rsp+740h+bIgnoreCase], rax; unsigned int *
0x180678dbf  lea     r8, [rbp+640h+var_460]; unsigned __int16 *
0x180678dc6  mov     edx, 0C000h; unsigned int
0x180678dcb  mov     rcx, rdi; pidl
0x180678dce  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x180678dd3  test    eax, eax
0x180678dd5  js      loc_180679588
0x180678ddb  mov     eax, r13d
0x180678dde  and     eax, 2
0x180678de1  mov     [rsp+740h+var_6F4], eax
0x180678de5  jz      short loc_180678E09
0x180678de7  test    esi, esi
0x180678de9  jnz     short loc_180678E09
0x180678deb  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x180678df2  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x180678df7  test    eax, eax
0x180678df9  jnz     short loc_180678E09
0x180678dfb  test    [rsp+740h+var_6FC], 40000000h
0x180678e03  jnz     loc_180679588
0x180678e09  mov     [rbp+640h+ppv], r14
0x180678e0d  lea     rcx, [rbp+640h+ppv]
0x180678e11  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180678e16  lea     r8, [rbp+640h+ppv]; ppv
0x180678e1a  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180678e21  mov     rcx, rdi; pidl
0x180678e24  call    cs:__imp_SHCreateItemFromIDList
0x180678e2a  mov     r14d, eax
0x180678e2d  xor     edi, edi
0x180678e2f  test    eax, eax
0x180678e31  js      loc_180679578
0x180678e37  mov     [rbp+640h+var_690], rdi
0x180678e3b  lea     rdx, [rbp+640h+var_690]
0x180678e3f  lea     rcx, [rbp+640h+ppv]
0x180678e43  call    ??$As@UIShellItem2@@@?$ComPtr@UIShellItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIShellItem2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellItem>::As<IShellItem2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellItem2>>)
0x180678e48  test    eax, eax
0x180678e4a  js      loc_180678EE0
0x180678e50  xorps   xmm0, xmm0
0x180678e53  movups  xmmword ptr [rbp+640h+ppidl], xmm0
0x180678e57  mov     [rbp+640h+ppidl], rdi
0x180678e5b  mov     [rbp+640h+ppidl+8], rdi
0x180678e5f  mov     [rbp+640h+var_6A0], rdi
0x180678e63  mov     rsi, [rbp+640h+var_690]
0x180678e67  mov     rax, [rsi]
0x180678e6a  mov     rdi, [rax+88h]
0x180678e71  lea     rcx, [rbp+640h+ppidl]
0x180678e75  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180678e7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180678e7e  mov     [rbp+640h+ppidl+8], rax
0x180678e82  mov     [rbp+640h+var_6A0], rax
0x180678e86  lea     r8, [rbp+640h+ppidl]
0x180678e8a  lea     rdx, PKEY_AppUserModel_ParentID
0x180678e91  mov     rcx, rsi
0x180678e94  mov     rax, rdi
0x180678e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678e9c  xor     edi, edi
0x180678e9e  test    eax, eax
0x180678ea0  js      short loc_180678EB8
0x180678ea2  lea     rcx, [rbp+640h+ppidl]
0x180678ea6  call    ?HasLength@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::HasLength(void)
0x180678eab  test    al, al
0x180678ead  mov     esi, 80004005h
0x180678eb2  cmovnz  r14d, esi
0x180678eb6  jmp     short loc_180678EBD
0x180678eb8  mov     esi, 80004005h
0x180678ebd  test    r13b, 10h
0x180678ec1  jnz     short loc_180678ED2
0x180678ec3  mov     rdx, [rbp+640h+var_690]; struct IShellItem2 *
0x180678ec7  call    ?IsPinnable@CTaskbandPin@@AEAA_NPEAUIShellItem2@@@Z; CTaskbandPin::IsPinnable(IShellItem2 *)
0x180678ecc  test    al, al
0x180678ece  cmovz   r14d, esi
0x180678ed2  lea     rcx, [rbp+640h+ppidl]
0x180678ed6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180678edb  test    r14d, r14d
0x180678ede  js      short loc_180678F18
0x180678ee0  mov     [rbp+640h+pidl], rdi
0x180678ee4  lea     rcx, [rbp+640h+pidl]
0x180678ee8  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180678eed  lea     rdx, [rbp+640h+pidl]; struct IShellItem *
0x180678ef1  mov     rcx, [rbp+640h+ppv]; this
0x180678ef5  call    ?GetTaskbarPinnableItem@TaskbarPinHelper@@YAJPEAUIShellItem@@PEAPEAU2@@Z; TaskbarPinHelper::GetTaskbarPinnableItem(IShellItem *,IShellItem * *)
0x180678efa  test    eax, eax
0x180678efc  js      short loc_180678F0E
0x180678efe  mov     rcx, [rbp+640h+ppv]
0x180678f02  mov     rax, [rbp+640h+pidl]
0x180678f06  mov     [rbp+640h+ppv], rax
0x180678f0a  mov     [rbp+640h+pidl], rcx
0x180678f0e  lea     rcx, [rbp+640h+pidl]
0x180678f12  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180678f17  nop
0x180678f18  lea     rcx, [rbp+640h+var_690]
0x180678f1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180678f21  test    r14d, r14d
0x180678f24  js      loc_180679578
0x180678f2a  mov     [rbp+640h+var_688], rdi
0x180678f2e  lea     rcx, [rbp+640h+var_688]
0x180678f32  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180678f37  lea     rax, [rbp+640h+var_688]
0x180678f3b  mov     qword ptr [rsp+740h+bIgnoreCase], rax; ppv
0x180678f40  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x180678f47  xor     edx, edx; pUnkOuter
0x180678f49  lea     r8d, [rdx+3]; dwClsContext
0x180678f4d  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x180678f54  call    cs:__imp_CoCreateInstance
0x180678f5a  mov     r14d, eax
0x180678f5d  test    eax, eax
0x180678f5f  js      loc_18067956E
0x180678f65  mov     [rsp+740h+var_6FF], dil
0x180678f6a  mov     [rsp+740h+var_700], dil
0x180678f6f  xor     edx, edx; Val
0x180678f71  mov     r8d, 208h; Size
0x180678f77  lea     rcx, [rbp+640h+var_670]; void *
0x180678f7b  call    memset_0
0x180678f80  mov     [rbp+640h+var_698], rbx
0x180678f84  test    rbx, rbx
0x180678f87  jz      short loc_180678F9C
0x180678f89  mov     rax, [rbx]
0x180678f8c  mov     rcx, rbx
0x180678f8f  mov     rax, [rax+8]
0x180678f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678f98  mov     rbx, [rbp+640h+var_698]
0x180678f9c  mov     rsi, rdi
0x180678f9f  mov     [rsp+740h+var_6E8], rdi
0x180678fa4  test    rbx, rbx
0x180678fa7  jnz     short loc_180678FEF
0x180678fa9  mov     rdi, [rbp+640h+ppv]
0x180678fad  mov     rax, [rdi]
0x180678fb0  mov     rbx, [rax+18h]
0x180678fb4  lea     rcx, [rbp+640h+var_698]
0x180678fb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180678fbd  lea     rax, [rbp+640h+var_698]
0x180678fc1  mov     qword ptr [rsp+740h+bIgnoreCase], rax; int
0x180678fc6  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180678fcd  lea     r8, BHID_SFUIObject
0x180678fd4  xor     edx, edx
0x180678fd6  mov     rcx, rdi
0x180678fd9  mov     rax, rbx
0x180678fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180678fe1  xor     edi, edi
0x180678fe3  test    eax, eax
0x180678fe5  js      loc_1806791A2
0x180678feb  mov     rbx, [rbp+640h+var_698]
0x180678fef  mov     [rbp+640h+pidl], rdi
0x180678ff3  mov     rax, [rbx]
0x180678ff6  lea     rcx, [rbp+640h+pidl]
0x180678ffa  mov     [rbp+640h+ppidl], rcx
0x180678ffe  mov     [rbp+640h+ppidl+8], rdi
0x180679002  mov     byte ptr [rbp+640h+var_6A0], 1
0x180679006  lea     rdx, [rbp+640h+ppidl+8]
0x18067900a  mov     rcx, rbx
0x18067900d  mov     rax, [rax+20h]
0x180679011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180679016  mov     r14d, eax
0x180679019  lea     rcx, [rbp+640h+ppidl]
0x18067901d  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180679022  test    r14d, r14d
0x180679025  js      loc_18067918F
0x18067902b  mov     [rbp+640h+var_678], rdi
0x18067902f  mov     [rsp+740h+ppidlLast], rdi
0x180679034  lea     rcx, [rbp+640h+var_678]
0x180679038  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067903d  lea     r9, [rsp+740h+ppidlLast]; ppidlLast
0x180679042  lea     r8, [rbp+640h+var_678]; ppv
0x180679046  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18067904d  mov     rcx, [rbp+640h+pidl]; pidl
0x180679051  call    cs:__imp_SHBindToParent
0x180679057  test    eax, eax
0x180679059  js      loc_180679112
0x18067905f  mov     [rbp+640h+pidl1], rdi
0x180679063  lea     rax, [rbp+640h+pidl1]
0x180679067  mov     [rbp+640h+ppidl], rax
0x18067906b  mov     [rbp+640h+ppidl+8], rdi
0x18067906f  mov     byte ptr [rbp+640h+var_6A0], 1
0x180679073  lea     r9, [rbp+640h+ppidl+8]; ppidl
0x180679077  xor     r8d, r8d; hToken
0x18067907a  mov     edx, 4000h; dwFlags
0x18067907f  lea     rcx, FOLDERID_AppsFolder; rfid
0x180679086  call    cs:__imp_SHGetKnownFolderIDList
0x18067908c  mov     ebx, eax
0x18067908e  shr     ebx, 1Fh
0x180679091  lea     rcx, [rbp+640h+ppidl]
0x180679095  call    ??1?$out_param_ptr_t@PEAPEAUGMRelatedProcess@KnownGameList@@V?$unique_ptr@$$BY0A@UGMRelatedProcess@KnownGameList@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<KnownGameList::GMRelatedProcess * *,wistd::unique_ptr<KnownGameList::GMRelatedProcess [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18067909a  xor     bl, 1
0x18067909d  jz      short loc_1806790FF
0x18067909f  mov     r8d, 1; fImmediate
0x1806790a5  mov     rdx, [rbp+640h+pidl]; pidl2
0x1806790a9  mov     rcx, [rbp+640h+pidl1]; pidl1
0x1806790ad  call    cs:__imp_ILIsParent
0x1806790b3  test    eax, eax
0x1806790b5  jz      short loc_1806790FF
0x1806790b7  mov     [rbp+640h+var_690], rdi
0x1806790bb  lea     rcx, [rbp+640h+var_690]
0x1806790bf  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1806790c4  lea     r8, [rbp+640h+var_690]; ppv
0x1806790c8  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1806790cf  mov     rcx, [rbp+640h+pidl]; pidl
0x1806790d3  call    cs:__imp_SHCreateItemFromIDList
0x1806790d9  test    eax, eax
0x1806790db  js      short loc_1806790F6
0x1806790dd  lea     rcx, [rbp+640h+var_698]
0x1806790e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1806790e6  mov     rcx, [rbp+640h+ppv]
0x1806790ea  mov     rax, [rbp+640h+var_690]
0x1806790ee  mov     [rbp+640h+ppv], rax
0x1806790f2  mov     [rbp+640h+var_690], rcx
0x1806790f6  lea     rcx, [rbp+640h+var_690]
0x1806790fa  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x1806790ff  mov     rcx, [rbp+640h+pidl1]; pv
0x180679103  mov     [rbp+640h+pidl1], rdi
0x180679107  test    rcx, rcx
0x18067910a  jz      short loc_180679112
0x18067910c  call    cs:__imp_CoTaskMemFree
0x180679112  mov     rcx, [rbp+640h+var_698]; struct IShellLinkW *
0x180679116  test    rcx, rcx
0x180679119  jz      short loc_180679185
0x18067911b  mov     [rsp+740h+var_6FF], 1
0x180679120  lea     r9, [rbp+640h+var_670]; unsigned __int16 *
0x180679124  mov     r8d, 8000h; unsigned int
0x18067912a  mov     rdx, [rbp+640h+ppv]; struct IShellItem *
0x18067912e  call    ?GetAppPathFromShortcut@CPinnedList@@SAJPEAUIShellLinkW@@PEAUIShellItem@@KPEAGH@Z; CPinnedList::GetAppPathFromShortcut(IShellLinkW *,IShellItem *,ulong,ushort *,int)
0x180679133  test    eax, eax
0x180679135  js      short loc_180679185
0x180679137  cmp     [rsp+740h+var_6F4], edi
0x18067913b  jz      short loc_180679185
0x18067913d  cmp     [rbp+640h+var_670], 3Ah ; ':'
0x180679142  jnz     short loc_18067915A
0x180679144  cmp     [rbp+640h+var_66E], 3Ah ; ':'
0x180679149  jnz     short loc_18067915A
0x18067914b  cmp     [rbp+640h+var_66C], 7Bh ; '{'
0x180679150  jnz     short loc_18067915A
0x180679152  cmp     [rbp+640h+var_66A], di
0x180679156  mov     bl, 1
0x180679158  jnz     short loc_18067915D
0x18067915a  mov     bl, dil
0x18067915d  mov     [rsp+740h+var_700], bl
0x180679161  cmp     [rsp+740h+var_6F8], edi
0x180679165  jnz     short loc_180679178
0x180679167  lea     rdx, [rbp+640h+var_670]; unsigned __int16 *
0x18067916b  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x180679170  test    eax, eax
0x180679172  jnz     short loc_180679178
0x180679174  test    bl, bl
0x180679176  jz      short loc_180679185
0x180679178  mov     rsi, [rbp+640h+pidl]
0x18067917c  mov     [rsp+740h+var_6E8], rsi
0x180679181  mov     [rbp+640h+pidl], rdi
0x180679185  lea     rcx, [rbp+640h+var_678]
0x180679189  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18067918e  nop
0x18067918f  mov     rcx, [rbp+640h+pidl]; pv
0x180679193  mov     [rbp+640h+pidl], rdi
0x180679197  test    rcx, rcx
0x18067919a  jz      short loc_1806791A2
0x18067919c  call    cs:__imp_CoTaskMemFree
0x1806791a2  test    r14d, r14d
0x1806791a5  js      loc_180679555
0x1806791ab  mov     dil, [rsp+740h+var_6FF]
  ... truncated ...
```
