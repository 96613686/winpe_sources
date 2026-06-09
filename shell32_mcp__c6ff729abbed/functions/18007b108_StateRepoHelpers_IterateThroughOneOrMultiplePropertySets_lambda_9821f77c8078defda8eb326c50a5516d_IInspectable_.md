# StateRepoHelpers::IterateThroughOneOrMultiplePropertySets<_lambda_9821f77c8078defda8eb326c50a5516d_>(IInspectable *,ushort const *,_lambda_9821f77c8078defda8eb326c50a5516d_ const &)

- ea: `0x18007b108`
- end: `0x18007b93c`
- name: `??$IterateThroughOneOrMultiplePropertySets@V_lambda_9821f77c8078defda8eb326c50a5516d_@@@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGAEBV_lambda_9821f77c8078defda8eb326c50a5516d_@@@Z`
- size: `2100`
- prototype: `__int64 __fastcall(StateRepoHelpers *this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180079f98`

## callees

- `0x18000f6cc`
- `0x180038608`
- `0x18007a73c`
- `0x18007aa50`
- `0x18007ac94`
- `0x18007b108`
- `0x18007b944`
- `0x18007b98c`
- `0x18007b9b0`
- `0x18007b9dc`
- `0x18007c0f4`
- `0x18007c7e0`
- `0x18007c880`
- `0x1801b6558`
- `0x1801d29a8`
- `0x180249490`
- `0x18029fcc4`
- `0x1802a0500`
- `0x1802cbe34`
- `0x180337630`
- `0x1804aa57c`
- `0x1804aa5b8`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b4fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b4fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b59a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007b89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b43a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b53e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b714`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b43a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b53e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007b714`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b31c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b375`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b31c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007b375`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007b513`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007b513`

## string_xrefs

