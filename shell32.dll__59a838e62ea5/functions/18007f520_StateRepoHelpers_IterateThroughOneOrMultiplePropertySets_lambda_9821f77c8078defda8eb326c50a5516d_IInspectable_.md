# StateRepoHelpers::IterateThroughOneOrMultiplePropertySets<_lambda_9821f77c8078defda8eb326c50a5516d_>(IInspectable *,ushort const *,_lambda_9821f77c8078defda8eb326c50a5516d_ const &)

- ea: `0x18007f520`
- end: `0x18007fd1b`
- name: `??$IterateThroughOneOrMultiplePropertySets@V_lambda_9821f77c8078defda8eb326c50a5516d_@@@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGAEBV_lambda_9821f77c8078defda8eb326c50a5516d_@@@Z`
- size: `2043`
- prototype: `__int64 __fastcall(StateRepoHelpers *this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007e3f8`

## callees

- `0x18000f05c`
- `0x18003cd64`
- `0x18007eb78`
- `0x18007ee98`
- `0x18007f0e4`
- `0x18007f520`
- `0x18007fd24`
- `0x18007fd70`
- `0x18007fd9c`
- `0x18007fdc8`
- `0x1800803e4`
- `0x180080b90`
- `0x180080c24`
- `0x1801a1ecc`
- `0x180233280`
- `0x1802859e4`
- `0x1802862c8`
- `0x1802b06e4`
- `0x180317a98`
- `0x180475820`
- `0x18047585c`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fcb6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fcf0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fcb6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fcf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fc5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007fc5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f8d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f8f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f97b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007fc6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f8d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f8f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f958`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007f97b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007fc6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007faef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007f92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007faef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007f787`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f906`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f906`

## string_xrefs

