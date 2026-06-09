# CTaskbandPin::v_IsAcceptableTarget(_ITEMIDLIST_ABSOLUTE const *,IShellLinkW *,PINNABLEFLAG,IShellItem * *,ushort * *,ushort * *,IShellItem * *)

- ea: `0x1801acd70`
- end: `0x1801ad6a8`
- name: `?v_IsAcceptableTarget@CTaskbandPin@@MEAAHPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellLinkW@@W4PINNABLEFLAG@@PEAPEAUIShellItem@@PEAPEAG43@Z`
- size: `2360`
- prototype: `int __high(const struct _ITEMIDLIST_ABSOLUTE *, struct IShellLinkW *, enum PINNABLEFLAG, struct IShellItem **, unsigned __int16 **, unsigned __int16 **, struct IShellItem **)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f6cc`
- `0x18000fc30`
- `0x180016018`
- `0x180043ac0`
- `0x180044704`
- `0x1800859a4`
- `0x1800f1cf8`
- `0x180107920`
- `0x180162920`
- `0x180168178`
- `0x18016cf18`
- `0x180187884`
- `0x1801acd70`
- `0x180249490`
- `0x18024a53c`
- `0x1803e4d3c`
- `0x1803e4f54`
- `0x1803e5298`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ad54a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ad588`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ad54a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801ad588`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801ad2cb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1801ad2cb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801acfe1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801acfe1`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801ad347`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801ad417`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801ad5a0`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801ad347`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801ad417`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1801ad5a0`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1801ad123`
- `api-ms-win-storage-exports-internal-l1-1-0!SHGetKnownFolderIDList` at `0x1801ad123`
- `Windows.Storage!ILIsParent` at `0x1801ad151`
- `Windows.Storage!ILIsParent` at `0x1801ad151`
- `Windows.Storage!SHCreateItemInKnownFolder` at `0x1801ad5e0`
- `Windows.Storage!SHCreateItemInKnownFolder` at `0x1801ad5e0`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801ace8d`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801ad17f`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801ad3fc`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801ace8d`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801ad17f`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1801ad3fc`
- `Windows.Storage!SHBindToParent` at `0x1801ad0e8`
- `Windows.Storage!SHBindToParent` at `0x1801ad0e8`

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
        && !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_IsEmpty(ppidl) )
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
          wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
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
      wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pidl,
        0);