- `0x18007b6eb`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b727`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b770`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b7a3`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b8c4`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b8ee`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007b36e`: `@ShellNewCommandParameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall StateRepoHelpers::IterateThroughOneOrMultiplePropertySets<_lambda_9821f77c8078defda8eb326c50a5516d_>(
        __int64 (__fastcall ***this)(StateRepoHelpers *, GUID *, NewMenuEntry **),
        __int64 a2,
        __int64 a3)
{
  __int64 (__fastcall *v5)(StateRepoHelpers *, GUID *, NewMenuEntry **); // rbx
  int v6; // eax
  StateRepoHelpers *v7; // r15
  NewMenuEntry *v8; // rdi
  __int64 v9; // rbx
  unsigned int v10; // eax
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rcx
  NewMenuEntry *v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64, __int64); // rbx
  unsigned int i; // edi
  struct Windows::Internal::StateRepository::IFileTypeAssociation *v20; // r12
  __int64 v21; // rsi
  int v22; // eax
  __int64 v23; // r14
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // eax
  __int64 v28; // r14
  HRESULT v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  char v32; // bl
  __int64 v33; // rcx
  __int64 v34; // rcx
  HSTRING *v36; // r9
  int v37; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int Reserved1; // edx
  NewMenuEntry *v40; // rax
  __int64 v41; // rcx
  const WCHAR *v42; // rax
  unsigned int v43; // edx
  NewMenuEntry *v44; // rcx
  __int64 v45; // rax
  NewMenuEntry *v46; // rbx
  const unsigned __int16 *v47; // rax
  StateRepoNewMenuCache *v48; // rcx
  __int64 v49; // rcx
  NewMenuEntry *v50; // rcx
  int v51; // eax
  int v52; // eax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned int v56; // edx
  NewMenuEntry *v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  NewMenuEntry *v61; // rcx
  unsigned __int64 v62; // r9
  __int64 v63; // rdx
  __int64 v64; // rdx
  void **v65; // [rsp+20h] [rbp-59h]
  int v66; // [rsp+20h] [rbp-59h]
  int v67; // [rsp+20h] [rbp-59h]
  int v68; // [rsp+20h] [rbp-59h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  LPWSTR ppwsz; // [rsp+50h] [rbp-29h] BYREF
  struct _GUID v72; // [rsp+58h] [rbp-21h] BYREF
  NewMenuEntry *v73; // [rsp+68h] [rbp-11h] BYREF
  __int64 v74; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER v75; // [rsp+78h] [rbp-1h] BYREF
  __int64 v76; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v74 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
  v74 = 0;
  v73 = 0;
  v5 = **this;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
  v6 = v5((StateRepoHelpers *)this, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v73);
  v7 = (StateRepoHelpers *)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h";
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v6,
      (int)v65);
    goto LABEL_48;
  }
  *(_QWORD *)&v72.Data1 = 0;
  v8 = v73;
  v9 = *(_QWORD *)v73;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v76 = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(8u);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v75, L"FileType", v10, 8u);
  v11 = (*(__int64 (__fastcall **)(NewMenuEntry *, __int64, struct _GUID *))(v9 + 48))(v8, v76, &v72);
  if ( v11 < 0 )
  {
    if ( v11 != -2147483637 )
    {
      v62 = (unsigned int)v11;
      v63 = 47;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v63,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
        (const char *)v62,
        (int)v65);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v73);
      goto LABEL_50;
    }
    v49 = *(_QWORD *)&v72.Data1;
    if ( *(_QWORD *)&v72.Data1 )
    {
      *(_QWORD *)&v72.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
LABEL_48:
    v50 = v73;
    if ( v73 )
    {
      v73 = 0;
      (*(void (__fastcall **)(NewMenuEntry *))(*(_QWORD *)v50 + 16LL))(v50);
    }
    goto LABEL_50;
  }
  v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v72.Data1)(
          *(_QWORD *)&v72.Data1,
          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
          &v74);
  if ( (unsigned int)(v12 + 2147467263) > 1 )
  {
    if ( v12 >= 0 )
    {
      v60 = *(_QWORD *)&v72.Data1;
      if ( *(_QWORD *)&v72.Data1 )
      {
        *(_QWORD *)&v72.Data1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      }
      v61 = v73;
      if ( v73 )
      {
        v73 = 0;
        (*(void (__fastcall **)(NewMenuEntry *))(*(_QWORD *)v61 + 16LL))(v61);
      }
      goto LABEL_9;
    }
    v62 = (unsigned int)v12;
    v63 = 50;
    goto LABEL_80;
  }
  v13 = *(_QWORD *)&v72.Data1;
  if ( *(_QWORD *)&v72.Data1 )
  {
    *(_QWORD *)&v72.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v73;
  if ( v73 )
  {
    v73 = 0;
    (*(void (__fastcall **)(NewMenuEntry *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( v12 >= 0 )
  {
LABEL_9:
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v75);
    v15 = v74;
    v18 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v74 + 304LL);
    v16 = wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(&v75);
    v17 = wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned int>(
            &v75,
            &hstringHeader,
            v16);
    LODWORD(v18) = v18(v15, v17 + 8);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned int>::~size_address_ptr<unsigned int>(&hstringHeader);
    if ( (int)v18 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( (unsigned __int64)i >= *(_QWORD *)&v75.Reserved.Reserved2[8] )
        {
          wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v75);
          goto LABEL_24;
        }
        v7 = *(StateRepoHelpers **)wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](&v75);
        v20 = **(struct Windows::Internal::StateRepository::IFileTypeAssociation ***)(a3 + 16);
        v21 = *(_QWORD *)(a3 + 8);
        *(_QWORD *)&v72.Data1 = 0;
        v18 = **(__int64 (__fastcall ***)(__int64, __int64))v7;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        v22 = ((__int64 (__fastcall *)(StateRepoHelpers *, GUID *, struct _GUID *))v18)(
                v7,
                &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                &v72);
        LODWORD(v18) = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD0,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)(unsigned int)v22,
            (int)v65);
          v58 = *(_QWORD *)&v72.Data1;
          if ( *(_QWORD *)&v72.Data1 )
          {
            *(_QWORD *)&v72.Data1 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
          }
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)(unsigned int)v18,
            v68);
          goto LABEL_64;
        }
        v72.Data4[0] = 0;
        v18 = *(__int64 (__fastcall **)(__int64, __int64))&v72.Data1;
        v23 = **(_QWORD **)&v72.Data1;
        string = 0;
        v24 = WindowsCreateStringReference(L"@ShellNewFileName", 0x11u, &hstringHeader, &string);
        if ( v24 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
          goto LABEL_90;
        }
        v27 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(__int64, __int64), HSTRING, unsigned __int8 *))(v23 + 64))(
                v18,
                string,
                v72.Data4);
        LODWORD(v18) = v27;
        if ( v27 < 0 )
        {
          v64 = 213;
LABEL_88:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v64,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)(unsigned int)v27,
            (int)v65);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
          goto LABEL_68;
        }
        v72.Data4[1] = 0;
        v18 = *(__int64 (__fastcall **)(__int64, __int64))&v72.Data1;
        v28 = **(_QWORD **)&v72.Data1;
        string = 0;
        v29 = WindowsCreateStringReference(L"@ShellNewCommandParameters", 0x1Au, &hstringHeader, &string);
        if ( v29 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
          __debugbreak();
        }
        v27 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(__int64, __int64), HSTRING, unsigned __int8 *))(v28 + 64))(
                v18,
                string,
                &v72.Data4[1]);
        LODWORD(v18) = v27;
        if ( v27 < 0 )
        {
          v64 = 215;
          goto LABEL_88;
        }
        if ( v72.Data4[0] || (v32 = 0, v72.Data4[1]) )
          v32 = 1;
        v33 = *(_QWORD *)&v72.Data1;
        if ( *(_QWORD *)&v72.Data1 )
        {
          *(_QWORD *)&v72.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        if ( v32 )
          break;
LABEL_22:
        ;
      }
      *(_QWORD *)&v72.Data1 = 0;
      WindowsDeleteString(0);
      *(_QWORD *)&v72.Data1 = 0;
      v37 = StateRepoHelpers::LookupStringInPropertySet(
              v7,
              (struct IInspectable *)&stru_180619028,
              (const unsigned __int16 *)&v72,
              v36);
      LODWORD(v18) = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
          (const char *)(unsigned int)v37,
          (int)v65);
        goto LABEL_63;
      }
      v73 = 0;
      hstringHeader.Reserved.Reserved1 = &v73;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&v72.Data1, 0);
      LODWORD(v18) = StateRepoNewMenuCache::GetInfoForShellNewEntry(
                       (StateRepoNewMenuCache *)&hstringHeader.Reserved.Reserved2[8],
                       StringRawBuffer,
                       v20,
                       (struct IInspectable *)v7,
                       (struct NewMenuEntry **)&hstringHeader.Reserved.Reserved2[8]);
      if ( hstringHeader.Reserved.Reserved2[16] )
      {
        Reserved1 = (unsigned int)hstringHeader.Reserved.Reserved1;
        v40 = *(NewMenuEntry **)hstringHeader.Reserved.Reserved1;
        *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        if ( v40 )
          NewMenuEntry::`scalar deleting destructor'(v40, Reserved1);
      }
      if ( (int)v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
          (const char *)(unsigned int)v18,
          (int)v65);
        v57 = v73;
        v73 = 0;
        if ( v57 )
          NewMenuEntry::`scalar deleting destructor'(v57, v56);
LABEL_63:
        WindowsDeleteString(*(HSTRING *)&v72.Data1);
LABEL_64:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x205,
          (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
          (const char *)(unsigned int)v18,
          v66);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
          (const char *)(unsigned int)v18,
          v67);
        wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v75);
        goto LABEL_65;
      }
      ppwsz = (LPWSTR)WindowsGetStringRawBuffer(*(HSTRING *)&v72.Data1, 0);
      v41 = *(_QWORD *)(v21 + 16);
      if ( v41
        && (v45 = CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                    v41,
                    *(unsigned int *)(v21 + 4),
                    &ppwsz),
            *(_DWORD *)v45 == 1) )
      {
        v46 = *(NewMenuEntry **)(v45 + 16);
        v47 = WindowsGetStringRawBuffer(*(HSTRING *)&v72.Data1, 0);
        if ( StateRepoNewMenuCache::IsDefaultHandler(v48, v47, v20) )
        {
          ppwsz = (LPWSTR)v73;
          hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(*(HSTRING *)&v72.Data1, 0);
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v21,
                      0,
                      &hstringHeader,
                      &ppwsz) >= 0 )
          {
            if ( v46 )
              NewMenuEntry::`scalar deleting destructor'(v46, v43);
            goto LABEL_44;
          }
        }
      }
      else
      {
        hstringHeader.Reserved.Reserved1 = v73;
        v42 = WindowsGetStringRawBuffer(*(HSTRING *)&v72.Data1, 0);
        ppwsz = 0;
        if ( SHStrDupW(v42, &ppwsz) >= 0 )
        {
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v21,
                      1,
                      &ppwsz,
                      &hstringHeader) >= 0 )
          {
            hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(*(HSTRING *)&v72.Data1, 0);
            FileExplorerTelemetry::ShellNew_CentennialExtCached<unsigned short const *>(&hstringHeader);
LABEL_44:
            v44 = 0;
            goto LABEL_35;
          }
          CoTaskMemFree(ppwsz);
        }
      }
      v44 = v73;