- `0x18007fac6`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007fafc`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007fb45`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007fb78`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007fc8d`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007fcc2`: `shell\shell32\unicpp\statereponewmenucache.cpp`
- `0x18007f780`: `@ShellNewCommandParameters`

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
  signed int v24; // eax
  int v25; // eax
  __int64 v26; // r14
  signed int v27; // eax
  char v28; // bl
  __int64 v29; // rcx
  __int64 v30; // rcx
  HSTRING *v32; // r9
  int v33; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int Reserved1; // edx
  NewMenuEntry *v36; // rax
  __int64 v37; // rcx
  const WCHAR *v38; // rax
  unsigned int v39; // edx
  NewMenuEntry *v40; // rcx
  __int64 v41; // rax
  NewMenuEntry *v42; // rbx
  const unsigned __int16 *v43; // rax
  StateRepoNewMenuCache *v44; // rcx
  __int64 v45; // rcx
  NewMenuEntry *v46; // rcx
  int v47; // eax
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned int v52; // edx
  NewMenuEntry *v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  NewMenuEntry *v57; // rcx
  unsigned __int64 v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rdx
  void **v61; // [rsp+20h] [rbp-59h]
  int v62; // [rsp+20h] [rbp-59h]
  int v63; // [rsp+20h] [rbp-59h]
  int v64; // [rsp+20h] [rbp-59h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+48h] [rbp-31h] BYREF
  LPWSTR ppwsz; // [rsp+50h] [rbp-29h] BYREF
  struct _GUID v68; // [rsp+58h] [rbp-21h] BYREF
  NewMenuEntry *v69; // [rsp+68h] [rbp-11h] BYREF
  __int64 v70; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER v71; // [rsp+78h] [rbp-1h] BYREF
  __int64 v72; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v70 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
  v70 = 0;
  v69 = 0;
  v5 = **this;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
  v6 = v5((StateRepoHelpers *)this, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v69);
  v7 = (StateRepoHelpers *)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h";
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v6,
      (int)v61);
    goto LABEL_48;
  }
  *(_QWORD *)&v68.Data1 = 0;
  v8 = v69;
  v9 = *(_QWORD *)v69;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v72 = 0;
  v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(8u);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v71, L"FileType", v10, 8u);
  v11 = (*(__int64 (__fastcall **)(NewMenuEntry *, __int64, struct _GUID *))(v9 + 48))(v8, v72, &v68);
  if ( v11 < 0 )
  {
    if ( v11 != -2147483637 )
    {
      v58 = (unsigned int)v11;
      v59 = 47;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v59,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
        (const char *)v58,
        (int)v61);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      goto LABEL_50;
    }
    v45 = *(_QWORD *)&v68.Data1;
    if ( *(_QWORD *)&v68.Data1 )
    {
      *(_QWORD *)&v68.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
LABEL_48:
    v46 = v69;
    if ( v69 )
    {
      v69 = 0;
      (*(void (__fastcall **)(NewMenuEntry *))(*(_QWORD *)v46 + 16LL))(v46);
    }
    goto LABEL_50;
  }
  v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v68.Data1)(
          *(_QWORD *)&v68.Data1,
          &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
          &v70);
  if ( (unsigned int)(v12 + 2147467263) > 1 )
  {
    if ( v12 >= 0 )
    {
      v56 = *(_QWORD *)&v68.Data1;
      if ( *(_QWORD *)&v68.Data1 )
      {
        *(_QWORD *)&v68.Data1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v57 = v69;
      if ( v69 )
      {
        v69 = 0;
        (*(void (__fastcall **)(NewMenuEntry *))(*(_QWORD *)v57 + 16LL))(v57);
      }
      goto LABEL_9;
    }
    v58 = (unsigned int)v12;
    v59 = 50;
    goto LABEL_80;
  }
  v13 = *(_QWORD *)&v68.Data1;
  if ( *(_QWORD *)&v68.Data1 )
  {
    *(_QWORD *)&v68.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(NewMenuEntry *))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( v12 >= 0 )
  {
LABEL_9:
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(&v71);
    v15 = v70;
    v18 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 304LL);
    v16 = wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(&v71);
    v17 = wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned int>(
            &v71,
            &hstringHeader,
            v16);
    LODWORD(v18) = v18(v15, v17 + 8);
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned int>::~size_address_ptr<unsigned int>(&hstringHeader);
    if ( (int)v18 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( (unsigned __int64)i >= *(_QWORD *)&v71.Reserved.Reserved2[8] )
        {
          wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v71);
          goto LABEL_24;
        }
        v7 = *(StateRepoHelpers **)wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](&v71);
        v20 = **(struct Windows::Internal::StateRepository::IFileTypeAssociation ***)(a3 + 16);
        v21 = *(_QWORD *)(a3 + 8);
        *(_QWORD *)&v68.Data1 = 0;
        v18 = **(__int64 (__fastcall ***)(__int64, __int64))v7;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
        v22 = ((__int64 (__fastcall *)(StateRepoHelpers *, GUID *, struct _GUID *))v18)(
                v7,
                &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca,
                &v68);
        LODWORD(v18) = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD0,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)(unsigned int)v22,
            (int)v61);
          v54 = *(_QWORD *)&v68.Data1;
          if ( *(_QWORD *)&v68.Data1 )
          {
            *(_QWORD *)&v68.Data1 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
          }
LABEL_68:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)(unsigned int)v18,
            v64);
          goto LABEL_64;
        }
        v68.Data4[0] = 0;
        v18 = *(__int64 (__fastcall **)(__int64, __int64))&v68.Data1;
        v23 = **(_QWORD **)&v68.Data1;
        string = 0;
        v24 = WindowsCreateStringReference(L"@ShellNewFileName", 0x11u, &hstringHeader, &string);
        if ( v24 < 0 )
        {
          RaiseException(v24, 1u, 0, 0);
          goto LABEL_90;
        }
        v25 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(__int64, __int64), HSTRING, unsigned __int8 *))(v23 + 64))(
                v18,
                string,
                v68.Data4);
        LODWORD(v18) = v25;
        if ( v25 < 0 )
        {
          v60 = 213;
LABEL_88:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v60,
            (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
            (const char *)(unsigned int)v25,
            (int)v61);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
          goto LABEL_68;
        }
        v68.Data4[1] = 0;
        v18 = *(__int64 (__fastcall **)(__int64, __int64))&v68.Data1;
        v26 = **(_QWORD **)&v68.Data1;
        string = 0;
        v27 = WindowsCreateStringReference(L"@ShellNewCommandParameters", 0x1Au, &hstringHeader, &string);
        if ( v27 < 0 )
        {
          RaiseException(v27, 1u, 0, 0);
          __debugbreak();
        }
        v25 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(__int64, __int64), HSTRING, unsigned __int8 *))(v26 + 64))(
                v18,
                string,
                &v68.Data4[1]);
        LODWORD(v18) = v25;
        if ( v25 < 0 )
        {
          v60 = 215;
          goto LABEL_88;
        }
        if ( v68.Data4[0] || (v28 = 0, v68.Data4[1]) )
          v28 = 1;
        v29 = *(_QWORD *)&v68.Data1;
        if ( *(_QWORD *)&v68.Data1 )
        {
          *(_QWORD *)&v68.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        if ( v28 )
          break;
LABEL_22:
        ;
      }
      *(_QWORD *)&v68.Data1 = 0;
      WindowsDeleteString(0);
      *(_QWORD *)&v68.Data1 = 0;
      v33 = StateRepoHelpers::LookupStringInPropertySet(
              v7,
              (struct IInspectable *)&stru_1805D8078,
              (const unsigned __int16 *)&v68,
              v32);
      LODWORD(v18) = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
          (const char *)(unsigned int)v33,
          (int)v61);
        goto LABEL_63;
      }
      v69 = 0;
      hstringHeader.Reserved.Reserved1 = &v69;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&v68.Data1, 0);
      LODWORD(v18) = StateRepoNewMenuCache::GetInfoForShellNewEntry(
                       (StateRepoNewMenuCache *)&hstringHeader.Reserved.Reserved2[8],
                       StringRawBuffer,
                       v20,
                       (struct IInspectable *)v7,
                       (struct NewMenuEntry **)&hstringHeader.Reserved.Reserved2[8]);
      if ( hstringHeader.Reserved.Reserved2[16] )
      {
        Reserved1 = (unsigned int)hstringHeader.Reserved.Reserved1;
        v36 = *(NewMenuEntry **)hstringHeader.Reserved.Reserved1;
        *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
        if ( v36 )
          NewMenuEntry::`scalar deleting destructor'(v36, Reserved1);
      }
      if ( (int)v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CE,
          (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
          (const char *)(unsigned int)v18,
          (int)v61);
        v53 = v69;
        v69 = 0;
        if ( v53 )
          NewMenuEntry::`scalar deleting destructor'(v53, v52);
LABEL_63:
        WindowsDeleteString(*(HSTRING *)&v68.Data1);
LABEL_64:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x205,
          (unsigned int)"shell\\shell32\\unicpp\\statereponewmenucache.cpp",
          (const char *)(unsigned int)v18,
          v62);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
          (const char *)(unsigned int)v18,
          v63);
        wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v71);
        goto LABEL_65;
      }
      ppwsz = (LPWSTR)WindowsGetStringRawBuffer(*(HSTRING *)&v68.Data1, 0);
      v37 = *(_QWORD *)(v21 + 16);
      if ( v37
        && (v41 = CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(
                    v37,
                    *(unsigned int *)(v21 + 4),
                    &ppwsz),
            *(_DWORD *)v41 == 1) )
      {
        v42 = *(NewMenuEntry **)(v41 + 16);
        v43 = WindowsGetStringRawBuffer(*(HSTRING *)&v68.Data1, 0);
        if ( StateRepoNewMenuCache::IsDefaultHandler(v44, v43, v20) )
        {
          ppwsz = (LPWSTR)v69;
          hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(*(HSTRING *)&v68.Data1, 0);
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v21,
                      0,
                      &hstringHeader,
                      &ppwsz) >= 0 )
          {
            if ( v42 )
              NewMenuEntry::`scalar deleting destructor'(v42, v39);
            goto LABEL_44;
          }
        }
      }
      else
      {
        hstringHeader.Reserved.Reserved1 = v69;
        v38 = WindowsGetStringRawBuffer(*(HSTRING *)&v68.Data1, 0);
        ppwsz = 0;
        if ( SHStrDupW(v38, &ppwsz) >= 0 )
        {
          if ( (int)CSimpleHashTable<unsigned short const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                      v21,
                      1,
                      &ppwsz,
                      &hstringHeader) >= 0 )
          {
            hstringHeader.Reserved.Reserved1 = (PVOID)WindowsGetStringRawBuffer(*(HSTRING *)&v68.Data1, 0);
            FileExplorerTelemetry::ShellNew_CentennialExtCached<unsigned short const *>(&hstringHeader);
LABEL_44:
            v40 = 0;
            goto LABEL_35;
          }
          CoTaskMemFree(ppwsz);
        }
      }
      v40 = v69;
