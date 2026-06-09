# Windows::Internal::Shell::details::BuildItemFolderPath(IShellItem *,ushort * *)

- ea: `0x1800c3cbc`
- end: `0x1800c437c`
- name: `?BuildItemFolderPath@details@Shell@Internal@Windows@@YAJPEAUIShellItem@@PEAPEAG@Z`
- size: `1728`
- prototype: `__int64 __fastcall(Windows::Internal::Shell::details *__hidden this, struct IShellItem *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c2e6c`

## callees

- `0x180009fc0`
- `0x180038f50`
- `0x180044320`
- `0x180063050`
- `0x1800c29e8`
- `0x1800c2be0`
- `0x1800c34f0`
- `0x1800c35d8`
- `0x1800c3cbc`
- `0x1800c4384`
- `0x1800c4d70`
- `0x1800c4f78`
- `0x1800c5204`
- `0x1800c72b0`
- `0x1800fd500`
- `0x1801720d0`
- `0x18030815c`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x180634d00`
- `0x180634e24`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3fdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c40e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c40f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c410a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c418a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3e1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c3fdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c4038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c40e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c40f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c410a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c418a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c41c2`

## string_xrefs

- `0x1800c3ffb`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1800c4122`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1800c415a`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1800c420c`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1800c4260`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1800c42c7`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1800c4347`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x1806641fa`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`
- `0x180664250`: `onecoreuap\internal\shell\inc\private\FriendlyItemPath.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::Shell::details::BuildItemFolderPath(
        struct IShellItem *this,
        LPWSTR *a2,
        unsigned __int16 **a3)
{
  HRESULT (__stdcall *GetParent)(IShellItem *, IShellItem **); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  OLECHAR *v8; // rdi
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, struct IShellItem **); // rsi
  int v11; // eax
  int v12; // r12d
  const OLECHAR *v13; // r15
  __int64 v14; // rdx
  struct IShellItem2 *v15; // rcx
  int v16; // eax
  struct IShellItem2 *v17; // rcx
  struct IShellItem *v18; // rcx
  int ItemNamespaceCLSID; // eax
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v21)(_QWORD, GUID *, struct IShellItem **); // rbx
  __int64 v22; // rax
  int v23; // eax
  struct IShellItemVtbl *v24; // rax
  struct IShellItem2 *v25; // rcx
  struct IShellItem *v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  struct IShellItem2 *v29; // rsi
  HRESULT (__stdcall *GetDisplayName)(IShellItem2 *, SIGDN, LPWSTR *); // rbx
  __int64 v31; // rax
  int v32; // eax
  const OLECHAR *v33; // rcx
  int v34; // eax
  struct IShellItem2 *v35; // rcx
  struct IShellItem *v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rcx
  struct IShellItem *v38; // rdx
  struct IShellItem *v39; // rdx
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rcx
  struct IShellItem2 *v41; // rcx
  struct IShellItem *v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 *p_pwzURI; // rcx
  __int64 v47; // rax
  __int64 v48; // r9
  __int64 v49; // rdx
  unsigned __int16 **v50; // rax
  unsigned __int16 **v51; // r8
  int HostFromUri; // eax
  unsigned __int16 **v53; // rax
  __int64 v54; // rax
  OLECHAR *v55; // [rsp+20h] [rbp-59h] BYREF
  struct IShellItem2 *v56; // [rsp+28h] [rbp-51h] BYREF
  __int64 (__fastcall ***v57)(_QWORD, GUID *, struct IShellItem **); // [rsp+30h] [rbp-49h] BYREF
  struct IShellItem *v58; // [rsp+38h] [rbp-41h] BYREF
  LPCWSTR pwzURI; // [rsp+40h] [rbp-39h] BYREF
  struct IShellItemVtbl *v60; // [rsp+48h] [rbp-31h] BYREF
  int v61; // [rsp+50h] [rbp-29h] BYREF
  LPVOID v62; // [rsp+58h] [rbp-21h] BYREF
  int v63; // [rsp+60h] [rbp-19h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-11h]
  char v65[8]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v66; // [rsp+80h] [rbp+7h] BYREF
  struct _GUID Buf1; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  v57 = 0;
  GetParent = this->lpVtbl->GetParent;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
  v6 = ((__int64 (__fastcall *)(struct IShellItem *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IShellItem **)))GetParent)(
         this,
         &v57);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
      (const char *)(unsigned int)v6,
      (int)v55);
    v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
    if ( v57 )
    {
      v57 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v40)[2])(v40);
    }
    return v7;
  }
  v8 = 0;
  v55 = 0;
  v58 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  v10 = **v57;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
  v11 = v10(v9, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v58);
  v7 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
      (const char *)(unsigned int)v11,
      (int)v55);
    goto LABEL_71;
  }
  CItemAncestorIterator::CItemAncestorIterator((CItemAncestorIterator *)&v63, v58);
  v56 = 0;
  v12 = 0;
  v13 = &WindowName;
  while ( 1 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    if ( !CItemAncestorIterator::Next((CItemAncestorIterator *)&v63, &v56) || (v15 = v56) == 0 )
    {
      v7 = v63;
      if ( v63 < 0 )
      {
        v48 = (unsigned int)v63;
        v49 = 223;
      }
      else
      {
        if ( v8 )
          v13 = v8;
        v16 = _AllocString<CTCoAllocPolicy>(v15, v14, v13, a2);
        v7 = v16;
        if ( v16 >= 0 )
        {
          v17 = v56;
          if ( v56 )
          {
            v56 = 0;
            ((void (__fastcall *)(struct IShellItem2 *))v17->lpVtbl->Release)(v17);
          }
          CoTaskMemFree(pv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
          v18 = v58;
          if ( v58 )
          {
            v58 = 0;
            ((void (__fastcall *)(struct IShellItem *))v18->lpVtbl->Release)(v18);
          }
          if ( v8 )
            CoTaskMemFree(v8);
          goto LABEL_27;
        }
        v48 = (unsigned int)v16;
        v49 = 224;
      }
      goto LABEL_91;
    }
    Buf1 = 0;
    ItemNamespaceCLSID = GetItemNamespaceCLSID((struct IShellItem *)v56, &Buf1);
    v7 = ItemNamespaceCLSID;
    if ( ItemNamespaceCLSID < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
        (const char *)(unsigned int)ItemNamespaceCLSID,
        (int)v55);
      v41 = v56;
      if ( v56 )
      {
        v56 = 0;
        ((void (__fastcall *)(struct IShellItem2 *))v41->lpVtbl->Release)(v41);
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
      v42 = v58;
      if ( v58 )
      {
        v58 = 0;
        ((void (__fastcall *)(struct IShellItem *))v42->lpVtbl->Release)(v42);
      }
      if ( v8 )
        CoTaskMemFree(v8);
      v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
      if ( v57 )
      {
        v57 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v43)[2])(v43);
      }
      return v7;
    }
    if ( !memcmp_0(&Buf1, &CLSID_NetworkExplorerFolder, 0x10u) || !memcmp_0(&Buf1, &CLSID_NetworkPlaces, 0x10u) )
      break;
    if ( !memcmp_0(&Buf1, &CLSID_Internet, 0x10u) )
    {
      pwzURI = 0;
      v50 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pwzURI);
      if ( (int)GetOnlineFileUrlFromParsingName(this, v50, 0) >= 0 )
      {
        if ( pwzURI )
        {
          HostFromUri = Windows::Internal::Shell::details::GetHostFromUri(pwzURI, a2, v51);
          v7 = HostFromUri;
          if ( HostFromUri >= 0 )
            goto LABEL_90;
          v45 = 182;
LABEL_89:
          v44 = (unsigned int)HostFromUri;
        }
        else
        {
          v7 = -2147024809;
          v44 = 2147942487LL;
          v45 = 181;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v45,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
          (const char *)v44,
          (int)v55);
        p_pwzURI = (__int64 *)&pwzURI;
        goto LABEL_69;
      }
      HostFromUri = Windows::Internal::Shell::details::GetHostFromUriItem(
                      (Windows::Internal::Shell::details *)this,
                      (struct IShellItem *)a2,
                      v51);
      v7 = HostFromUri;
      if ( HostFromUri < 0 )
      {
        v45 = 187;
        goto LABEL_89;
      }
LABEL_90:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pwzURI);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
      CItemAncestorIterator::~CItemAncestorIterator((CItemAncestorIterator *)&v63);
      v7 = 0;
LABEL_71:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v57);
      return v7;
    }
    if ( v12 == 1 )
    {
      v61 = 0;
      if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, int *))v56->lpVtbl->GetBool)(
             v56,
             &PKEY_Volume_IsRoot,
             &v61) >= 0
        && v61 )
      {
        v47 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v60,
                &WindowName,
                -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v55,
          v47);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v60);
        v8 = v55;
        if ( !v55 )
        {
          v7 = -2147024882;
          v48 = 2147942414LL;
          v49 = 201;
LABEL_91:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v49,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
            (const char *)v48,
            (int)v55);
          goto LABEL_70;
        }
      }
      else if ( Windows::Internal::Shell::details::IsThisPCKnownFolder((Windows::Internal::Shell::details *)v56, v38)
             || Windows::Internal::Shell::details::IsDesktopKnownFolder((Windows::Internal::Shell::details *)v56, v39) )
      {
        v66 = 0;
        v53 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v66);
        if ( (int)GetStorageProviderNameForFolder((struct IShellItem *)v56, v53) >= 0 )
        {
          v54 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pwzURI,
                  v66,
                  -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v55,
            v54);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pwzURI);
          v8 = v55;
          if ( !v55 )
          {
            v7 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xD4,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
              (const char *)0x8007000ELL,
              0);
            p_pwzURI = &v66;
            goto LABEL_69;
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v66);
      }
    }
    v62 = 0;
    v29 = v56;
    GetDisplayName = v56->lpVtbl->GetDisplayName;
    v31 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v62);
    v32 = ((__int64 (__fastcall *)(struct IShellItem2 *, _QWORD, __int64))GetDisplayName)(v29, 0, v31);
    v7 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
        (const char *)(unsigned int)v32,
        (int)v55);
      if ( v62 )
        CoTaskMemFree(v62);
      v35 = v56;
      if ( v56 )
      {
        v56 = 0;
        ((void (__fastcall *)(struct IShellItem2 *))v35->lpVtbl->Release)(v35);
      }
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
      v36 = v58;
      if ( v58 )
      {
        v58 = 0;
        ((void (__fastcall *)(struct IShellItem *))v36->lpVtbl->Release)(v36);
      }
      if ( v8 )
        CoTaskMemFree(v8);
      v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
      if ( v57 )
      {
        v57 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v37)[2])(v37);
      }
      return v7;
    }
    v33 = &WindowName;
    if ( v8 )
      v33 = v8;
    v34 = PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,260>(
            v33,
            v62,
            &v55);
    v7 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
        (const char *)(unsigned int)v34,
        (int)v55);
      p_pwzURI = (__int64 *)&v62;
      goto LABEL_69;
    }
    if ( v62 )
      CoTaskMemFree(v62);
    ++v12;
    v8 = v55;
  }
  v60 = 0;
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  v21 = (*v57)[5];
  v22 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v60);
  v23 = v21(v20, (GUID *)2147794944LL, (struct IShellItem **)v22);
  v7 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\FriendlyItemPath.h",
      (const char *)(unsigned int)v23,
      (int)v55);
    p_pwzURI = (__int64 *)&v60;
LABEL_69:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(p_pwzURI);
LABEL_70:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v56);
    CItemAncestorIterator::~CItemAncestorIterator((CItemAncestorIterator *)&v63);
    goto LABEL_71;
  }
  v24 = v60;
  v60 = 0;
  *a2 = (LPWSTR)v24;
  v25 = v56;
  if ( v56 )
  {
    v56 = 0;
    ((void (__fastcall *)(struct IShellItem2 *))v25->lpVtbl->Release)(v25);
  }
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v65);
  v26 = v58;
  if ( v58 )
  {
    v58 = 0;
    ((void (__fastcall *)(struct IShellItem *))v26->lpVtbl->Release)(v26);
  }
  if ( v8 )
    CoTaskMemFree(v8);
LABEL_27:
  v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v57;
  if ( v57 )
  {
    v57 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x1800c3cbc  mov     [rsp-8+arg_10], rbx
0x1800c3cc1  push    rbp
0x1800c3cc2  push    rsi
0x1800c3cc3  push    rdi
0x1800c3cc4  push    r12
0x1800c3cc6  push    r13
0x1800c3cc8  push    r14
0x1800c3cca  push    r15
0x1800c3ccc  lea     rbp, [rsp-27h]
0x1800c3cd1  sub     rsp, 0A0h
0x1800c3cd8  mov     rax, cs:__security_cookie
0x1800c3cdf  xor     rax, rsp
0x1800c3ce2  mov     [rbp+57h+var_38], rax
0x1800c3ce6  mov     r14, rdx
0x1800c3ce9  mov     r13, rcx
0x1800c3cec  xor     esi, esi
0x1800c3cee  mov     [rdx], rsi
0x1800c3cf1  mov     [rbp+57h+var_A0], rsi
0x1800c3cf5  mov     rax, [rcx]
0x1800c3cf8  mov     rbx, [rax+20h]
0x1800c3cfc  lea     rcx, [rbp+57h+var_A0]
0x1800c3d00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c3d05  lea     rdx, [rbp+57h+var_A0]
0x1800c3d09  mov     rcx, r13
0x1800c3d0c  mov     rax, rbx
0x1800c3d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3d14  mov     ebx, eax
0x1800c3d16  test    eax, eax
0x1800c3d18  js      loc_1800C411B
0x1800c3d1e  mov     edi, esi
0x1800c3d20  mov     [rbp+57h+var_B0], rsi
0x1800c3d24  mov     [rbp+57h+var_98], rsi
0x1800c3d28  mov     rbx, [rbp+57h+var_A0]
0x1800c3d2c  mov     rax, [rbx]
0x1800c3d2f  mov     rsi, [rax]
0x1800c3d32  lea     rcx, [rbp+57h+var_98]
0x1800c3d36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c3d3b  lea     r8, [rbp+57h+var_98]
0x1800c3d3f  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x1800c3d46  mov     rcx, rbx
0x1800c3d49  mov     rax, rsi
0x1800c3d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3d51  mov     ebx, eax
0x1800c3d53  xor     esi, esi
0x1800c3d55  test    eax, eax
0x1800c3d57  js      loc_1800C4259
0x1800c3d5d  mov     rdx, [rbp+57h+var_98]; struct IShellItem *
0x1800c3d61  lea     rcx, [rbp+57h+var_70]; this
0x1800c3d65  call    ??0CItemAncestorIterator@@QEAA@PEAUIShellItem@@@Z; CItemAncestorIterator::CItemAncestorIterator(IShellItem *)
0x1800c3d6a  nop
0x1800c3d6b  mov     [rbp+57h+var_A8], rsi
0x1800c3d6f  mov     r12d, esi
0x1800c3d72  lea     r15, WindowName
0x1800c3d79  lea     rcx, [rbp+57h+var_A8]
0x1800c3d7d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c3d82  lea     rdx, [rbp+57h+var_A8]; struct IShellItem2 **
0x1800c3d86  lea     rcx, [rbp+57h+var_70]; this
0x1800c3d8a  call    ?Next@CItemAncestorIterator@@QEAA_NPEAPEAUIShellItem2@@@Z; CItemAncestorIterator::Next(IShellItem2 * *)
0x1800c3d8f  test    al, al
0x1800c3d91  jz      short loc_1800C3DA0
0x1800c3d93  mov     rcx, [rbp+57h+var_A8]; struct IShellItem *
0x1800c3d97  test    rcx, rcx
0x1800c3d9a  jnz     loc_1800C3E2F
0x1800c3da0  mov     ebx, [rbp+57h+var_70]
0x1800c3da3  test    ebx, ebx
0x1800c3da5  js      loc_1800C4362
0x1800c3dab  test    rdi, rdi
0x1800c3dae  cmovnz  r15, rdi
0x1800c3db2  mov     r9, r14
0x1800c3db5  mov     r8, r15
0x1800c3db8  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800c3dbd  mov     ebx, eax
0x1800c3dbf  test    eax, eax
0x1800c3dc1  js      loc_1800C436F
0x1800c3dc7  mov     rcx, [rbp+57h+var_A8]
0x1800c3dcb  test    rcx, rcx
0x1800c3dce  jz      short loc_1800C3DE1
0x1800c3dd0  mov     [rbp+57h+var_A8], rsi
0x1800c3dd4  mov     rax, [rcx]
0x1800c3dd7  mov     rax, [rax+10h]
0x1800c3ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3de0  nop
0x1800c3de1  mov     rcx, [rbp+57h+pv]; pv
0x1800c3de5  call    cs:__imp_CoTaskMemFree
0x1800c3dec  nop     dword ptr [rax+rax+00h]
0x1800c3df1  lea     rcx, [rbp+57h+var_58]
0x1800c3df5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c3dfa  nop
0x1800c3dfb  mov     rcx, [rbp+57h+var_98]
0x1800c3dff  test    rcx, rcx
0x1800c3e02  jz      short loc_1800C3E15
0x1800c3e04  mov     [rbp+57h+var_98], rsi
0x1800c3e08  mov     rax, [rcx]
0x1800c3e0b  mov     rax, [rax+10h]
0x1800c3e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3e14  nop
0x1800c3e15  test    rdi, rdi
0x1800c3e18  jz      short loc_1800C3E2A
0x1800c3e1a  mov     rcx, rdi; pv
0x1800c3e1d  call    cs:__imp_CoTaskMemFree
0x1800c3e24  nop     dword ptr [rax+rax+00h]
0x1800c3e29  nop
0x1800c3e2a  jmp     loc_1800C3F19
0x1800c3e2f  xorps   xmm0, xmm0
0x1800c3e32  movups  [rbp+57h+Buf1], xmm0
0x1800c3e36  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1800c3e3a  call    ?GetItemNamespaceCLSID@@YAJPEAUIShellItem@@PEAU_GUID@@@Z; GetItemNamespaceCLSID(IShellItem *,_GUID *)
0x1800c3e3f  mov     ebx, eax
0x1800c3e41  test    eax, eax
0x1800c3e43  js      loc_1800C4153
0x1800c3e49  mov     ebx, 10h
0x1800c3e4e  mov     r8d, ebx; Size
0x1800c3e51  lea     rdx, CLSID_NetworkExplorerFolder; Buf2
0x1800c3e58  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800c3e5c  call    memcmp_0
0x1800c3e61  test    eax, eax
0x1800c3e63  jz      short loc_1800C3E80
0x1800c3e65  mov     r8d, ebx; Size
0x1800c3e68  lea     rdx, CLSID_NetworkPlaces; Buf2
0x1800c3e6f  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800c3e73  call    memcmp_0
0x1800c3e78  test    eax, eax
0x1800c3e7a  jnz     loc_1800C3F5D
0x1800c3e80  mov     [rbp+57h+var_88], rsi
0x1800c3e84  mov     rsi, [rbp+57h+var_A0]
0x1800c3e88  mov     rax, [rsi]
0x1800c3e8b  mov     rbx, [rax+28h]
0x1800c3e8f  lea     rcx, [rbp+57h+var_88]
0x1800c3e93  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800c3e98  mov     r8, rax
0x1800c3e9b  mov     edx, 8004C000h
0x1800c3ea0  mov     rcx, rsi
0x1800c3ea3  mov     rax, rbx
0x1800c3ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3eab  mov     ebx, eax
0x1800c3ead  xor     esi, esi
0x1800c3eaf  test    eax, eax
0x1800c3eb1  js      loc_1800C4340
0x1800c3eb7  mov     rax, [rbp+57h+var_88]
0x1800c3ebb  mov     [rbp+57h+var_88], rsi
0x1800c3ebf  mov     [r14], rax
0x1800c3ec2  mov     rcx, [rbp+57h+var_A8]
0x1800c3ec6  test    rcx, rcx
0x1800c3ec9  jz      short loc_1800C3EDC
0x1800c3ecb  mov     [rbp+57h+var_A8], rsi
0x1800c3ecf  mov     rax, [rcx]
0x1800c3ed2  mov     rax, [rax+10h]
0x1800c3ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3edb  nop
0x1800c3edc  mov     rcx, [rbp+57h+pv]; pv
0x1800c3ee0  call    cs:__imp_CoTaskMemFree
0x1800c3ee7  nop     dword ptr [rax+rax+00h]
0x1800c3eec  lea     rcx, [rbp+57h+var_58]
0x1800c3ef0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c3ef5  nop
0x1800c3ef6  mov     rcx, [rbp+57h+var_98]
0x1800c3efa  test    rcx, rcx
0x1800c3efd  jz      short loc_1800C3F10
0x1800c3eff  mov     [rbp+57h+var_98], rsi
0x1800c3f03  mov     rax, [rcx]
0x1800c3f06  mov     rax, [rax+10h]
0x1800c3f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3f0f  nop
0x1800c3f10  test    rdi, rdi
0x1800c3f13  jnz     loc_1800C4107
0x1800c3f19  mov     rcx, [rbp+57h+var_A0]
0x1800c3f1d  test    rcx, rcx
0x1800c3f20  jz      short loc_1800C3F33
0x1800c3f22  mov     [rbp+57h+var_A0], rsi
0x1800c3f26  mov     rax, [rcx]
0x1800c3f29  mov     rax, [rax+10h]
0x1800c3f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3f32  nop
0x1800c3f33  xor     eax, eax
0x1800c3f35  mov     rcx, [rbp+57h+var_38]
0x1800c3f39  xor     rcx, rsp; StackCookie
0x1800c3f3c  call    __security_check_cookie
0x1800c3f41  mov     rbx, [rsp+0D0h+arg_10]
0x1800c3f49  add     rsp, 0A0h
0x1800c3f50  pop     r15
0x1800c3f52  pop     r14
0x1800c3f54  pop     r13
0x1800c3f56  pop     r12
0x1800c3f58  pop     rdi
0x1800c3f59  pop     rsi
0x1800c3f5a  pop     rbp
0x1800c3f5b  retn
0x1800c3f5d  mov     r8, rbx; Size
0x1800c3f60  lea     rdx, CLSID_Internet; Buf2
0x1800c3f67  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800c3f6b  call    memcmp_0
0x1800c3f70  test    eax, eax
0x1800c3f72  jz      loc_1800C42E2
0x1800c3f78  cmp     r12d, 1
0x1800c3f7c  jz      loc_1800C4092
0x1800c3f82  mov     [rbp+57h+var_78], rsi
0x1800c3f86  mov     rsi, [rbp+57h+var_A8]
0x1800c3f8a  mov     rax, [rsi]
0x1800c3f8d  mov     rbx, [rax+28h]
0x1800c3f91  lea     rcx, [rbp+57h+var_78]
0x1800c3f95  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800c3f9a  mov     r8, rax
0x1800c3f9d  xor     edx, edx
0x1800c3f9f  mov     rcx, rsi
0x1800c3fa2  mov     rax, rbx
0x1800c3fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3faa  mov     ebx, eax
0x1800c3fac  xor     esi, esi
0x1800c3fae  test    eax, eax
0x1800c3fb0  js      short loc_1800C3FF4
0x1800c3fb2  mov     rcx, r15
0x1800c3fb5  test    rdi, rdi
0x1800c3fb8  cmovnz  rcx, rdi
0x1800c3fbc  lea     r8, [rbp+57h+var_B0]
0x1800c3fc0  mov     rdx, [rbp+57h+var_78]
0x1800c3fc4  call    ??$Append@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAE@@PathAlloc@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PathAlloc::Append<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,260>(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800c3fc9  mov     ebx, eax
0x1800c3fcb  test    eax, eax
0x1800c3fcd  js      loc_1800C42C0
0x1800c3fd3  mov     rcx, [rbp+57h+var_78]; pv
0x1800c3fd7  test    rcx, rcx
0x1800c3fda  jz      short loc_1800C3FE8
0x1800c3fdc  call    cs:__imp_CoTaskMemFree
0x1800c3fe3  nop     dword ptr [rax+rax+00h]
0x1800c3fe8  inc     r12d
0x1800c3feb  mov     rdi, [rbp+57h+var_B0]
0x1800c3fef  jmp     loc_1800C3D79
0x1800c3ff4  mov     rcx, [rbp+5Fh]; this
0x1800c3ff8  mov     r9d, ebx; char *
0x1800c3ffb  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800c4002  mov     edx, 0DAh; void *
0x1800c4007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c400c  nop
0x1800c400d  mov     rcx, [rbp+57h+var_78]; pv
0x1800c4011  test    rcx, rcx
0x1800c4014  jnz     loc_1800C40E2
0x1800c401a  mov     rcx, [rbp+57h+var_A8]
0x1800c401e  test    rcx, rcx
0x1800c4021  jz      short loc_1800C4034
0x1800c4023  mov     [rbp+57h+var_A8], rsi
0x1800c4027  mov     rax, [rcx]
0x1800c402a  mov     rax, [rax+10h]
0x1800c402e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4033  nop
0x1800c4034  mov     rcx, [rbp+57h+pv]; pv
0x1800c4038  call    cs:__imp_CoTaskMemFree
0x1800c403f  nop     dword ptr [rax+rax+00h]
0x1800c4044  lea     rcx, [rbp+57h+var_58]
0x1800c4048  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c404d  nop
0x1800c404e  mov     rcx, [rbp+57h+var_98]
0x1800c4052  test    rcx, rcx
0x1800c4055  jz      short loc_1800C4068
0x1800c4057  mov     [rbp+57h+var_98], rsi
0x1800c405b  mov     rax, [rcx]
0x1800c405e  mov     rax, [rax+10h]
0x1800c4062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4067  nop
0x1800c4068  test    rdi, rdi
0x1800c406b  jnz     loc_1800C40F3
0x1800c4071  mov     rcx, [rbp+57h+var_A0]
0x1800c4075  test    rcx, rcx
0x1800c4078  jz      short loc_1800C408B
0x1800c407a  mov     [rbp+57h+var_A0], rsi
0x1800c407e  mov     rax, [rcx]
0x1800c4081  mov     rax, [rax+10h]
0x1800c4085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c408a  nop
0x1800c408b  mov     eax, ebx
0x1800c408d  jmp     loc_1800C3F35
0x1800c4092  mov     [rbp+57h+var_80], esi
0x1800c4095  mov     rcx, [rbp+57h+var_A8]
0x1800c4099  mov     rax, [rcx]
0x1800c409c  lea     r8, [rbp+57h+var_80]
0x1800c40a0  lea     rdx, PKEY_Volume_IsRoot
0x1800c40a7  mov     rax, [rax+0A0h]
0x1800c40ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c40b3  test    eax, eax
0x1800c40b5  jns     loc_1800C4273
0x1800c40bb  mov     rcx, [rbp+57h+var_A8]; this
0x1800c40bf  call    ?IsThisPCKnownFolder@details@Shell@Internal@Windows@@YA_NPEAUIShellItem@@@Z; Windows::Internal::Shell::details::IsThisPCKnownFolder(IShellItem *)
0x1800c40c4  test    al, al
0x1800c40c6  jnz     loc_1806641A2
0x1800c40cc  mov     rcx, [rbp+57h+var_A8]; this
0x1800c40d0  call    ?IsDesktopKnownFolder@details@Shell@Internal@Windows@@YA_NPEAUIShellItem@@@Z; Windows::Internal::Shell::details::IsDesktopKnownFolder(IShellItem *)
0x1800c40d5  test    al, al
0x1800c40d7  jz      loc_1800C3F82
0x1800c40dd  jmp     loc_1806641A2
0x1800c40e2  call    cs:__imp_CoTaskMemFree
0x1800c40e9  nop     dword ptr [rax+rax+00h]
0x1800c40ee  jmp     loc_1800C401A
0x1800c40f3  mov     rcx, rdi; pv
0x1800c40f6  call    cs:__imp_CoTaskMemFree
0x1800c40fd  nop     dword ptr [rax+rax+00h]
0x1800c4102  jmp     loc_1800C4071
0x1800c4107  mov     rcx, rdi; pv
0x1800c410a  call    cs:__imp_CoTaskMemFree
0x1800c4111  nop     dword ptr [rax+rax+00h]
0x1800c4116  jmp     loc_1800C3F19
0x1800c411b  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
