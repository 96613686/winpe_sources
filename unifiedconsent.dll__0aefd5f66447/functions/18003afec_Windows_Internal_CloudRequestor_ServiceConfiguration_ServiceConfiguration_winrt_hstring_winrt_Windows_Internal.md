# Windows::Internal::CloudRequestor::ServiceConfiguration::ServiceConfiguration(winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig)

- ea: `0x18003afec`
- end: `0x18003b720`
- name: `??0ServiceConfiguration@CloudRequestor@Internal@Windows@@QEAA@Uhstring@winrt@@UEnvironmentConfig@1235@@Z`
- size: `1844`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bd18`

## callees

- `0x180002840`
- `0x180002884`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000e4a4`
- `0x18000ed24`
- `0x180014364`
- `0x180016438`
- `0x180016a58`
- `0x180016d38`
- `0x18001c1d4`
- `0x1800325a8`
- `0x180038674`
- `0x18003a904`
- `0x18003ad5c`
- `0x18003aea4`
- `0x18003afec`
- `0x18003b838`
- `0x18006cd78`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b156`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b161`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b22b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b236`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b504`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b513`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b66f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b67e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b689`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b694`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b156`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b161`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b22b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b236`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b504`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b513`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b66f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b67e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b689`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003b694`

## string_xrefs