LABEL_35:
      v73 = 0;
      if ( v44 )
        NewMenuEntry::`scalar deleting destructor'(v44, v43);
      WindowsDeleteString(*(HSTRING *)&v72.Data1);
      goto LABEL_22;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v18,
      (int)v65);
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v75);
    v59 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    return (unsigned int)v18;
  }
LABEL_50:
  *(_QWORD *)&v72.Data1 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
  v51 = StateRepoHelpers::LookupInPropertySet(
          (StateRepoHelpers *)this,
          (struct IInspectable *)L"FileType",
          (const unsigned __int16 *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
          &v72,
          v65);
  LODWORD(v18) = v51;
  if ( v51 < 0 )
  {
LABEL_90:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)v7,
      (const char *)(unsigned int)v51,
      (int)v65);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
LABEL_65:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v74);
    return (unsigned int)v18;
  }
  v52 = _lambda_9821f77c8078defda8eb326c50a5516d_::operator()(a3, *(_QWORD *)&v72.Data1);
  LODWORD(v18) = v52;
  if ( v52 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v52,
      (int)v65);
    v54 = *(_QWORD *)&v72.Data1;
    if ( *(_QWORD *)&v72.Data1 )
    {
      *(_QWORD *)&v72.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
    }
    v55 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    return (unsigned int)v18;
  }
  v53 = *(_QWORD *)&v72.Data1;
  if ( *(_QWORD *)&v72.Data1 )
  {
    *(_QWORD *)&v72.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
LABEL_24:
  v34 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return 0;
}

```

