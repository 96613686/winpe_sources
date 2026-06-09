# CTaskbandPin::v_IsAcceptableTarget(_ITEMIDLIST_ABSOLUTE const *,IShellLinkW *,PINNABLEFLAG,IShellItem * *,ushort * *,ushort * *,IShellItem * *)

- ea: `0x1801993b0`
- end: `0x180199c93`
- name: `?v_IsAcceptableTarget@CTaskbandPin@@MEAAHPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellLinkW@@W4PINNABLEFLAG@@PEAPEAUIShellItem@@PEAPEAG43@Z`
- size: `2275`
- prototype: `int __high(const struct _ITEMIDLIST_ABSOLUTE *, struct IShellLinkW *, enum PINNABLEFLAG, struct IShellItem **, unsigned __int16 **, unsigned __int16 **, struct IShellItem **)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f05c`
- `0x18000f5a4`
- `0x18001dc64`
- `0x180047d00`
- `0x180048930`
- `0x1800ff4dc`
- `0x1800ffb30`
- `0x1801526a8`
- `0x180157d88`
- `0x18015d674`
- `0x180175f68`
- `0x1801993b0`
- `0x180233280`
- `0x1802342fc`
- `0x1802acb9c`
- `0x1803bc290`
- `0x1803bc4a4`
- `0x1803bc7a0`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180199b4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180199b86`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180199b4e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180199b86`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801998e7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801998e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019961b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019961b`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18019995d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180199a21`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180199b98`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18019995d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180199a21`
- `SHCORE!__imp_SHWindowsPolicy` at `0x180199b98`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180199751`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x180199751`
- `Windows.Storage!ILIsParent` at `0x180199779`
- `Windows.Storage!ILIsParent` at `0x180199779`
- `Windows.Storage!SHCreateItemInKnownFolder` at `0x180199bd2`
- `Windows.Storage!SHCreateItemInKnownFolder` at `0x180199bd2`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801994cd`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801997a1`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180199a0c`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801994cd`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801997a1`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180199a0c`
- `Windows.Storage!SHBindToParent` at `0x18019971c`
- `Windows.Storage!SHBindToParent` at `0x18019971c`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
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
  CPinnedList *v13; // rcx
  HRESULT Instance; // r14d
  void *v15; // rbx
  int (__fastcall *v16)(void *, GUID *, struct IShellItem2 **); // rsi
  struct IShellItem2 *v17; // rsi
  HRESULT (__stdcall *GetString)(IShellItem2 *, const PROPERTYKEY *const, LPWSTR *); // rbx
  CTaskbandPin *v19; // rcx
  struct IShellItem **v20; // r8
  const ITEMIDLIST *v21; // rcx
  LPCITEMIDLIST v22; // rbx
  void *v23; // rsi
  int (__fastcall *v24)(void *, _QWORD, const GUID *, GUID *, struct IShellLinkW **); // rdi
  struct IShellLinkW v25; // rax
  char v26; // di
  unsigned int v27; // edi
  void *v28; // rcx
  CPinnedList *v29; // rcx
  unsigned __int16 *v30; // rcx
  struct IShellItem2Vtbl *lpVtbl; // rax
  int v32; // eax
  int v33; // r13d
  unsigned int v34; // r9d
  const struct _ITEMIDLIST_ABSOLUTE *v35; // rdi
  void **v36; // rbx
  int v37; // eax
  CPinnedList *v38; // rcx
  CTaskbandPin *v39; // rcx
  LPITEMIDLIST v40; // rcx
  LPITEMIDLIST v41; // rax
  struct IShellItem *v42; // rax
  char v44; // [rsp+40h] [rbp-C0h]
  char v45; // [rsp+41h] [rbp-BFh]
  unsigned int v46; // [rsp+44h] [rbp-BCh] BYREF
  int v47; // [rsp+48h] [rbp-B8h]
  int v48; // [rsp+4Ch] [rbp-B4h]
  CTaskbandPin *v49; // [rsp+50h] [rbp-B0h]
  const ITEMIDLIST *v50; // [rsp+58h] [rbp-A8h]
  void **v51; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v52; // [rsp+68h] [rbp-98h]
  LPCITEMIDLIST ppidlLast; // [rsp+70h] [rbp-90h] BYREF
  void *ppv; // [rsp+78h] [rbp-88h] BYREF
  struct IShellItem2 *v55; // [rsp+80h] [rbp-80h] BYREF
  LPCITEMIDLIST pidl; // [rsp+88h] [rbp-78h] BYREF
  LPITEMIDLIST ppidl[3]; // [rsp+90h] [rbp-70h] BYREF
  struct IShellLinkW *v58; // [rsp+A8h] [rbp-58h] BYREF
  void *v59; // [rsp+B0h] [rbp-50h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+B8h] [rbp-48h] BYREF
  void *v61; // [rsp+C0h] [rbp-40h] BYREF
  LPCITEMIDLIST v62; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v63[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v64[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR pszStr1[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v50 = a2;
  v49 = a1;
  v52 = a7;
  v51 = a8;
  v11 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a5 )
    *a5 = 0;
  *a7 = 0;
  v47 = a4 & 4;
  v12 = 0x40000000;
  if ( (a4 & 4) != 0 )
    v12 = 1614807040;
  v46 = v12;
  if ( (int)SHGetNameAndFlagsW(a2, 0xC000u, v64, 0x104u, &v46) >= 0 )
  {
    v48 = a4 & 2;
    if ( (a4 & 2) == 0 || (a4 & 4) != 0 || CPinnedList::_IsLocalHardDisk(v13, v64) || (v46 & 0x40000000) == 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      Instance = SHCreateItemFromIDList(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( Instance < 0 )
        goto LABEL_116;
      v55 = 0;
      v15 = ppv;
      v16 = **(int (__fastcall ***)(void *, GUID *, struct IShellItem2 **))ppv;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      if ( v16(v15, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v55) < 0 )
        goto LABEL_23;
      memset(ppidl, 0, sizeof(ppidl));
      v17 = v55;
      GetString = v55->lpVtbl->GetString;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      ppidl[1] = (LPITEMIDLIST)-1LL;
      ppidl[2] = (LPITEMIDLIST)-1LL;
      if ( ((int (__fastcall *)(struct IShellItem2 *, void *, LPITEMIDLIST *))GetString)(
             v17,
             &PKEY_AppUserModel_ParentID,
             ppidl) >= 0
        && (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::HasLength(ppidl) )
      {
        Instance = -2147467259;
      }
      if ( (a4 & 0x10) == 0 && !CTaskbandPin::IsPinnable(v19, v55) )
        Instance = -2147467259;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      if ( Instance >= 0 )
      {
LABEL_23:
        pidl = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pidl);
        if ( TaskbarPinHelper::GetTaskbarPinnableItem((TaskbarPinHelper *)ppv, (struct IShellItem *)&pidl, v20) >= 0 )
        {
          v21 = (const ITEMIDLIST *)ppv;
          ppv = (void *)pidl;
          pidl = v21;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pidl);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      if ( Instance < 0 )
        goto LABEL_116;
      v55 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
      Instance = CoCreateInstance(
                   &CLSID_StartMenuCacheAndAppResolver,
                   0,
                   3u,
                   &GUID_de25675a_72de_44b4_9373_05170450c140,
                   (LPVOID *)&v55);
      if ( Instance < 0 )
      {
LABEL_115:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v55);
LABEL_116:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
        return Instance >= 0;
      }
      v45 = 0;
      v44 = 0;
      memset_0(v63, 0, 0x208u);
      v58 = a3;
      if ( a3 )
      {
        ((void (__fastcall *)(struct IShellLinkW *))a3->lpVtbl->AddRef)(a3);
        a3 = v58;
      }
      v22 = 0;
      v62 = 0;
      if ( !a3 )
      {
        v23 = ppv;
        v24 = *(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *, struct IShellLinkW **))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        if ( v24(v23, 0, &BHID_SFUIObject, &GUID_000214f9_0000_0000_c000_000000000046, &v58) < 0 )
          goto LABEL_56;
        a3 = v58;
      }
      pidl = 0;
      v25.lpVtbl = a3->lpVtbl;
      ppidl[0] = (LPITEMIDLIST)&pidl;
      ppidl[1] = 0;
      LOBYTE(ppidl[2]) = 1;
      Instance = ((__int64 (__fastcall *)(struct IShellLinkW *, LPITEMIDLIST *))v25.lpVtbl->GetIDList)(a3, &ppidl[1]);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
      v26 = 0;
      if ( Instance >= 0 )
      {
        v61 = 0;
        ppidlLast = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
        if ( SHBindToParent(pidl, &GUID_000214e6_0000_0000_c000_000000000046, &v61, &ppidlLast) >= 0 )
        {
          pidl1 = 0;
          ppidl[0] = (LPITEMIDLIST)&pidl1;
          ppidl[1] = 0;
          LOBYTE(ppidl[2]) = 1;
          v27 = (unsigned int)SHGetKnownFolderIDList(&FOLDERID_AppsFolder, 0x4000u, 0, &ppidl[1]) >> 31;
          wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
          if ( (unsigned __int8)v27 != 1 )
          {
            v26 = 0;
            if ( ILIsParent(pidl1, pidl, 1) )
            {
              v59 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
              if ( SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v59) >= 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
                v28 = ppv;
                ppv = v59;
                v59 = v28;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
            }
          }
          else
          {
            v26 = 0;
          }
          wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            &pidl1,
            0);
        }
        if ( v58 )
        {
          v45 = 1;
          if ( (int)GetAppPathFromShortcut(v58, (struct IShellItem *)ppv, 0x8000u, v63, 260) >= 0 )
          {
            if ( v48 )
            {
              if ( v63[0] == 58 && v63[1] == 58 && v63[2] == 123 && v63[3] )
                v26 = 1;
              v44 = v26;
              if ( v47 || CPinnedList::_IsLocalHardDisk(v29, v63) || v26 )
              {
                v22 = pidl;
                v62 = pidl;
                pidl = 0;
              }
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
      }
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pidl,
        0);
LABEL_56:
      if ( Instance < 0 )
      {
LABEL_114:
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v62,
          0);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        goto LABEL_115;
      }
      if ( !v45 || (int)GetAppPathFromShortcut(v58, (struct IShellItem *)ppv, 0x4000u, pszStr1, 260) >= 0 )
      {
        *(_OWORD *)ppidl = *(_OWORD *)L"search-ms:";
        *(LPITEMIDLIST *)((char *)&ppidl[1] + 6) = *(LPITEMIDLIST *)L"ms:";
        v30 = v64;
        if ( v45 )
          v30 = pszStr1;
        if ( !StrCmpNICW(v30, (LPCWSTR)ppidl, 10) )
        {
LABEL_62:
          Instance = -2147467259;
          goto LABEL_114;
        }
      }
      lpVtbl = v55->lpVtbl;
      if ( v58 )
        v32 = ((__int64 (__fastcall *)(struct IShellItem2 *, struct IShellLinkW *, void *))lpVtbl->GetPropertyDescriptionList)(
                v55,
                v58,
                ppv);
      else
        v32 = ((__int64 (__fastcall *)(struct IShellItem2 *, void *))lpVtbl->GetPropertyStoreForKeys)(v55, ppv);
      Instance = v32;
      if ( v47 )
      {
        v33 = a4 & 8;
      }
      else
      {
        v33 = a4 & 8;
        if ( !v33 )
          goto LABEL_114;
      }
      if ( v32 < 0 )
      {
        if ( v33 == 8 )
          goto LABEL_114;
        if ( !(unsigned int)SHWindowsPolicy(&POLID_NoPinningToDestinations) )
        {
          v35 = (const struct _ITEMIDLIST_ABSOLUTE *)v50;
          if ( v22 )
            v35 = (const struct _ITEMIDLIST_ABSOLUTE *)v22;
          if ( !v45 || v63[0] )
          {
            v36 = v51;
            if ( v51 )
            {
              if ( (v46 & 0x20000000) == 0 || (v46 & 0x400000) != 0 )
                v37 = CTaskbandPin::_ProcessDestinationFile(
                        v49,
                        (struct IApplicationResolver *)v55,
                        v35,
                        v46,
                        a5,
                        a6,
                        v52);
              else
                v37 = CTaskbandPin::_ProcessDestinationFolder(v49, (struct IApplicationResolver *)v55, v35, v34, a5, a6);
              Instance = v37;
              if ( v37 >= 0 )
                Instance = SHCreateItemFromIDList((LPCITEMIDLIST)v35, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v36);
            }
            else
            {
              Instance = -2147418113;
            }
          }
          goto LABEL_114;
        }
LABEL_86:
        Instance = -2147024891;
        goto LABEL_114;
      }
      if ( (unsigned int)SHWindowsPolicy(&POLID_NoPinningToTaskbar) )
        goto LABEL_86;
      if ( v45 )
      {
        if ( !a5 && !a6 )
          goto LABEL_114;
        if ( ((v46 & 0x40000000) == 0 || CPinnedList::_IsLocalHardDisk(v38, v64))
          && (CPinnedList::_IsLocalHardDisk(v38, v63) || v44) )
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
              Instance = ((__int64 (__fastcall *)(struct IShellItem2 *, struct IShellLinkW *, void *, unsigned __int16 **))v55->lpVtbl->GetParent)(
                           v55,
                           v58,
                           ppv,
                           a6);
              if ( Instance < 0 )
              {
                if ( a5 )
                  SafeRelease<IUpdatableItemSet>(a5);
              }
            }
          }
          goto LABEL_114;
        }
        goto LABEL_62;
      }
      memset(ppidl, 0, sizeof(ppidl));
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      ppidl[1] = (LPITEMIDLIST)-1LL;
      ppidl[2] = (LPITEMIDLIST)-1LL;
      Instance = IShellItem_GetString((struct IShellItem *)ppv, &PKEY_AppUserModel_ID, (unsigned __int16 **)ppidl);
      if ( Instance < 0 )
      {
        Instance = CTaskbandPin::_GetApplication(v39, (struct IApplicationResolver *)v55, v64, a5, a6, 0);
        if ( Instance >= 0 )
        {
LABEL_111:
          if ( a5 )
          {
            v42 = (struct IShellItem *)ppv;
            ppv = 0;
            *a5 = v42;
          }
        }
      }
      else
      {
        if ( CompareStringOrdinal(&ppidl[0]->mkid.cb, -1, L"Microsoft.Windows.Cortana_cw5n1h2txyewy!CortanaUI", -1, 1) == 2 )
          goto LABEL_102;
        v40 = (LPITEMIDLIST)&pszStart;
        if ( ppidl[0] )
          v40 = ppidl[0];
        if ( CompareStringOrdinal(&v40->mkid.cb, -1, L"Microsoft.WindowsStore_8wekyb3d8bbwe!App", -1, 1) == 2
          && (unsigned int)SHWindowsPolicy(&POLID_NoPinningStoreToTaskbar) )
        {
LABEL_102:
          Instance = -2147467259;
        }
        else
        {
          if ( !a6 )
            goto LABEL_111;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          Instance = SHCreateItemInKnownFolder(
                       &FOLDERID_AppsFolder,
                       0x4000u,
                       &ppidl[0]->mkid.cb,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &ppv);
          if ( Instance >= 0 )
          {
            v41 = ppidl[0];
            memset(ppidl, 0, sizeof(ppidl));
            *a6 = &v41->mkid.cb;
            goto LABEL_111;
          }
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
      goto LABEL_114;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1801993b0  mov     [rsp-8+arg_10], rbx
0x1801993b5  push    rbp
0x1801993b6  push    rsi
0x1801993b7  push    rdi
0x1801993b8  push    r12
0x1801993ba  push    r13
0x1801993bc  push    r14
0x1801993be  push    r15
0x1801993c0  lea     rbp, [rsp-610h]
0x1801993c8  sub     rsp, 710h
0x1801993cf  mov     rax, cs:__security_cookie
0x1801993d6  xor     rax, rsp
0x1801993d9  mov     [rbp+640h+var_40], rax
0x1801993e0  mov     r13d, r9d
0x1801993e3  mov     rdi, r8
0x1801993e6  mov     rbx, rdx
0x1801993e9  mov     [rsp+740h+var_6E8], rdx
0x1801993ee  mov     [rsp+740h+var_6F0], rcx
0x1801993f3  mov     r15, [rbp+640h+arg_20]
0x1801993fa  mov     r12, [rbp+640h+arg_28]
0x180199401  mov     rcx, [rbp+640h+arg_30]
0x180199408  mov     [rsp+740h+var_6D8], rcx
0x18019940d  mov     rax, [rbp+640h+arg_38]
0x180199414  mov     [rsp+740h+var_6E0], rax
0x180199419  xor     edx, edx
0x18019941b  mov     r14d, edx
0x18019941e  test    rax, rax
0x180199421  jz      short loc_180199426
0x180199423  mov     [rax], rdx
0x180199426  test    r12, r12
0x180199429  jz      short loc_18019942F
0x18019942b  mov     [r12], rdx
0x18019942f  test    r15, r15
0x180199432  jz      short loc_180199437
0x180199434  mov     [r15], rdx
0x180199437  mov     [rcx], rdx
0x18019943a  mov     esi, r13d
0x18019943d  and     esi, 4
0x180199440  mov     [rsp+740h+var_6F8], esi
0x180199444  mov     eax, 40000000h
0x180199449  mov     ecx, 60400000h
0x18019944e  cmovnz  eax, ecx
0x180199451  mov     [rsp+740h+var_6FC], eax
0x180199455  lea     rax, [rsp+740h+var_6FC]
0x18019945a  mov     qword ptr [rsp+740h+bIgnoreCase], rax; unsigned int *
0x18019945f  mov     r9d, 104h; unsigned int
0x180199465  lea     r8, [rbp+640h+var_460]; unsigned __int16 *
0x18019946c  mov     edx, 0C000h; unsigned int
0x180199471  mov     rcx, rbx; pidl
0x180199474  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x180199479  test    eax, eax
0x18019947b  js      loc_180199C66
0x180199481  mov     eax, r13d
0x180199484  and     eax, 2
0x180199487  mov     [rsp+740h+var_6F4], eax
0x18019948b  jz      short loc_1801994AF
0x18019948d  test    esi, esi
0x18019948f  jnz     short loc_1801994AF
0x180199491  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x180199498  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x18019949d  test    eax, eax
0x18019949f  jnz     short loc_1801994AF
0x1801994a1  test    [rsp+740h+var_6FC], 40000000h
0x1801994a9  jnz     loc_180199C66
0x1801994af  mov     [rsp+740h+ppv], r14
0x1801994b4  lea     rcx, [rsp+740h+ppv]
0x1801994b9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801994be  lea     r8, [rsp+740h+ppv]; ppv
0x1801994c3  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1801994ca  mov     rcx, rbx; pidl
0x1801994cd  call    cs:__imp_SHCreateItemFromIDList
0x1801994d3  mov     r14d, eax
0x1801994d6  test    eax, eax
0x1801994d8  js      loc_180199C55
0x1801994de  mov     [rbp+640h+var_6C0], 0
0x1801994e6  mov     rbx, [rsp+740h+ppv]
0x1801994eb  mov     rax, [rbx]
0x1801994ee  mov     rsi, [rax]
0x1801994f1  lea     rcx, [rbp+640h+var_6C0]
0x1801994f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801994fa  lea     r8, [rbp+640h+var_6C0]
0x1801994fe  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180199505  mov     rcx, rbx
0x180199508  mov     rax, rsi
0x18019950b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199510  nop
0x180199511  xor     esi, esi
0x180199513  test    eax, eax
0x180199515  js      loc_1801995A4
0x18019951b  mov     [rbp+640h+ppidl], rsi
0x18019951f  mov     [rbp+640h+ppidl+8], rsi
0x180199523  mov     [rbp+640h+var_6A0], rsi
0x180199527  mov     rsi, [rbp+640h+var_6C0]
0x18019952b  mov     rax, [rsi]
0x18019952e  mov     rbx, [rax+88h]
0x180199535  lea     rcx, [rbp+640h+ppidl]; void *
0x180199539  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18019953e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180199542  mov     [rbp+640h+ppidl+8], rax
0x180199546  mov     [rbp+640h+var_6A0], rax
0x18019954a  lea     r8, [rbp+640h+ppidl]
0x18019954e  lea     rdx, PKEY_AppUserModel_ParentID
0x180199555  mov     rcx, rsi
0x180199558  mov     rax, rbx
0x18019955b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199560  xor     esi, esi
0x180199562  test    eax, eax
0x180199564  js      short loc_18019957C
0x180199566  lea     rcx, [rbp+640h+ppidl]
0x18019956a  call    ?HasLength@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::HasLength(void)
0x18019956f  test    al, al
0x180199571  mov     ebx, 80004005h
0x180199576  cmovnz  r14d, ebx
0x18019957a  jmp     short loc_180199581
0x18019957c  mov     ebx, 80004005h
0x180199581  test    r13b, 10h
0x180199585  jnz     short loc_180199596
0x180199587  mov     rdx, [rbp+640h+var_6C0]; struct IShellItem2 *
0x18019958b  call    ?IsPinnable@CTaskbandPin@@AEAA_NPEAUIShellItem2@@@Z; CTaskbandPin::IsPinnable(IShellItem2 *)
0x180199590  test    al, al
0x180199592  cmovz   r14d, ebx
0x180199596  lea     rcx, [rbp+640h+ppidl]; void *
0x18019959a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18019959f  test    r14d, r14d
0x1801995a2  js      short loc_1801995DF
0x1801995a4  mov     [rbp+640h+pidl], rsi
0x1801995a8  lea     rcx, [rbp+640h+pidl]
0x1801995ac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801995b1  lea     rdx, [rbp+640h+pidl]; struct IShellItem *
0x1801995b5  mov     rcx, [rsp+740h+ppv]; this
0x1801995ba  call    ?GetTaskbarPinnableItem@TaskbarPinHelper@@YAJPEAUIShellItem@@PEAPEAU2@@Z; TaskbarPinHelper::GetTaskbarPinnableItem(IShellItem *,IShellItem * *)
0x1801995bf  test    eax, eax
0x1801995c1  js      short loc_1801995D5
0x1801995c3  mov     rcx, [rsp+740h+ppv]
0x1801995c8  mov     rax, [rbp+640h+pidl]
0x1801995cc  mov     [rsp+740h+ppv], rax
0x1801995d1  mov     [rbp+640h+pidl], rcx
0x1801995d5  lea     rcx, [rbp+640h+pidl]
0x1801995d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801995de  nop
0x1801995df  lea     rcx, [rbp+640h+var_6C0]
0x1801995e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801995e8  test    r14d, r14d
0x1801995eb  js      loc_180199C55
0x1801995f1  mov     [rbp+640h+var_6C0], rsi
0x1801995f5  lea     rcx, [rbp+640h+var_6C0]
0x1801995f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801995fe  lea     rax, [rbp+640h+var_6C0]
0x180199602  mov     qword ptr [rsp+740h+bIgnoreCase], rax; ppv
0x180199607  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x18019960e  xor     edx, edx; pUnkOuter
0x180199610  lea     r8d, [rdx+3]; dwClsContext
0x180199614  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x18019961b  call    cs:__imp_CoCreateInstance
0x180199621  mov     r14d, eax
0x180199624  test    eax, eax
0x180199626  js      loc_180199C4B
0x18019962c  mov     [rsp+740h+var_6FF], sil
0x180199631  mov     [rsp+740h+var_700], sil
0x180199636  xor     edx, edx; Val
0x180199638  mov     r8d, 208h; Size
0x18019963e  lea     rcx, [rbp+640h+var_670]; void *
0x180199642  call    memset_0
0x180199647  mov     [rbp+640h+var_698], rdi
0x18019964b  test    rdi, rdi
0x18019964e  jz      short loc_180199663
0x180199650  mov     rax, [rdi]
0x180199653  mov     rcx, rdi
0x180199656  mov     rax, [rax+8]
0x18019965a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019965f  mov     rdi, [rbp+640h+var_698]
0x180199663  mov     rbx, rsi
0x180199666  mov     [rbp+640h+var_678], rbx
0x18019966a  test    rdi, rdi
0x18019966d  jnz     short loc_1801996B8
0x18019966f  mov     rsi, [rsp+740h+ppv]
0x180199674  mov     rax, [rsi]
0x180199677  mov     rdi, [rax+18h]
0x18019967b  lea     rcx, [rbp+640h+var_698]
0x18019967f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199684  lea     rax, [rbp+640h+var_698]
0x180199688  mov     qword ptr [rsp+740h+bIgnoreCase], rax
0x18019968d  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180199694  lea     r8, BHID_SFUIObject
0x18019969b  xor     edx, edx
0x18019969d  mov     rcx, rsi
0x1801996a0  mov     rax, rdi
0x1801996a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801996a8  xor     edi, edi
0x1801996aa  test    eax, eax
0x1801996ac  js      loc_180199876
0x1801996b2  mov     rdi, [rbp+640h+var_698]
0x1801996b6  xor     esi, esi
0x1801996b8  mov     [rbp+640h+pidl], rsi
0x1801996bc  mov     rax, [rdi]
0x1801996bf  lea     rcx, [rbp+640h+pidl]
0x1801996c3  mov     [rbp+640h+ppidl], rcx
0x1801996c7  mov     [rbp+640h+ppidl+8], rsi
0x1801996cb  mov     byte ptr [rbp+640h+var_6A0], 1
0x1801996cf  lea     rdx, [rbp+640h+ppidl+8]
0x1801996d3  mov     rcx, rdi
0x1801996d6  mov     rax, [rax+20h]
0x1801996da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801996df  mov     r14d, eax
0x1801996e2  lea     rcx, [rbp+640h+ppidl]
0x1801996e6  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801996eb  xor     edi, edi
0x1801996ed  test    r14d, r14d
0x1801996f0  js      loc_18019986B
0x1801996f6  mov     [rbp+640h+var_680], rdi
0x1801996fa  mov     [rsp+740h+ppidlLast], rdi
0x1801996ff  lea     rcx, [rbp+640h+var_680]
0x180199703  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199708  lea     r9, [rsp+740h+ppidlLast]; ppidlLast
0x18019970d  lea     r8, [rbp+640h+var_680]; ppv
0x180199711  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180199718  mov     rcx, [rbp+640h+pidl]; pidl
0x18019971c  call    cs:__imp_SHBindToParent
0x180199722  test    eax, eax
0x180199724  js      loc_1801997DE
0x18019972a  mov     [rbp+640h+pidl1], rdi
0x18019972e  lea     rax, [rbp+640h+pidl1]
0x180199732  mov     [rbp+640h+ppidl], rax
0x180199736  mov     [rbp+640h+ppidl+8], rdi
0x18019973a  mov     byte ptr [rbp+640h+var_6A0], 1
0x18019973e  lea     r9, [rbp+640h+ppidl+8]; ppidl
0x180199742  xor     r8d, r8d; hToken
0x180199745  mov     edx, 4000h; dwFlags
0x18019974a  lea     rcx, FOLDERID_AppsFolder; rfid
0x180199751  call    cs:__imp_SHGetKnownFolderIDList
0x180199757  mov     edi, eax
0x180199759  shr     edi, 1Fh
0x18019975c  lea     rcx, [rbp+640h+ppidl]
0x180199760  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180199765  xor     dil, 1
0x180199769  jz      short loc_1801997D1
0x18019976b  mov     r8d, 1; fImmediate
0x180199771  mov     rdx, [rbp+640h+pidl]; pidl2
0x180199775  mov     rcx, [rbp+640h+pidl1]; pidl1
0x180199779  call    cs:__imp_ILIsParent
0x18019977f  xor     edi, edi
0x180199781  test    eax, eax
0x180199783  jz      short loc_1801997D3
0x180199785  mov     [rbp+640h+var_690], rdi
0x180199789  lea     rcx, [rbp+640h+var_690]
0x18019978d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199792  lea     r8, [rbp+640h+var_690]; ppv
0x180199796  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18019979d  mov     rcx, [rbp+640h+pidl]; pidl
0x1801997a1  call    cs:__imp_SHCreateItemFromIDList
0x1801997a7  test    eax, eax
0x1801997a9  js      short loc_1801997C6
0x1801997ab  lea     rcx, [rbp+640h+var_698]
0x1801997af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801997b4  mov     rcx, [rsp+740h+ppv]
0x1801997b9  mov     rax, [rbp+640h+var_690]
0x1801997bd  mov     [rsp+740h+ppv], rax
0x1801997c2  mov     [rbp+640h+var_690], rcx
0x1801997c6  lea     rcx, [rbp+640h+var_690]
0x1801997ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801997cf  jmp     short loc_1801997D3
0x1801997d1  xor     edi, edi
0x1801997d3  xor     edx, edx
0x1801997d5  lea     rcx, [rbp+640h+pidl1]
0x1801997d9  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1801997de  mov     rcx, [rbp+640h+var_698]; struct IShellLinkW *
0x1801997e2  test    rcx, rcx
0x1801997e5  jz      short loc_180199861
0x1801997e7  mov     [rsp+740h+var_6FF], 1
0x1801997ec  mov     [rsp+740h+bIgnoreCase], 104h; int
0x1801997f4  lea     r9, [rbp+640h+var_670]; unsigned __int16 *
0x1801997f8  mov     r8d, 8000h; unsigned int
0x1801997fe  mov     rdx, [rsp+740h+ppv]; struct IShellItem *
0x180199803  call    ?GetAppPathFromShortcut@@YAJPEAUIShellLinkW@@PEAUIShellItem@@KPEAGH@Z; GetAppPathFromShortcut(IShellLinkW *,IShellItem *,ulong,ushort *,int)
0x180199808  test    eax, eax
0x18019980a  js      short loc_180199861
0x18019980c  cmp     [rsp+740h+var_6F4], edi
0x180199810  jz      short loc_180199861
0x180199812  cmp     [rbp+640h+var_670], 3Ah ; ':'
0x180199817  jnz     short loc_180199830
0x180199819  cmp     [rbp+640h+var_66E], 3Ah ; ':'
0x18019981e  jnz     short loc_180199830
0x180199820  cmp     [rbp+640h+var_66C], 7Bh ; '{'
0x180199825  jnz     short loc_180199830
0x180199827  cmp     [rbp+640h+var_66A], di
0x18019982b  jz      short loc_180199830
0x18019982d  mov     dil, 1
0x180199830  mov     [rsp+740h+var_700], dil
0x180199835  xor     esi, esi
0x180199837  cmp     [rsp+740h+var_6F8], esi
0x18019983b  jnz     short loc_18019984F
0x18019983d  lea     rdx, [rbp+640h+var_670]; unsigned __int16 *
0x180199841  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x180199846  test    eax, eax
0x180199848  jnz     short loc_18019984F
0x18019984a  test    dil, dil
0x18019984d  jz      short loc_18019985F
0x18019984f  mov     rbx, [rbp+640h+pidl]
0x180199853  mov     [rbp+640h+var_678], rbx
0x180199857  xor     edi, edi
  ... truncated ...
```