- `0x18003b6a1`: `onecoreuap\shell\clouddirect\cloudrequestor\src\serviceconfiguration.cpp`
- `0x18003b6b9`: `onecoreuap\shell\clouddirect\cloudrequestor\src\serviceconfiguration.cpp`
- `0x18003b6d1`: `onecoreuap\shell\clouddirect\cloudrequestor\src\serviceconfiguration.cpp`
- `0x18003b6e9`: `onecoreuap\shell\clouddirect\cloudrequestor\src\serviceconfiguration.cpp`
- `0x18003b701`: `onecoreuap\shell\clouddirect\cloudrequestor\src\serviceconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall Windows::Internal::CloudRequestor::ServiceConfiguration::ServiceConfiguration(
        _QWORD *a1,
        volatile signed __int32 **a2,
        __int64 *a3)
{
  __int64 *v6; // r15
  char v7; // al
  _QWORD *v8; // rax
  int v9; // ebx
  __int64 *v10; // rax
  __int64 v11; // rcx
  char v12; // al
  void *v13; // r14
  int v14; // eax
  HANDLE ProcessHeap; // rax
  void *v16; // r14
  int v17; // eax
  HANDLE v18; // rax
  _QWORD *v19; // rax
  int v20; // ebx
  __int64 v21; // rax
  void *v23; // r14
  int v24; // eax
  HANDLE v25; // rax
  void *v26; // r14
  int v27; // eax
  HANDLE v28; // rax
  _QWORD *v29; // rax
  int v30; // ebx
  __int64 v31; // rax
  void *v33; // r14
  int v34; // eax
  HANDLE v35; // rax
  void *v36; // rbx
  int v37; // eax
  HANDLE v38; // rax
  __int64 *ObjectW; // rax
  __int64 v40; // rcx
  int v41; // eax
  __int64 *v42; // r14
  __int64 v43; // rax
  __int64 *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rcx
  _QWORD *v47; // rax
  void **v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rax
  _QWORD *v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rbx
  void *v55; // rbx
  int v56; // eax
  HANDLE v57; // rax
  void *v58; // rbx
  int v59; // eax
  HANDLE v60; // rax
  void *v61; // rbx
  int v62; // eax
  HANDLE v63; // rax
  volatile signed __int32 *v64; // rbx
  int v65; // edi
  HANDLE v66; // rax
  LPVOID lpMem; // [rsp+28h] [rbp-E0h] BYREF
  LPVOID v69; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v70; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v71[2]; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v72[2]; // [rsp+50h] [rbp-B8h] BYREF
  void *v73; // [rsp+60h] [rbp-A8h] BYREF
  void *v74; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v75; // [rsp+70h] [rbp-98h]
  int v76; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v77[2]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v78; // [rsp+98h] [rbp-70h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-60h]
  __int64 v80; // [rsp+B0h] [rbp-58h]
  __int64 v81; // [rsp+B8h] [rbp-50h]
  int v82; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v83[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v84; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v85; // [rsp+E8h] [rbp-20h]
  __int64 v86; // [rsp+F0h] [rbp-18h]
  __int64 v87; // [rsp+F8h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]
  LPVOID v89; // [rsp+170h] [rbp+68h] BYREF

  LODWORD(v89) = 0;
  *a1 = &Windows::Internal::CloudRequestor::ServiceConfiguration::`vftable';
  v6 = a1 + 1;
  a1[1] = 0;
  if ( !*a2 || (v7 = 0, !*((_DWORD *)*a2 + 1)) )
    v7 = 1;
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\serviceconfiguration.cpp",
      (const char *)0x80070057LL,
      (int)lpMem);
  v8 = (_QWORD *)winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
                   a3,
                   &v69);
  v9 = 1;
  LODWORD(v89) = 1;
  if ( !*v8
    || (v10 = (__int64 *)winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
                           a3,
                           &lpMem),
        v9 = 3,
        LODWORD(v89) = 3,
        (v11 = *v10) == 0)
    || (v12 = 0, !*(_DWORD *)(v11 + 4)) )
  {
    v12 = 1;
  }
  if ( v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\serviceconfiguration.cpp",
      (const char *)0x80070057LL,
      (int)lpMem);
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    v13 = lpMem;
    if ( lpMem )
    {
      v14 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v14 )
      {
        if ( v14 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
      }
      lpMem = 0;
    }
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    v16 = v69;
    if ( v69 )
    {
      v17 = _InterlockedDecrement((volatile signed __int32 *)v69 + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          abort();
      }
      else
      {
        v18 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v18, 0, v16);
      }
    }
  }
  v19 = (_QWORD *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
                    a3,
                    &v69);
  v20 = v9 | 4;
  LODWORD(v89) = v20;
  if ( !*v19
    || (v21 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
                a3,
                &lpMem),
        v20 |= 8u,
        LODWORD(v89) = v20,
        !*(_QWORD *)v21)
    || !*(_DWORD *)(*(_QWORD *)v21 + 4LL) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\serviceconfiguration.cpp",
      (const char *)0x80070057LL,
      (int)lpMem);
  }
  if ( (v20 & 8) != 0 )
  {
    v20 &= ~8u;
    v23 = lpMem;
    if ( lpMem )
    {
      v24 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v24 )
      {
        if ( v24 < 0 )
          abort();
      }
      else
      {
        v25 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v25, 0, v23);
      }
      lpMem = 0;
    }
  }
  if ( (v20 & 4) != 0 )
  {
    v20 &= ~4u;
    v26 = v69;
    if ( v69 )
    {
      v27 = _InterlockedDecrement((volatile signed __int32 *)v69 + 6);
      if ( v27 )
      {
        if ( v27 < 0 )
          abort();
      }
      else
      {
        v28 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v28, 0, v26);
      }
    }
  }
  v29 = (_QWORD *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
                    a3,
                    &v69);
  v30 = v20 | 0x10;
  LODWORD(v89) = v30;
  if ( !*v29
    || (v31 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
                a3,
                &lpMem),
        v30 |= 0x20u,
        LODWORD(v89) = v30,
        !*(_QWORD *)v31)
    || !*(_DWORD *)(*(_QWORD *)v31 + 4LL) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\serviceconfiguration.cpp",
      (const char *)0x80070057LL,
      (int)lpMem);
  }
  if ( (v30 & 0x20) != 0 )
  {
    LOBYTE(v30) = v30 & 0xDF;
    v33 = lpMem;
    if ( lpMem )
    {
      v34 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v34 )
      {
        if ( v34 < 0 )
          abort();
      }
      else
      {
        v35 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v35, 0, v33);
      }
      lpMem = 0;
    }
  }
  if ( (v30 & 0x10) != 0 )
  {
    v36 = v69;
    if ( v69 )
    {
      v37 = _InterlockedDecrement((volatile signed __int32 *)v69 + 6);
      if ( v37 )
      {
        if ( v37 < 0 )
          abort();
      }
      else
      {
        v38 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v38, 0, v36);
      }
    }
  }
  ObjectW = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
                         a3,
                         &lpMem);
  LODWORD(v89) = 0;
  v40 = *ObjectW;
  LODWORD(v74) = 0;
  v75 = 0;
  v41 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 56LL))(v40, &v89);
  if ( v41 < 0 )
    winrt::throw_hresult((unsigned int)v41, &v74);
  if ( !(_DWORD)v89 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\serviceconfiguration.cpp",
      (const char *)0x80070057LL,
      (int)lpMem);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  v42 = (__int64 *)StringToLower(&v69, a2);
  v43 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
          a3,
          &lpMem);
  v44 = (__int64 *)StringToLower(&v89, v43);
  v45 = *v44;
  *v44 = 0;
  v72[0] = v45;
  v46 = *a3;
  v72[1] = v46;
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
  v82 = 0;
  v83[0] = 0;
  v83[1] = 0;
  v47 = operator new(0x20u);
  *v47 = v47;
  v47[1] = v47;
  v83[0] = v47;
  v84 = 0;
  v85 = 0;
  v86 = 7;
  v87 = 8;
  v82 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(
    &v84,
    16,
    v47);
  v48 = (void **)v72;
  do
  {
    std::_Hash<std::_Umap_traits<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>,0>>::emplace<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>> const &>(
      &v82,
      &v74,
      v48);
    v48 += 2;
  }
  while ( v48 != &v73 );
  v73 = operator new(0x78u);
  v49 = winrt::impl::heap_implements<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::heap_implements<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>(
          v73,
          &v82);
  v50 = *v42;
  *v42 = 0;
  v71[0] = v50;
  v73 = 0;
  v71[1] = (v49 + 16) & -(__int64)(v49 != 0);
  v76 = 0;
  v77[0] = 0;
  v77[1] = 0;
  v51 = operator new(0x20u);
  *v51 = v51;
  v51[1] = v51;
  v77[0] = v51;
  v78 = 0;
  v79 = 0;
  v80 = 7;
  v81 = 8;
  v76 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(
    &v78,
    16,
    v51);
  v52 = v71;
  do
  {
    std::_Hash<std::_Umap_traits<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>,0>>::emplace<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>> const &>(
      &v76,
      &v74,
      v52);
    v52 += 2;
  }
  while ( v52 != v72 );
  v74 = operator new(0x78u);
  v53 = winrt::impl::heap_implements<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,std::unordered_map<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>,winrt::impl::multi_threaded_collection_base>>::heap_implements<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,std::unordered_map<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>,winrt::impl::multi_threaded_collection_base>>(
          v74,
          &v76);
  v54 = (v53 + 16) & -(__int64)(v53 != 0);
  v70 = v54;
  if ( v6 == &v70 )
  {
    if ( v54 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v70);
  }
  else
  {
    if ( *v6 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v6);
    *v6 = v54;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(&v78);
  std::list<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>::~list<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>(v77);
  `eh vector destructor iterator'(
    v71,
    0x10u,
    1u,
    std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>::~pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(&v84);
  std::list<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>::~list<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>(v83);
  `eh vector destructor iterator'(
    v72,
    0x10u,
    1u,
    std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>::~pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>);
  v55 = v89;
  if ( v89 )
  {
    v56 = _InterlockedDecrement((volatile signed __int32 *)v89 + 6);
    if ( v56 )
    {
      if ( v56 < 0 )
        abort();
    }
    else
    {
      v57 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v57, 0, v55);
    }
    v89 = 0;
  }
  v58 = lpMem;
  if ( lpMem )
  {
    v59 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
    if ( v59 )
    {
      if ( v59 < 0 )
        abort();
    }
    else
    {
      v60 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v60, 0, v58);
    }
    lpMem = 0;
  }
  v61 = v69;
  if ( v69 )
  {
    v62 = _InterlockedDecrement((volatile signed __int32 *)v69 + 6);
    if ( v62 )
    {
      if ( v62 < 0 )
        abort();
    }
    else
    {
      v63 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v63, 0, v61);
    }
  }
  v64 = *a2;
  if ( *a2 )
  {
    v65 = _InterlockedDecrement(v64 + 6);
    if ( v65 )
    {
      if ( v65 < 0 )
        abort();
    }
    else
    {
      v66 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v66, 0, (LPVOID)v64);
    }
    *a2 = 0;
  }
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return a1;
}