LABEL_35:
      v69 = 0;
      if ( v40 )
        NewMenuEntry::`scalar deleting destructor'(v40, v39);
      WindowsDeleteString(*(HSTRING *)&v68.Data1);
      goto LABEL_22;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v18,
      (int)v61);
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(&v71);
    v55 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    }
    return (unsigned int)v18;
  }
LABEL_50:
  *(_QWORD *)&v68.Data1 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
  v47 = StateRepoHelpers::LookupInPropertySet(
          (StateRepoHelpers *)this,
          (struct IInspectable *)L"FileType",
          (const unsigned __int16 *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
          &v68,
          v61);
  LODWORD(v18) = v47;
  if ( v47 < 0 )
  {
LABEL_90:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)v7,
      (const char *)(unsigned int)v47,
      (int)v61);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v68);
LABEL_65:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
    return (unsigned int)v18;
  }
  v48 = _lambda_9821f77c8078defda8eb326c50a5516d_::operator()(a3, *(_QWORD *)&v68.Data1);
  LODWORD(v18) = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateRepoUtil.h",
      (const char *)(unsigned int)v48,
      (int)v61);
    v50 = *(_QWORD *)&v68.Data1;
    if ( *(_QWORD *)&v68.Data1 )
    {
      *(_QWORD *)&v68.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    return (unsigned int)v18;
  }
  v49 = *(_QWORD *)&v68.Data1;
  if ( *(_QWORD *)&v68.Data1 )
  {
    *(_QWORD *)&v68.Data1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  }
LABEL_24:
  v30 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return 0;
}

```