## disassembly

```asm
0x18007b108  mov     [rsp-8+arg_8], rbx
0x18007b10d  push    rbp
0x18007b10e  push    rsi
0x18007b10f  push    rdi
0x18007b110  push    r12
0x18007b112  push    r13
0x18007b114  push    r14
0x18007b116  push    r15
0x18007b118  lea     rbp, [rsp-27h]
0x18007b11d  sub     rsp, 0A0h
0x18007b124  mov     rax, cs:__security_cookie
0x18007b12b  xor     rax, rsp
0x18007b12e  mov     [rbp+57h+var_38], rax
0x18007b132  mov     r13, r8
0x18007b135  mov     rsi, rcx
0x18007b138  xor     r14d, r14d
0x18007b13b  mov     [rbp+57h+var_60], r14
0x18007b13f  lea     rcx, [rbp+57h+var_60]
0x18007b143  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b148  mov     [rbp+57h+var_60], r14
0x18007b14c  mov     [rbp+57h+var_68], r14
0x18007b150  mov     rax, [rsi]
0x18007b153  mov     rbx, [rax]
0x18007b156  lea     rcx, [rbp+57h+var_68]
0x18007b15a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b15f  lea     r8, [rbp+57h+var_68]
0x18007b163  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007b16a  mov     rcx, rsi
0x18007b16d  mov     rax, rbx
0x18007b170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b175  lea     r15, aOnecoreuapInte_29; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18007b17c  test    eax, eax
0x18007b17e  js      loc_18007B67A
0x18007b184  mov     [rbp+57h+var_78], r14
0x18007b188  mov     rdi, [rbp+57h+var_68]
0x18007b18c  mov     rbx, [rdi]
0x18007b18f  lea     rcx, [rbp+57h+var_78]
0x18007b193  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b198  mov     [rbp+57h+var_40], r14
0x18007b19c  mov     r14d, 8
0x18007b1a2  mov     ecx, r14d; unsigned int
0x18007b1a5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007b1aa  mov     r9d, r14d; unsigned int
0x18007b1ad  mov     r8d, eax; unsigned int
0x18007b1b0  lea     rdx, aFiletype; "FileType"
0x18007b1b7  lea     rcx, [rbp+57h+var_58]; hstringHeader
0x18007b1bb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007b1c0  nop
0x18007b1c1  lea     r8, [rbp+57h+var_78]
0x18007b1c5  mov     rdx, [rbp+57h+var_40]
0x18007b1c9  mov     rcx, rdi
0x18007b1cc  mov     rax, [rbx+30h]
0x18007b1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b1d5  nop
0x18007b1d6  xor     r14d, r14d
0x18007b1d9  test    eax, eax
0x18007b1db  js      loc_18007B5D9
0x18007b1e1  mov     rcx, [rbp+57h+var_78]
0x18007b1e5  mov     rax, [rcx]
0x18007b1e8  lea     r8, [rbp+57h+var_60]
0x18007b1ec  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18007b1f3  mov     rax, [rax]
0x18007b1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b1fb  mov     ebx, eax
0x18007b1fd  lea     ecx, [rax+7FFFBFFFh]
0x18007b203  cmp     ecx, 1
0x18007b206  ja      loc_18007B7F7
0x18007b20c  mov     rcx, [rbp+57h+var_78]
0x18007b210  test    rcx, rcx
0x18007b213  jz      short loc_18007B226
0x18007b215  mov     [rbp+57h+var_78], r14
0x18007b219  mov     rax, [rcx]
0x18007b21c  mov     rax, [rax+10h]
0x18007b220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b225  nop
0x18007b226  mov     rcx, [rbp+57h+var_68]
0x18007b22a  test    rcx, rcx
0x18007b22d  jz      short loc_18007B240
0x18007b22f  mov     [rbp+57h+var_68], r14
0x18007b233  mov     rax, [rcx]
0x18007b236  mov     rax, [rax+10h]
0x18007b23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b23f  nop
0x18007b240  test    ebx, ebx
0x18007b242  js      loc_18007B618
0x18007b248  lea     rcx, [rbp+57h+var_58]
0x18007b24c  call    ??0?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18007b251  nop
0x18007b252  mov     rdi, [rbp+57h+var_60]
0x18007b256  mov     rax, [rdi]
0x18007b259  mov     rbx, [rax+130h]
0x18007b260  lea     rcx, [rbp+57h+var_58]
0x18007b264  call    ??I?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAPEAPEAPEAUIInspectable@@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(void)
0x18007b269  mov     r8, rax
0x18007b26c  lea     rdx, [rbp+57h+hstringHeader]
0x18007b270  lea     rcx, [rbp+57h+var_58]
0x18007b274  call    ??$size_address@I@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@I@01@XZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address<uint>(void)
0x18007b279  nop
0x18007b27a  lea     rdx, [rax+8]
0x18007b27e  mov     rcx, rdi
0x18007b281  mov     rax, rbx
0x18007b284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b289  mov     ebx, eax
0x18007b28b  lea     rcx, [rbp+57h+hstringHeader]
0x18007b28f  call    ??1?$size_address_ptr@I@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<uint>::~size_address_ptr<uint>(void)
0x18007b294  test    ebx, ebx
0x18007b296  js      loc_18007B7B9
0x18007b29c  mov     edi, r14d
0x18007b29f  mov     edx, edi
0x18007b2a1  cmp     rdx, qword ptr [rbp+57h+var_58.Reserved+8]
0x18007b2a5  jnb     loc_18007B3E6
0x18007b2ab  lea     rcx, [rbp+57h+var_58]
0x18007b2af  call    ??A?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAG_K@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x18007b2b4  mov     r15, [rax]
0x18007b2b7  mov     rax, [r13+10h]
0x18007b2bb  mov     r12, [rax]
0x18007b2be  mov     rsi, [r13+8]
0x18007b2c2  mov     [rbp+57h+var_78], r14
0x18007b2c6  mov     rax, [r15]
0x18007b2c9  mov     rbx, [rax]
0x18007b2cc  lea     rcx, [rbp+57h+var_78]
0x18007b2d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007b2d5  lea     r8, [rbp+57h+var_78]
0x18007b2d9  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007b2e0  mov     rcx, r15
0x18007b2e3  mov     rax, rbx
0x18007b2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2eb  mov     ebx, eax
0x18007b2ed  test    eax, eax
0x18007b2ef  js      loc_18007B769
0x18007b2f5  mov     [rbp+57h+var_70], r14b
0x18007b2f9  mov     rbx, [rbp+57h+var_78]
0x18007b2fd  mov     r14, [rbx]
0x18007b300  mov     [rbp+57h+string], 0
0x18007b308  lea     r9, [rbp+57h+string]; string
0x18007b30c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007b310  mov     edx, 11h; length
0x18007b315  lea     rcx, sourceString; "@ShellNewFileName"
0x18007b31c  call    cs:__imp_WindowsCreateStringReference
0x18007b323  nop     dword ptr [rax+rax+00h]
0x18007b328  test    eax, eax
0x18007b32a  js      loc_18007B910
0x18007b330  lea     r8, [rbp+57h+var_70]
0x18007b334  mov     rdx, [rbp+57h+string]
0x18007b338  mov     rcx, rbx
0x18007b33b  mov     rax, [r14+40h]
0x18007b33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b344  mov     ebx, eax
0x18007b346  test    eax, eax
0x18007b348  js      loc_18007B8E9
0x18007b34e  mov     [rbp+57h+var_6F], 0
0x18007b352  mov     rbx, [rbp+57h+var_78]
0x18007b356  mov     r14, [rbx]
0x18007b359  mov     [rbp+57h+string], 0
0x18007b361  lea     r9, [rbp+57h+string]; string
0x18007b365  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007b369  mov     edx, 1Ah; length
0x18007b36e  lea     rcx, aShellnewcomman; "@ShellNewCommandParameters"
0x18007b375  call    cs:__imp_WindowsCreateStringReference
0x18007b37c  nop     dword ptr [rax+rax+00h]
0x18007b381  test    eax, eax
0x18007b383  js      loc_18007B8E1
0x18007b389  lea     r8, [rbp+57h+var_6F]
0x18007b38d  mov     rdx, [rbp+57h+string]
0x18007b391  mov     rcx, rbx
0x18007b394  mov     rax, [r14+40h]
0x18007b398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b39d  mov     ebx, eax
0x18007b39f  xor     r14d, r14d
0x18007b3a2  test    eax, eax
0x18007b3a4  js      loc_18007B8DA
0x18007b3aa  cmp     [rbp+57h+var_70], r14b
0x18007b3ae  jnz     loc_18007B54F
0x18007b3b4  cmp     [rbp+57h+var_6F], r14b
0x18007b3b8  mov     bl, r14b
0x18007b3bb  jnz     loc_18007B54F
0x18007b3c1  mov     rcx, [rbp+57h+var_78]
0x18007b3c5  test    rcx, rcx
0x18007b3c8  jz      short loc_18007B3DB
0x18007b3ca  mov     [rbp+57h+var_78], r14
0x18007b3ce  mov     rax, [rcx]
0x18007b3d1  mov     rax, [rax+10h]
0x18007b3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b3da  nop
0x18007b3db  test    bl, bl
0x18007b3dd  jnz     short loc_18007B434
0x18007b3df  inc     edi
0x18007b3e1  jmp     loc_18007B29F
0x18007b3e6  lea     rcx, [rbp+57h+var_58]
0x18007b3ea  call    ??1?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x18007b3ef  nop
0x18007b3f0  mov     rcx, [rbp+57h+var_60]
0x18007b3f4  test    rcx, rcx
0x18007b3f7  jz      short loc_18007B40A
0x18007b3f9  mov     [rbp+57h+var_60], r14
0x18007b3fd  mov     rax, [rcx]
0x18007b400  mov     rax, [rax+10h]
0x18007b404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b409  nop
0x18007b40a  xor     eax, eax
0x18007b40c  mov     rcx, [rbp+57h+var_38]
0x18007b410  xor     rcx, rsp; StackCookie
0x18007b413  call    __security_check_cookie
0x18007b418  mov     rbx, [rsp+0D0h+arg_8]
0x18007b420  add     rsp, 0A0h
0x18007b427  pop     r15
0x18007b429  pop     r14
0x18007b42b  pop     r13
0x18007b42d  pop     r12
0x18007b42f  pop     rdi
0x18007b430  pop     rsi
0x18007b431  pop     rbp
0x18007b432  retn
0x18007b434  mov     [rbp+57h+var_78], r14
0x18007b438  xor     ecx, ecx; string
0x18007b43a  call    cs:__imp_WindowsDeleteString
0x18007b441  nop     dword ptr [rax+rax+00h]
0x18007b446  mov     [rbp+57h+var_78], r14
0x18007b44a  lea     r8, [rbp+57h+var_78]; unsigned __int16 *
0x18007b44e  lea     rdx, stru_180619028; struct IInspectable *
0x18007b455  mov     rcx, r15; this
0x18007b458  call    ?LookupStringInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; StateRepoHelpers::LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x18007b45d  mov     ebx, eax
0x18007b45f  test    eax, eax
0x18007b461  js      loc_18007B8BD
0x18007b467  mov     [rbp+57h+var_68], r14
0x18007b46b  lea     rax, [rbp+57h+var_68]
0x18007b46f  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18007b473  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r14
0x18007b477  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x18007b47b  xor     edx, edx; length
0x18007b47d  mov     rcx, [rbp+57h+var_78]; string
0x18007b481  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b488  nop     dword ptr [rax+rax+00h]
0x18007b48d  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]; this
0x18007b491  mov     [rsp+0D0h+var_B0], rcx; int
0x18007b496  mov     r9, r15; struct IInspectable *
0x18007b499  mov     r8, r12; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007b49c  mov     rdx, rax; unsigned __int16 *
0x18007b49f  call    ?GetInfoForShellNewEntry@StateRepoNewMenuCache@@AEAAJPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@PEAUIInspectable@@PEAPEAUNewMenuEntry@@@Z; StateRepoNewMenuCache::GetInfoForShellNewEntry(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *,IInspectable *,NewMenuEntry * *)
0x18007b4a4  mov     ebx, eax
0x18007b4a6  cmp     byte ptr [rbp+57h+hstringHeader.Reserved+10h], r14b
0x18007b4aa  jz      short loc_18007B4C7
0x18007b4ac  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]; unsigned int
0x18007b4b0  mov     rax, [rdx]
0x18007b4b3  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18007b4b7  mov     [rdx], rcx
0x18007b4ba  test    rax, rax
0x18007b4bd  jz      short loc_18007B4C7
0x18007b4bf  mov     rcx, rax; this
0x18007b4c2  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007b4c7  test    ebx, ebx
0x18007b4c9  js      loc_18007B6E4
0x18007b4cf  xor     edx, edx; length
0x18007b4d1  mov     rcx, [rbp+57h+var_78]; string
0x18007b4d5  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b4dc  nop     dword ptr [rax+rax+00h]
0x18007b4e1  mov     [rbp+57h+ppwsz], rax
0x18007b4e5  mov     rcx, [rsi+10h]
0x18007b4e9  test    rcx, rcx
0x18007b4ec  jnz     short loc_18007B556
0x18007b4ee  mov     rax, [rbp+57h+var_68]
0x18007b4f2  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18007b4f6  xor     edx, edx; length
0x18007b4f8  mov     rcx, [rbp+57h+var_78]; string
0x18007b4fc  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b503  nop     dword ptr [rax+rax+00h]
0x18007b508  mov     [rbp+57h+ppwsz], r14
0x18007b50c  lea     rdx, [rbp+57h+ppwsz]; ppwsz
0x18007b510  mov     rcx, rax; psz
0x18007b513  call    cs:__imp_SHStrDupW
0x18007b51a  nop     dword ptr [rax+rax+00h]
0x18007b51f  test    eax, eax
0x18007b521  jns     loc_18007B86B
0x18007b527  mov     rcx, [rbp+57h+var_68]; this
0x18007b52b  mov     [rbp+57h+var_68], r14
0x18007b52f  test    rcx, rcx
0x18007b532  jz      short loc_18007B53A
0x18007b534  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007b539  nop
0x18007b53a  mov     rcx, [rbp+57h+var_78]; string
0x18007b53e  call    cs:__imp_WindowsDeleteString
0x18007b545  nop     dword ptr [rax+rax+00h]
0x18007b54a  jmp     loc_18007B3DF
0x18007b54f  mov     bl, 1
0x18007b551  jmp     loc_18007B3C1
0x18007b556  lea     r8, [rbp+57h+ppwsz]
0x18007b55a  mov     edx, [rsi+4]
0x18007b55d  call    ?s_LookupEntry@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAAEAVHashBucket@1@PEAV21@IAEBQEBG@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::HashBucket *,uint,ushort const * const &)
0x18007b562  cmp     dword ptr [rax], 1
0x18007b565  jnz     short loc_18007B4EE
0x18007b567  mov     rbx, [rax+10h]
0x18007b56b  xor     edx, edx; length
0x18007b56d  mov     rcx, [rbp+57h+var_78]; string
0x18007b571  call    cs:__imp_WindowsGetStringRawBuffer
0x18007b578  nop     dword ptr [rax+rax+00h]
0x18007b57d  mov     r8, r12; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007b580  mov     rdx, rax; unsigned __int16 *
0x18007b583  call    ?IsDefaultHandler@StateRepoNewMenuCache@@AEAA_NPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@@Z; StateRepoNewMenuCache::IsDefaultHandler(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *)
0x18007b588  test    al, al
  ... truncated ...
```