```

## disassembly

```asm
0x18003afec  mov     rax, rsp
0x18003afef  mov     [rax+18h], r8
0x18003aff3  mov     [rax+10h], rdx
0x18003aff7  mov     [rax+8], rcx
0x18003affb  push    rbp
0x18003affc  push    rbx
0x18003affd  push    rsi
0x18003affe  push    rdi
0x18003afff  push    r12
0x18003b001  push    r13
0x18003b003  push    r14
0x18003b005  push    r15
0x18003b007  lea     rbp, [rax-48h]
0x18003b00b  sub     rsp, 108h
0x18003b012  mov     rsi, r8
0x18003b015  mov     r12, rdx
0x18003b018  mov     r13, rcx
0x18003b01b  xor     edi, edi
0x18003b01d  mov     dword ptr [rbp+40h+arg_18], edi
0x18003b020  lea     rax, ??_7ServiceConfiguration@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::ServiceConfiguration::`vftable'
0x18003b027  mov     [rcx], rax
0x18003b02a  lea     r15, [rcx+8]
0x18003b02e  mov     [r15], rdi
0x18003b031  mov     rax, [rdx]
0x18003b034  test    rax, rax
0x18003b037  jz      short loc_18003B041
0x18003b039  cmp     [rax+4], edi
0x18003b03c  mov     al, dil
0x18003b03f  jnz     short loc_18003B043
0x18003b041  mov     al, 1
0x18003b043  mov     rcx, [rbp+48h]; this
0x18003b047  test    al, al
0x18003b049  jnz     loc_18003B6B3
0x18003b04f  lea     rdx, [rsp+140h+var_118]
0x18003b054  mov     rcx, rsi
0x18003b057  call    ?Properties@?$consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(void)
0x18003b05c  nop
0x18003b05d  mov     ebx, 1
0x18003b062  mov     dword ptr [rbp+40h+arg_18], ebx
0x18003b065  cmp     [rax], rdi
0x18003b068  jz      short loc_18003B090
0x18003b06a  lea     rdx, [rsp+140h+lpMem]
0x18003b06f  mov     rcx, rsi
0x18003b072  call    ?Properties@?$consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(void)
0x18003b077  nop
0x18003b078  mov     ebx, 3
0x18003b07d  mov     dword ptr [rbp+40h+arg_18], ebx
0x18003b080  mov     rcx, [rax]
0x18003b083  test    rcx, rcx
0x18003b086  jz      short loc_18003B090
0x18003b088  cmp     [rcx+4], edi
0x18003b08b  mov     al, dil
0x18003b08e  jnz     short loc_18003B092
0x18003b090  mov     al, 1
0x18003b092  mov     rcx, [rbp+48h]; this
0x18003b096  test    al, al
0x18003b098  jnz     loc_18003B6CB
0x18003b09e  or      edi, 0FFFFFFFFh
0x18003b0a1  test    bl, 2
0x18003b0a4  jz      short loc_18003B0E0
0x18003b0a6  and     ebx, 0FFFFFFFDh
0x18003b0a9  mov     r14, [rsp+140h+lpMem]
0x18003b0ae  test    r14, r14
0x18003b0b1  jz      short loc_18003B0E0
0x18003b0b3  mov     eax, edi
0x18003b0b5  lock xadd [r14+18h], eax
0x18003b0bb  sub     eax, 1
0x18003b0be  jnz     loc_18003B152
0x18003b0c4  nop
0x18003b0c5  call    WINRT_IMPL_GetProcessHeap
0x18003b0ca  mov     rcx, rax; hHeap
0x18003b0cd  mov     r8, r14; lpMem
0x18003b0d0  xor     edx, edx; dwFlags
0x18003b0d2  call    WINRT_IMPL_HeapFree
0x18003b0d7  mov     [rsp+140h+lpMem], 0; int
0x18003b0e0  test    bl, 1
0x18003b0e3  jz      short loc_18003B112
0x18003b0e5  and     ebx, 0FFFFFFFEh
0x18003b0e8  mov     r14, [rsp+140h+var_118]
0x18003b0ed  test    r14, r14
0x18003b0f0  jz      short loc_18003B112
0x18003b0f2  mov     eax, edi
0x18003b0f4  lock xadd [r14+18h], eax
0x18003b0fa  sub     eax, 1
0x18003b0fd  jnz     short loc_18003B15D
0x18003b0ff  nop
0x18003b100  call    WINRT_IMPL_GetProcessHeap
0x18003b105  mov     rcx, rax; hHeap
0x18003b108  mov     r8, r14; lpMem
0x18003b10b  xor     edx, edx; dwFlags
0x18003b10d  call    WINRT_IMPL_HeapFree
0x18003b112  lea     rdx, [rsp+140h+var_118]
0x18003b117  mov     rcx, rsi
0x18003b11a  call    ?ClientId@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(void)
0x18003b11f  nop
0x18003b120  or      ebx, 4
0x18003b123  mov     dword ptr [rbp+40h+arg_18], ebx
0x18003b126  cmp     qword ptr [rax], 0
0x18003b12a  jz      short loc_18003B168
0x18003b12c  lea     rdx, [rsp+140h+lpMem]
0x18003b131  mov     rcx, rsi
0x18003b134  call    ?ClientId@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(void)
0x18003b139  nop
0x18003b13a  or      ebx, 8
0x18003b13d  mov     dword ptr [rbp+40h+arg_18], ebx
0x18003b140  mov     rcx, [rax]
0x18003b143  test    rcx, rcx
0x18003b146  jz      short loc_18003B168
0x18003b148  cmp     dword ptr [rcx+4], 0
0x18003b14c  jz      short loc_18003B168
0x18003b14e  xor     al, al
0x18003b150  jmp     short loc_18003B16A
0x18003b152  test    eax, eax
0x18003b154  jns     short loc_18003B0D7
0x18003b156  call    cs:__imp_abort
0x18003b15d  test    eax, eax
0x18003b15f  jns     short loc_18003B112
0x18003b161  call    cs:__imp_abort
0x18003b168  mov     al, 1
0x18003b16a  mov     rcx, [rbp+48h]; this
0x18003b16e  test    al, al
0x18003b170  jnz     loc_18003B6E3
0x18003b176  test    bl, 8
0x18003b179  jz      short loc_18003B1B5
0x18003b17b  and     ebx, 0FFFFFFF7h
0x18003b17e  mov     r14, [rsp+140h+lpMem]
0x18003b183  test    r14, r14
0x18003b186  jz      short loc_18003B1B5
0x18003b188  mov     eax, edi
0x18003b18a  lock xadd [r14+18h], eax
0x18003b190  sub     eax, 1
0x18003b193  jnz     loc_18003B227
0x18003b199  nop
0x18003b19a  call    WINRT_IMPL_GetProcessHeap
0x18003b19f  mov     rcx, rax; hHeap
0x18003b1a2  mov     r8, r14; lpMem
0x18003b1a5  xor     edx, edx; dwFlags
0x18003b1a7  call    WINRT_IMPL_HeapFree
0x18003b1ac  mov     [rsp+140h+lpMem], 0; int
0x18003b1b5  test    bl, 4
0x18003b1b8  jz      short loc_18003B1E7
0x18003b1ba  and     ebx, 0FFFFFFFBh
0x18003b1bd  mov     r14, [rsp+140h+var_118]
0x18003b1c2  test    r14, r14
0x18003b1c5  jz      short loc_18003B1E7
0x18003b1c7  mov     eax, edi
0x18003b1c9  lock xadd [r14+18h], eax
0x18003b1cf  sub     eax, 1
0x18003b1d2  jnz     short loc_18003B232
0x18003b1d4  nop
0x18003b1d5  call    WINRT_IMPL_GetProcessHeap
0x18003b1da  mov     rcx, rax; hHeap
0x18003b1dd  mov     r8, r14; lpMem
0x18003b1e0  xor     edx, edx; dwFlags
0x18003b1e2  call    WINRT_IMPL_HeapFree
0x18003b1e7  lea     rdx, [rsp+140h+var_118]
0x18003b1ec  mov     rcx, rsi
0x18003b1ef  call    ?BaseUrl@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(void)
0x18003b1f4  nop
0x18003b1f5  or      ebx, 10h
0x18003b1f8  mov     dword ptr [rbp+40h+arg_18], ebx
0x18003b1fb  cmp     qword ptr [rax], 0
0x18003b1ff  jz      short loc_18003B23D
0x18003b201  lea     rdx, [rsp+140h+lpMem]
0x18003b206  mov     rcx, rsi
0x18003b209  call    ?BaseUrl@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(void)
0x18003b20e  nop
0x18003b20f  or      ebx, 20h
0x18003b212  mov     dword ptr [rbp+40h+arg_18], ebx
0x18003b215  mov     rcx, [rax]
0x18003b218  test    rcx, rcx
0x18003b21b  jz      short loc_18003B23D
0x18003b21d  cmp     dword ptr [rcx+4], 0
0x18003b221  jz      short loc_18003B23D
0x18003b223  xor     al, al
0x18003b225  jmp     short loc_18003B23F
0x18003b227  test    eax, eax
0x18003b229  jns     short loc_18003B1AC
0x18003b22b  call    cs:__imp_abort
0x18003b232  test    eax, eax
0x18003b234  jns     short loc_18003B1E7
0x18003b236  call    cs:__imp_abort
0x18003b23d  mov     al, 1
0x18003b23f  mov     rcx, [rbp+48h]; this
0x18003b243  test    al, al
0x18003b245  jnz     loc_18003B6FB
0x18003b24b  test    bl, 20h
0x18003b24e  jz      short loc_18003B28A
0x18003b250  and     ebx, 0FFFFFFDFh
0x18003b253  mov     r14, [rsp+140h+lpMem]
0x18003b258  test    r14, r14
0x18003b25b  jz      short loc_18003B28A
0x18003b25d  mov     eax, edi
0x18003b25f  lock xadd [r14+18h], eax
0x18003b265  sub     eax, 1
0x18003b268  jnz     loc_18003B4FC
0x18003b26e  nop
0x18003b26f  call    WINRT_IMPL_GetProcessHeap
0x18003b274  mov     rcx, rax; hHeap
0x18003b277  mov     r8, r14; lpMem
0x18003b27a  xor     edx, edx; dwFlags
0x18003b27c  call    WINRT_IMPL_HeapFree
0x18003b281  mov     [rsp+140h+lpMem], 0; int
0x18003b28a  test    bl, 10h
0x18003b28d  jz      short loc_18003B2BC
0x18003b28f  mov     rbx, [rsp+140h+var_118]
0x18003b294  test    rbx, rbx
0x18003b297  jz      short loc_18003B2BC
0x18003b299  mov     eax, edi
0x18003b29b  lock xadd [rbx+18h], eax
0x18003b2a0  sub     eax, 1
0x18003b2a3  jnz     loc_18003B50B
0x18003b2a9  nop
0x18003b2aa  call    WINRT_IMPL_GetProcessHeap
0x18003b2af  mov     rcx, rax; hHeap
0x18003b2b2  mov     r8, rbx; lpMem
0x18003b2b5  xor     edx, edx; dwFlags
0x18003b2b7  call    WINRT_IMPL_HeapFree
0x18003b2bc  lea     rdx, [rsp+140h+lpMem]
0x18003b2c1  mov     rcx, rsi
0x18003b2c4  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x18003b2c9  nop
0x18003b2ca  mov     dword ptr [rbp+40h+arg_18], 0
0x18003b2d1  mov     rcx, [rax]
0x18003b2d4  mov     dword ptr [rsp+140h+var_E0], 0
0x18003b2dc  xorps   xmm0, xmm0
0x18003b2df  movdqu  [rsp+140h+var_E0+8], xmm0
0x18003b2e5  mov     rax, [rcx]
0x18003b2e8  lea     rdx, [rbp+40h+arg_18]
0x18003b2ec  mov     rax, [rax+38h]
0x18003b2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2f5  test    eax, eax
0x18003b2f7  js      loc_18003B713
0x18003b2fd  cmp     dword ptr [rbp+40h+arg_18], 0
0x18003b301  setz    al
0x18003b304  mov     rcx, [rbp+48h]; this
0x18003b308  test    al, al
0x18003b30a  jnz     loc_18003B69B
0x18003b310  cmp     [rsp+140h+lpMem], 0
0x18003b316  jz      short loc_18003B322
0x18003b318  lea     rcx, [rsp+140h+lpMem]
0x18003b31d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003b322  mov     rdx, r12
0x18003b325  lea     rcx, [rsp+140h+var_118]
0x18003b32a  call    ?StringToLower@@YA?AUhstring@winrt@@AEBU12@@Z; StringToLower(winrt::hstring const &)
0x18003b32f  mov     r14, rax
0x18003b332  lea     rdx, [rsp+140h+lpMem]
0x18003b337  mov     rcx, rsi
0x18003b33a  call    ?Properties@?$consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(void)
0x18003b33f  nop
0x18003b340  mov     rdx, rax
0x18003b343  lea     rcx, [rbp+40h+arg_18]
0x18003b347  call    ?StringToLower@@YA?AUhstring@winrt@@AEBU12@@Z; StringToLower(winrt::hstring const &)
0x18003b34c  nop
0x18003b34d  mov     rcx, [rax]
0x18003b350  xor     ebx, ebx
0x18003b352  mov     [rax], rbx
0x18003b355  mov     [rsp+140h+var_F8], rcx
0x18003b35a  mov     rcx, [rsi]
0x18003b35d  mov     [rsp+140h+var_F0], rcx
0x18003b362  test    rcx, rcx
0x18003b365  jz      short loc_18003B374
0x18003b367  mov     rax, [rcx]
0x18003b36a  mov     rax, [rax+8]
0x18003b36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b373  nop
0x18003b374  mov     [rbp+40h+var_88], 0
0x18003b37b  mov     [rbp+40h+var_80], rbx
0x18003b37f  mov     [rbp+40h+var_78], rbx
0x18003b383  mov     ecx, 20h ; ' '; Size
0x18003b388  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b38d  mov     [rax], rax
0x18003b390  mov     [rax+8], rax
0x18003b394  mov     [rbp+40h+var_80], rax
0x18003b398  xorps   xmm0, xmm0
0x18003b39b  movdqu  [rbp+40h+var_70], xmm0
0x18003b3a0  mov     [rbp+40h+var_60], rbx
0x18003b3a4  mov     [rbp+40h+var_58], 7
0x18003b3ac  mov     [rbp+40h+var_50], 8
0x18003b3b4  mov     [rbp+40h+var_88], 3F800000h
0x18003b3bb  mov     r8, rax
0x18003b3be  mov     edx, 10h
0x18003b3c3  lea     rcx, [rbp+40h+var_70]
0x18003b3c7  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>)
0x18003b3cc  nop
0x18003b3cd  lea     rbx, [rsp+140h+var_F8]
0x18003b3d2  mov     r8, rbx
0x18003b3d5  lea     rdx, [rsp+140h+var_E0]
0x18003b3da  lea     rcx, [rbp+40h+var_88]
0x18003b3de  call    ??$emplace@AEBU?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@?$_Hash@V?$_Umap_traits@Uhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@V?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@8@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@1@@Z; std::_Hash<std::_Umap_traits<winrt::hstring,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>,std::allocator<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>,0>>::emplace<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>> const &>(std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>> const &)
0x18003b3e3  add     rbx, 10h
0x18003b3e7  lea     rax, [rsp+140h+var_E8]
0x18003b3ec  cmp     rbx, rax
0x18003b3ef  jnz     short loc_18003B3D2
0x18003b3f1  mov     ecx, 78h ; 'x'; Size
0x18003b3f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b3fb  mov     [rsp+140h+var_E8], rax
0x18003b400  lea     rdx, [rbp+40h+var_88]
0x18003b404  mov     rcx, rax
0x18003b407  call    ??0?$heap_implements@U?$map_impl@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@V?$unordered_map@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@8@V?$allocator@U?$pair@$$CBUhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@std@@@8@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@impl@winrt@@QEAA@$$QEAV?$unordered_map@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@8@V?$allocator@U?$pair@$$CBUhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@std@@@8@@std@@@Z; winrt::impl::heap_implements<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::heap_implements<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>(std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig> &&)
  ... truncated ...
```