LABEL_56:
      if ( Instance < 0 )
      {
LABEL_114:
        wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
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
0x1801acd70  mov     [rsp-8+arg_10], rbx
0x1801acd75  push    rbp
0x1801acd76  push    rsi
0x1801acd77  push    rdi
0x1801acd78  push    r12
0x1801acd7a  push    r13
0x1801acd7c  push    r14
0x1801acd7e  push    r15
0x1801acd80  lea     rbp, [rsp-610h]
0x1801acd88  sub     rsp, 710h
0x1801acd8f  mov     rax, cs:__security_cookie
0x1801acd96  xor     rax, rsp
0x1801acd99  mov     [rbp+640h+var_40], rax
0x1801acda0  mov     r13d, r9d
0x1801acda3  mov     rdi, r8
0x1801acda6  mov     rbx, rdx
0x1801acda9  mov     [rsp+740h+var_6E8], rdx
0x1801acdae  mov     [rsp+740h+var_6F0], rcx
0x1801acdb3  mov     r15, [rbp+640h+arg_20]
0x1801acdba  mov     r12, [rbp+640h+arg_28]
0x1801acdc1  mov     rcx, [rbp+640h+arg_30]
0x1801acdc8  mov     [rsp+740h+var_6D8], rcx
0x1801acdcd  mov     rax, [rbp+640h+arg_38]
0x1801acdd4  mov     [rsp+740h+var_6E0], rax
0x1801acdd9  xor     edx, edx
0x1801acddb  mov     r14d, edx
0x1801acdde  test    rax, rax
0x1801acde1  jz      short loc_1801ACDE6
0x1801acde3  mov     [rax], rdx
0x1801acde6  test    r12, r12
0x1801acde9  jz      short loc_1801ACDEF
0x1801acdeb  mov     [r12], rdx
0x1801acdef  test    r15, r15
0x1801acdf2  jz      short loc_1801ACDF7
0x1801acdf4  mov     [r15], rdx
0x1801acdf7  mov     [rcx], rdx
0x1801acdfa  mov     esi, r13d
0x1801acdfd  and     esi, 4
0x1801ace00  mov     [rsp+740h+var_6F8], esi
0x1801ace04  mov     eax, 40000000h
0x1801ace09  mov     ecx, 60400000h
0x1801ace0e  cmovnz  eax, ecx
0x1801ace11  mov     [rsp+740h+var_6FC], eax
0x1801ace15  lea     rax, [rsp+740h+var_6FC]
0x1801ace1a  mov     qword ptr [rsp+740h+bIgnoreCase], rax; unsigned int *
0x1801ace1f  mov     r9d, 104h; unsigned int
0x1801ace25  lea     r8, [rbp+640h+var_460]; unsigned __int16 *
0x1801ace2c  mov     edx, 0C000h; unsigned int
0x1801ace31  mov     rcx, rbx; pidl
0x1801ace34  call    ?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)
0x1801ace39  test    eax, eax
0x1801ace3b  js      loc_1801AD67A
0x1801ace41  mov     eax, r13d
0x1801ace44  and     eax, 2
0x1801ace47  mov     [rsp+740h+var_6F4], eax
0x1801ace4b  jz      short loc_1801ACE6F
0x1801ace4d  test    esi, esi
0x1801ace4f  jnz     short loc_1801ACE6F
0x1801ace51  lea     rdx, [rbp+640h+var_460]; unsigned __int16 *
0x1801ace58  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x1801ace5d  test    eax, eax
0x1801ace5f  jnz     short loc_1801ACE6F
0x1801ace61  test    [rsp+740h+var_6FC], 40000000h
0x1801ace69  jnz     loc_1801AD67A
0x1801ace6f  mov     [rsp+740h+ppv], r14
0x1801ace74  lea     rcx, [rsp+740h+ppv]
0x1801ace79  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ace7e  lea     r8, [rsp+740h+ppv]; ppv
0x1801ace83  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1801ace8a  mov     rcx, rbx; pidl
0x1801ace8d  call    cs:__imp_SHCreateItemFromIDList
0x1801ace94  nop     dword ptr [rax+rax+00h]
0x1801ace99  mov     r14d, eax
0x1801ace9c  test    eax, eax
0x1801ace9e  js      loc_1801AD669
0x1801acea4  mov     [rbp+640h+var_6C0], 0
0x1801aceac  mov     rbx, [rsp+740h+ppv]
0x1801aceb1  mov     rax, [rbx]
0x1801aceb4  mov     rsi, [rax]
0x1801aceb7  lea     rcx, [rbp+640h+var_6C0]
0x1801acebb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801acec0  lea     r8, [rbp+640h+var_6C0]
0x1801acec4  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1801acecb  mov     rcx, rbx
0x1801acece  mov     rax, rsi
0x1801aced1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aced6  nop
0x1801aced7  xor     esi, esi
0x1801aced9  test    eax, eax
0x1801acedb  js      loc_1801ACF6A
0x1801acee1  mov     [rbp+640h+ppidl], rsi
0x1801acee5  mov     [rbp+640h+ppidl+8], rsi
0x1801acee9  mov     [rbp+640h+var_6A0], rsi
0x1801aceed  mov     rsi, [rbp+640h+var_6C0]
0x1801acef1  mov     rax, [rsi]
0x1801acef4  mov     rbx, [rax+88h]
0x1801acefb  lea     rcx, [rbp+640h+ppidl]; void *
0x1801aceff  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801acf04  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801acf08  mov     [rbp+640h+ppidl+8], rax
0x1801acf0c  mov     [rbp+640h+var_6A0], rax
0x1801acf10  lea     r8, [rbp+640h+ppidl]
0x1801acf14  lea     rdx, PKEY_AppUserModel_ParentID
0x1801acf1b  mov     rcx, rsi
0x1801acf1e  mov     rax, rbx
0x1801acf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801acf26  xor     esi, esi
0x1801acf28  test    eax, eax
0x1801acf2a  js      short loc_1801ACF42
0x1801acf2c  lea     rcx, [rbp+640h+ppidl]
0x1801acf30  call    ?_IsEmpty@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_IsEmpty(void)
0x1801acf35  test    al, al
0x1801acf37  mov     ebx, 80004005h
0x1801acf3c  cmovz   r14d, ebx
0x1801acf40  jmp     short loc_1801ACF47
0x1801acf42  mov     ebx, 80004005h
0x1801acf47  test    r13b, 10h
0x1801acf4b  jnz     short loc_1801ACF5C
0x1801acf4d  mov     rdx, [rbp+640h+var_6C0]; struct IShellItem2 *
0x1801acf51  call    ?IsPinnable@CTaskbandPin@@AEAA_NPEAUIShellItem2@@@Z; CTaskbandPin::IsPinnable(IShellItem2 *)
0x1801acf56  test    al, al
0x1801acf58  cmovz   r14d, ebx
0x1801acf5c  lea     rcx, [rbp+640h+ppidl]; void *
0x1801acf60  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801acf65  test    r14d, r14d
0x1801acf68  js      short loc_1801ACFA5
0x1801acf6a  mov     [rbp+640h+pidl], rsi
0x1801acf6e  lea     rcx, [rbp+640h+pidl]
0x1801acf72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801acf77  lea     rdx, [rbp+640h+pidl]; struct IShellItem *
0x1801acf7b  mov     rcx, [rsp+740h+ppv]; this
0x1801acf80  call    ?GetTaskbarPinnableItem@TaskbarPinHelper@@YAJPEAUIShellItem@@PEAPEAU2@@Z; TaskbarPinHelper::GetTaskbarPinnableItem(IShellItem *,IShellItem * *)
0x1801acf85  test    eax, eax
0x1801acf87  js      short loc_1801ACF9B
0x1801acf89  mov     rcx, [rsp+740h+ppv]
0x1801acf8e  mov     rax, [rbp+640h+pidl]
0x1801acf92  mov     [rsp+740h+ppv], rax
0x1801acf97  mov     [rbp+640h+pidl], rcx
0x1801acf9b  lea     rcx, [rbp+640h+pidl]
0x1801acf9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801acfa4  nop
0x1801acfa5  lea     rcx, [rbp+640h+var_6C0]
0x1801acfa9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801acfae  test    r14d, r14d
0x1801acfb1  js      loc_1801AD669
0x1801acfb7  mov     [rbp+640h+var_6C0], rsi
0x1801acfbb  lea     rcx, [rbp+640h+var_6C0]
0x1801acfbf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801acfc4  lea     rax, [rbp+640h+var_6C0]
0x1801acfc8  mov     qword ptr [rsp+740h+bIgnoreCase], rax; ppv
0x1801acfcd  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x1801acfd4  xor     edx, edx; pUnkOuter
0x1801acfd6  lea     r8d, [rdx+3]; dwClsContext
0x1801acfda  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x1801acfe1  call    cs:__imp_CoCreateInstance
0x1801acfe8  nop     dword ptr [rax+rax+00h]
0x1801acfed  mov     r14d, eax
0x1801acff0  test    eax, eax
0x1801acff2  js      loc_1801AD65F
0x1801acff8  mov     [rsp+740h+var_6FF], sil
0x1801acffd  mov     [rsp+740h+var_700], sil
0x1801ad002  xor     edx, edx; Val
0x1801ad004  mov     r8d, 208h; Size
0x1801ad00a  lea     rcx, [rbp+640h+var_670]; void *
0x1801ad00e  call    memset_0
0x1801ad013  mov     [rbp+640h+var_698], rdi
0x1801ad017  test    rdi, rdi
0x1801ad01a  jz      short loc_1801AD02F
0x1801ad01c  mov     rax, [rdi]
0x1801ad01f  mov     rcx, rdi
0x1801ad022  mov     rax, [rax+8]
0x1801ad026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad02b  mov     rdi, [rbp+640h+var_698]
0x1801ad02f  mov     rbx, rsi
0x1801ad032  mov     [rbp+640h+var_678], rbx
0x1801ad036  test    rdi, rdi
0x1801ad039  jnz     short loc_1801AD084
0x1801ad03b  mov     rsi, [rsp+740h+ppv]
0x1801ad040  mov     rax, [rsi]
0x1801ad043  mov     rdi, [rax+18h]
0x1801ad047  lea     rcx, [rbp+640h+var_698]
0x1801ad04b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad050  lea     rax, [rbp+640h+var_698]
0x1801ad054  mov     qword ptr [rsp+740h+bIgnoreCase], rax
0x1801ad059  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x1801ad060  lea     r8, BHID_SFUIObject
0x1801ad067  xor     edx, edx
0x1801ad069  mov     rcx, rsi
0x1801ad06c  mov     rax, rdi
0x1801ad06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad074  xor     edi, edi
0x1801ad076  test    eax, eax
0x1801ad078  js      loc_1801AD25A
0x1801ad07e  mov     rdi, [rbp+640h+var_698]
0x1801ad082  xor     esi, esi
0x1801ad084  mov     [rbp+640h+pidl], rsi
0x1801ad088  mov     rax, [rdi]
0x1801ad08b  lea     rcx, [rbp+640h+pidl]
0x1801ad08f  mov     [rbp+640h+ppidl], rcx
0x1801ad093  mov     [rbp+640h+ppidl+8], rsi
0x1801ad097  mov     byte ptr [rbp+640h+var_6A0], 1
0x1801ad09b  lea     rdx, [rbp+640h+ppidl+8]
0x1801ad09f  mov     rcx, rdi
0x1801ad0a2  mov     rax, [rax+20h]
0x1801ad0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ad0ab  mov     r14d, eax
0x1801ad0ae  lea     rcx, [rbp+640h+ppidl]
0x1801ad0b2  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801ad0b7  xor     edi, edi
0x1801ad0b9  test    r14d, r14d
0x1801ad0bc  js      loc_1801AD24F
0x1801ad0c2  mov     [rbp+640h+var_680], rdi
0x1801ad0c6  mov     [rsp+740h+ppidlLast], rdi
0x1801ad0cb  lea     rcx, [rbp+640h+var_680]
0x1801ad0cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad0d4  lea     r9, [rsp+740h+ppidlLast]; ppidlLast
0x1801ad0d9  lea     r8, [rbp+640h+var_680]; ppv
0x1801ad0dd  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x1801ad0e4  mov     rcx, [rbp+640h+pidl]; pidl
0x1801ad0e8  call    cs:__imp_SHBindToParent
0x1801ad0ef  nop     dword ptr [rax+rax+00h]
0x1801ad0f4  test    eax, eax
0x1801ad0f6  js      loc_1801AD1C2
0x1801ad0fc  mov     [rbp+640h+pidl1], rdi
0x1801ad100  lea     rax, [rbp+640h+pidl1]
0x1801ad104  mov     [rbp+640h+ppidl], rax
0x1801ad108  mov     [rbp+640h+ppidl+8], rdi
0x1801ad10c  mov     byte ptr [rbp+640h+var_6A0], 1
0x1801ad110  lea     r9, [rbp+640h+ppidl+8]; ppidl
0x1801ad114  xor     r8d, r8d; hToken
0x1801ad117  mov     edx, 4000h; dwFlags
0x1801ad11c  lea     rcx, FOLDERID_AppsFolder; rfid
0x1801ad123  call    cs:__imp_SHGetKnownFolderIDList
0x1801ad12a  nop     dword ptr [rax+rax+00h]
0x1801ad12f  mov     edi, eax
0x1801ad131  shr     edi, 1Fh
0x1801ad134  lea     rcx, [rbp+640h+ppidl]
0x1801ad138  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801ad13d  xor     dil, 1
0x1801ad141  jz      short loc_1801AD1B5
0x1801ad143  mov     r8d, 1; fImmediate
0x1801ad149  mov     rdx, [rbp+640h+pidl]; pidl2
0x1801ad14d  mov     rcx, [rbp+640h+pidl1]; pidl1
0x1801ad151  call    cs:__imp_ILIsParent
0x1801ad158  nop     dword ptr [rax+rax+00h]
0x1801ad15d  xor     edi, edi
0x1801ad15f  test    eax, eax
0x1801ad161  jz      short loc_1801AD1B7
0x1801ad163  mov     [rbp+640h+var_690], rdi
0x1801ad167  lea     rcx, [rbp+640h+var_690]
0x1801ad16b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad170  lea     r8, [rbp+640h+var_690]; ppv
0x1801ad174  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1801ad17b  mov     rcx, [rbp+640h+pidl]; pidl
0x1801ad17f  call    cs:__imp_SHCreateItemFromIDList
0x1801ad186  nop     dword ptr [rax+rax+00h]
0x1801ad18b  test    eax, eax
0x1801ad18d  js      short loc_1801AD1AA
0x1801ad18f  lea     rcx, [rbp+640h+var_698]
0x1801ad193  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad198  mov     rcx, [rsp+740h+ppv]
0x1801ad19d  mov     rax, [rbp+640h+var_690]
0x1801ad1a1  mov     [rsp+740h+ppv], rax
0x1801ad1a6  mov     [rbp+640h+var_690], rcx
0x1801ad1aa  lea     rcx, [rbp+640h+var_690]
0x1801ad1ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801ad1b3  jmp     short loc_1801AD1B7
0x1801ad1b5  xor     edi, edi
0x1801ad1b7  xor     edx, edx
0x1801ad1b9  lea     rcx, [rbp+640h+pidl1]
0x1801ad1bd  call    ?reset@?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMID_CHILD@@@Z; wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMID_CHILD *)
0x1801ad1c2  mov     rcx, [rbp+640h+var_698]; struct IShellLinkW *
0x1801ad1c6  test    rcx, rcx
0x1801ad1c9  jz      short loc_1801AD245
0x1801ad1cb  mov     [rsp+740h+var_6FF], 1
0x1801ad1d0  mov     [rsp+740h+bIgnoreCase], 104h; int
0x1801ad1d8  lea     r9, [rbp+640h+var_670]; unsigned __int16 *
0x1801ad1dc  mov     r8d, 8000h; unsigned int
0x1801ad1e2  mov     rdx, [rsp+740h+ppv]; struct IShellItem *
0x1801ad1e7  call    ?GetAppPathFromShortcut@@YAJPEAUIShellLinkW@@PEAUIShellItem@@KPEAGH@Z; GetAppPathFromShortcut(IShellLinkW *,IShellItem *,ulong,ushort *,int)
0x1801ad1ec  test    eax, eax
0x1801ad1ee  js      short loc_1801AD245
0x1801ad1f0  cmp     [rsp+740h+var_6F4], edi
0x1801ad1f4  jz      short loc_1801AD245
0x1801ad1f6  cmp     [rbp+640h+var_670], 3Ah ; ':'
0x1801ad1fb  jnz     short loc_1801AD214
0x1801ad1fd  cmp     [rbp+640h+var_66E], 3Ah ; ':'
0x1801ad202  jnz     short loc_1801AD214
0x1801ad204  cmp     [rbp+640h+var_66C], 7Bh ; '{'
0x1801ad209  jnz     short loc_1801AD214
0x1801ad20b  cmp     [rbp+640h+var_66A], di
0x1801ad20f  jz      short loc_1801AD214
0x1801ad211  mov     dil, 1
0x1801ad214  mov     [rsp+740h+var_700], dil
0x1801ad219  xor     esi, esi
0x1801ad21b  cmp     [rsp+740h+var_6F8], esi
0x1801ad21f  jnz     short loc_1801AD233
0x1801ad221  lea     rdx, [rbp+640h+var_670]; unsigned __int16 *
0x1801ad225  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x1801ad22a  test    eax, eax
  ... truncated ...
```