## disassembly

```asm
0x18007f520  mov     [rsp-8+arg_8], rbx
0x18007f525  push    rbp
0x18007f526  push    rsi
0x18007f527  push    rdi
0x18007f528  push    r12
0x18007f52a  push    r13
0x18007f52c  push    r14
0x18007f52e  push    r15
0x18007f530  lea     rbp, [rsp-27h]
0x18007f535  sub     rsp, 0A0h
0x18007f53c  mov     rax, cs:__security_cookie
0x18007f543  xor     rax, rsp
0x18007f546  mov     [rbp+57h+var_38], rax
0x18007f54a  mov     r13, r8
0x18007f54d  mov     rsi, rcx
0x18007f550  xor     r14d, r14d
0x18007f553  mov     [rbp+57h+var_60], r14
0x18007f557  lea     rcx, [rbp+57h+var_60]
0x18007f55b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f560  mov     [rbp+57h+var_60], r14
0x18007f564  mov     [rbp+57h+var_68], r14
0x18007f568  mov     rax, [rsi]
0x18007f56b  mov     rbx, [rax]
0x18007f56e  lea     rcx, [rbp+57h+var_68]
0x18007f572  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f577  lea     r8, [rbp+57h+var_68]
0x18007f57b  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007f582  mov     rcx, rsi
0x18007f585  mov     rax, rbx
0x18007f588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f58d  lea     r15, aOnecoreuapInte_29; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18007f594  test    eax, eax
0x18007f596  js      loc_18007FA55
0x18007f59c  mov     [rbp+57h+var_78], r14
0x18007f5a0  mov     rdi, [rbp+57h+var_68]
0x18007f5a4  mov     rbx, [rdi]
0x18007f5a7  lea     rcx, [rbp+57h+var_78]
0x18007f5ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f5b0  mov     [rbp+57h+var_40], r14
0x18007f5b4  mov     r14d, 8
0x18007f5ba  mov     ecx, r14d; unsigned int
0x18007f5bd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007f5c2  mov     r9d, r14d; unsigned int
0x18007f5c5  mov     r8d, eax; unsigned int
0x18007f5c8  lea     rdx, aFiletype; "FileType"
0x18007f5cf  lea     rcx, [rbp+57h+var_58]; hstringHeader
0x18007f5d3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007f5d8  nop
0x18007f5d9  lea     r8, [rbp+57h+var_78]
0x18007f5dd  mov     rdx, [rbp+57h+var_40]
0x18007f5e1  mov     rcx, rdi
0x18007f5e4  mov     rax, [rbx+30h]
0x18007f5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f5ed  nop
0x18007f5ee  xor     r14d, r14d
0x18007f5f1  test    eax, eax
0x18007f5f3  js      loc_18007F9B4
0x18007f5f9  mov     rcx, [rbp+57h+var_78]
0x18007f5fd  mov     rax, [rcx]
0x18007f600  lea     r8, [rbp+57h+var_60]
0x18007f604  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18007f60b  mov     rax, [rax]
0x18007f60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f613  mov     ebx, eax
0x18007f615  lea     ecx, [rax+7FFFBFFFh]
0x18007f61b  cmp     ecx, 1
0x18007f61e  ja      loc_18007FBCC
0x18007f624  mov     rcx, [rbp+57h+var_78]
0x18007f628  test    rcx, rcx
0x18007f62b  jz      short loc_18007F63E
0x18007f62d  mov     [rbp+57h+var_78], r14
0x18007f631  mov     rax, [rcx]
0x18007f634  mov     rax, [rax+10h]
0x18007f638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f63d  nop
0x18007f63e  mov     rcx, [rbp+57h+var_68]
0x18007f642  test    rcx, rcx
0x18007f645  jz      short loc_18007F658
0x18007f647  mov     [rbp+57h+var_68], r14
0x18007f64b  mov     rax, [rcx]
0x18007f64e  mov     rax, [rax+10h]
0x18007f652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f657  nop
0x18007f658  test    ebx, ebx
0x18007f65a  js      loc_18007F9F3
0x18007f660  lea     rcx, [rbp+57h+var_58]
0x18007f664  call    ??0?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)
0x18007f669  nop
0x18007f66a  mov     rdi, [rbp+57h+var_60]
0x18007f66e  mov     rax, [rdi]
0x18007f671  mov     rbx, [rax+130h]
0x18007f678  lea     rcx, [rbp+57h+var_58]
0x18007f67c  call    ??I?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAPEAPEAPEAUIInspectable@@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::operator&(void)
0x18007f681  mov     r8, rax
0x18007f684  lea     rdx, [rbp+57h+hstringHeader]
0x18007f688  lea     rcx, [rbp+57h+var_58]
0x18007f68c  call    ??$size_address@I@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@I@01@XZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address<uint>(void)
0x18007f691  nop
0x18007f692  lea     rdx, [rax+8]
0x18007f696  mov     rcx, rdi
0x18007f699  mov     rax, rbx
0x18007f69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f6a1  mov     ebx, eax
0x18007f6a3  lea     rcx, [rbp+57h+hstringHeader]
0x18007f6a7  call    ??1?$size_address_ptr@I@?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<uint>::~size_address_ptr<uint>(void)
0x18007f6ac  test    ebx, ebx
0x18007f6ae  js      loc_18007FB8E
0x18007f6b4  mov     edi, r14d
0x18007f6b7  mov     edx, edi
0x18007f6b9  cmp     rdx, qword ptr [rbp+57h+var_58.Reserved+8]
0x18007f6bd  jnb     loc_18007F7F2
0x18007f6c3  lea     rcx, [rbp+57h+var_58]
0x18007f6c7  call    ??A?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAAEAPEAG_K@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::operator[](unsigned __int64)
0x18007f6cc  mov     r15, [rax]
0x18007f6cf  mov     rax, [r13+10h]
0x18007f6d3  mov     r12, [rax]
0x18007f6d6  mov     rsi, [r13+8]
0x18007f6da  mov     [rbp+57h+var_78], r14
0x18007f6de  mov     rax, [r15]
0x18007f6e1  mov     rbx, [rax]
0x18007f6e4  lea     rcx, [rbp+57h+var_78]
0x18007f6e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007f6ed  lea     r8, [rbp+57h+var_78]
0x18007f6f1  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18007f6f8  mov     rcx, r15
0x18007f6fb  mov     rax, rbx
0x18007f6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f703  mov     ebx, eax
0x18007f705  test    eax, eax
0x18007f707  js      loc_18007FB3E
0x18007f70d  mov     [rbp+57h+var_70], r14b
0x18007f711  mov     rbx, [rbp+57h+var_78]
0x18007f715  mov     r14, [rbx]
0x18007f718  mov     [rbp+57h+string], 0
0x18007f720  lea     r9, [rbp+57h+string]; string
0x18007f724  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007f728  mov     edx, 11h; length
0x18007f72d  lea     rcx, sourceString; "@ShellNewFileName"
0x18007f734  call    cs:__imp_WindowsCreateStringReference
0x18007f73a  test    eax, eax
0x18007f73c  js      loc_18007FCE4
0x18007f742  lea     r8, [rbp+57h+var_70]
0x18007f746  mov     rdx, [rbp+57h+string]
0x18007f74a  mov     rcx, rbx
0x18007f74d  mov     rax, [r14+40h]
0x18007f751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f756  mov     ebx, eax
0x18007f758  test    eax, eax
0x18007f75a  js      loc_18007FCBD
0x18007f760  mov     [rbp+57h+var_6F], 0
0x18007f764  mov     rbx, [rbp+57h+var_78]
0x18007f768  mov     r14, [rbx]
0x18007f76b  mov     [rbp+57h+string], 0
0x18007f773  lea     r9, [rbp+57h+string]; string
0x18007f777  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18007f77b  mov     edx, 1Ah; length
0x18007f780  lea     rcx, aShellnewcomman; "@ShellNewCommandParameters"
0x18007f787  call    cs:__imp_WindowsCreateStringReference
0x18007f78d  test    eax, eax
0x18007f78f  js      loc_18007FCAA
0x18007f795  lea     r8, [rbp+57h+var_6F]
0x18007f799  mov     rdx, [rbp+57h+string]
0x18007f79d  mov     rcx, rbx
0x18007f7a0  mov     rax, [r14+40h]
0x18007f7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f7a9  mov     ebx, eax
0x18007f7ab  xor     r14d, r14d
0x18007f7ae  test    eax, eax
0x18007f7b0  js      loc_18007FCA3
0x18007f7b6  cmp     [rbp+57h+var_70], r14b
0x18007f7ba  jnz     loc_18007F936
0x18007f7c0  cmp     [rbp+57h+var_6F], r14b
0x18007f7c4  mov     bl, r14b
0x18007f7c7  jnz     loc_18007F936
0x18007f7cd  mov     rcx, [rbp+57h+var_78]
0x18007f7d1  test    rcx, rcx
0x18007f7d4  jz      short loc_18007F7E7
0x18007f7d6  mov     [rbp+57h+var_78], r14
0x18007f7da  mov     rax, [rcx]
0x18007f7dd  mov     rax, [rax+10h]
0x18007f7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f7e6  nop
0x18007f7e7  test    bl, bl
0x18007f7e9  jnz     short loc_18007F83F
0x18007f7eb  inc     edi
0x18007f7ed  jmp     loc_18007F6B7
0x18007f7f2  lea     rcx, [rbp+57h+var_58]
0x18007f7f6  call    ??1?$unique_any_array_ptr@PEAUIInspectable@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::~unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>(void)
0x18007f7fb  nop
0x18007f7fc  mov     rcx, [rbp+57h+var_60]
0x18007f800  test    rcx, rcx
0x18007f803  jz      short loc_18007F816
0x18007f805  mov     [rbp+57h+var_60], r14
0x18007f809  mov     rax, [rcx]
0x18007f80c  mov     rax, [rax+10h]
0x18007f810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f815  nop
0x18007f816  xor     eax, eax
0x18007f818  mov     rcx, [rbp+57h+var_38]
0x18007f81c  xor     rcx, rsp; StackCookie
0x18007f81f  call    __security_check_cookie
0x18007f824  mov     rbx, [rsp+0D0h+arg_8]
0x18007f82c  add     rsp, 0A0h
0x18007f833  pop     r15
0x18007f835  pop     r14
0x18007f837  pop     r13
0x18007f839  pop     r12
0x18007f83b  pop     rdi
0x18007f83c  pop     rsi
0x18007f83d  pop     rbp
0x18007f83e  retn
0x18007f83f  mov     [rbp+57h+var_78], r14
0x18007f843  xor     ecx, ecx; string
0x18007f845  call    cs:__imp_WindowsDeleteString
0x18007f84b  mov     [rbp+57h+var_78], r14
0x18007f84f  lea     r8, [rbp+57h+var_78]; unsigned __int16 *
0x18007f853  lea     rdx, stru_1805D8078; struct IInspectable *
0x18007f85a  mov     rcx, r15; this
0x18007f85d  call    ?LookupStringInPropertySet@StateRepoHelpers@@YAJPEAUIInspectable@@PEBGPEAPEAUHSTRING__@@@Z; StateRepoHelpers::LookupStringInPropertySet(IInspectable *,ushort const *,HSTRING__ * *)
0x18007f862  mov     ebx, eax
0x18007f864  test    eax, eax
0x18007f866  js      loc_18007FC86
0x18007f86c  mov     [rbp+57h+var_68], r14
0x18007f870  lea     rax, [rbp+57h+var_68]
0x18007f874  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18007f878  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r14
0x18007f87c  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x18007f880  xor     edx, edx; length
0x18007f882  mov     rcx, [rbp+57h+var_78]; string
0x18007f886  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f88c  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]; this
0x18007f890  mov     [rsp+0D0h+var_B0], rcx; int
0x18007f895  mov     r9, r15; struct IInspectable *
0x18007f898  mov     r8, r12; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007f89b  mov     rdx, rax; unsigned __int16 *
0x18007f89e  call    ?GetInfoForShellNewEntry@StateRepoNewMenuCache@@AEAAJPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@PEAUIInspectable@@PEAPEAUNewMenuEntry@@@Z; StateRepoNewMenuCache::GetInfoForShellNewEntry(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *,IInspectable *,NewMenuEntry * *)
0x18007f8a3  mov     ebx, eax
0x18007f8a5  cmp     byte ptr [rbp+57h+hstringHeader.Reserved+10h], r14b
0x18007f8a9  jz      short loc_18007F8C6
0x18007f8ab  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]; unsigned int
0x18007f8af  mov     rax, [rdx]
0x18007f8b2  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18007f8b6  mov     [rdx], rcx
0x18007f8b9  test    rax, rax
0x18007f8bc  jz      short loc_18007F8C6
0x18007f8be  mov     rcx, rax; this
0x18007f8c1  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007f8c6  test    ebx, ebx
0x18007f8c8  js      loc_18007FABF
0x18007f8ce  xor     edx, edx; length
0x18007f8d0  mov     rcx, [rbp+57h+var_78]; string
0x18007f8d4  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f8da  mov     [rbp+57h+ppwsz], rax
0x18007f8de  mov     rcx, [rsi+10h]
0x18007f8e2  test    rcx, rcx
0x18007f8e5  jnz     short loc_18007F93D
0x18007f8e7  mov     rax, [rbp+57h+var_68]
0x18007f8eb  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18007f8ef  xor     edx, edx; length
0x18007f8f1  mov     rcx, [rbp+57h+var_78]; string
0x18007f8f5  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f8fb  mov     [rbp+57h+ppwsz], r14
0x18007f8ff  lea     rdx, [rbp+57h+ppwsz]; ppwsz
0x18007f903  mov     rcx, rax; psz
0x18007f906  call    cs:__imp_SHStrDupW
0x18007f90c  test    eax, eax
0x18007f90e  jns     loc_18007FC40
0x18007f914  mov     rcx, [rbp+57h+var_68]; this
0x18007f918  mov     [rbp+57h+var_68], r14
0x18007f91c  test    rcx, rcx
0x18007f91f  jz      short loc_18007F927
0x18007f921  call    ??_GNewMenuEntry@@QEAAPEAXI@Z; NewMenuEntry::`scalar deleting destructor'(uint)
0x18007f926  nop
0x18007f927  mov     rcx, [rbp+57h+var_78]; string
0x18007f92b  call    cs:__imp_WindowsDeleteString
0x18007f931  jmp     loc_18007F7EB
0x18007f936  mov     bl, 1
0x18007f938  jmp     loc_18007F7CD
0x18007f93d  lea     r8, [rbp+57h+ppwsz]
0x18007f941  mov     edx, [rsi+4]
0x18007f944  call    ?s_LookupEntry@?$CSimpleHashTable@PEBGPEAUNewMenuEntry@@VCCaseInsensitiveStringHashPolicy@@VCCaseInsensitiveStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAAEAVHashBucket@1@PEAV21@IAEBQEBG@Z; CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::s_LookupEntry(CSimpleHashTable<ushort const *,NewMenuEntry *,CCaseInsensitiveStringHashPolicy,CCaseInsensitiveStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::HashBucket *,uint,ushort const * const &)
0x18007f949  cmp     dword ptr [rax], 1
0x18007f94c  jnz     short loc_18007F8E7
0x18007f94e  mov     rbx, [rax+10h]
0x18007f952  xor     edx, edx; length
0x18007f954  mov     rcx, [rbp+57h+var_78]; string
0x18007f958  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f95e  mov     r8, r12; struct Windows::Internal::StateRepository::IFileTypeAssociation *
0x18007f961  mov     rdx, rax; unsigned __int16 *
0x18007f964  call    ?IsDefaultHandler@StateRepoNewMenuCache@@AEAA_NPEBGPEAUIFileTypeAssociation@StateRepository@Internal@Windows@@@Z; StateRepoNewMenuCache::IsDefaultHandler(ushort const *,Windows::Internal::StateRepository::IFileTypeAssociation *)
0x18007f969  test    al, al
0x18007f96b  jz      short loc_18007F914
0x18007f96d  mov     rax, [rbp+57h+var_68]
0x18007f971  mov     [rbp+57h+ppwsz], rax
0x18007f975  xor     edx, edx; length
0x18007f977  mov     rcx, [rbp+57h+var_78]; string
0x18007f97b  call    cs:__imp_WindowsGetStringRawBuffer
0x18007f981  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18007f985  lea     r9, [rbp+57h+ppwsz]
0x18007f989  lea     r8, [rbp+57h+hstringHeader]
  ... truncated ...
```
