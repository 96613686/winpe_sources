# Windows::Internal::CloudRequestor::Common::JsonParser::ParseProtocolConfig(ushort const *)

- ea: `0x18006f340`
- end: `0x18006f9c6`
- name: `?ParseProtocolConfig@JsonParser@Common@CloudRequestor@Internal@Windows@@SA?AV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@@std@@@2@@std@@PEBG@Z`
- size: `1670`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064ae0`

## callees

- `0x180002810`
- `0x180002840`
- `0x1800034f7`
- `0x1800035ab`
- `0x180005004`
- `0x18000e7ec`
- `0x18000ed24`
- `0x1800130a4`
- `0x1800139fc`
- `0x180013f6c`
- `0x180016438`
- `0x180018198`
- `0x180018320`
- `0x18001c1d4`
- `0x180023754`
- `0x180027f44`
- `0x18002d118`
- `0x1800325a8`
- `0x180038674`
- `0x180060d60`
- `0x180066c60`
- `0x18006e64c`
- `0x18006e768`
- `0x18006e9d4`
- `0x18006ee90`
- `0x18006ef20`
- `0x18006f340`
- `0x18006f9cc`
- `0x1800703dc`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f402`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f8c2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f8c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f8d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f402`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f8c2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f8c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006f8d0`

## string_xrefs

- `0x18006f94c`: `ProtocolConfigJson Parse Error`
- `0x18006f692`: `onecoreuap\shell\clouddirect\common\jsonparser.cpp`
- `0x18006f958`: `onecoreuap\shell\clouddirect\common\jsonparser.cpp`
- `0x18006f9b4`: `onecoreuap\shell\clouddirect\common\jsonparser.cpp`
- `0x18006f9a8`: `ProtocolConfigJson Parse Error - Invalid Protocol Object: %ls`
- `0x18006f680`: `ProtocolConfigJson Parse Error - Expected String Value Type for Config: %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall Windows::Internal::CloudRequestor::Common::JsonParser::ParseProtocolConfig(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  char v7; // al
  int v8; // ebx
  int v9; // eax
  _QWORD *v10; // rax
  __int64 ObjectW; // rax
  int v12; // ebx
  int v13; // eax
  int v14; // eax
  volatile signed __int32 *v15; // rdi
  const WCHAR *v16; // rdx
  __int64 v17; // rsi
  const WCHAR *v18; // rdx
  __int64 v19; // rax
  int v20; // eax
  HANDLE ProcessHeap; // rax
  void *v22; // rdi
  int v23; // eax
  HANDLE v24; // rax
  const WCHAR *v25; // rdx
  __int64 v26; // rax
  void *v27; // rdi
  int v28; // eax
  HANDLE v29; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  const char *v33; // rdx
  char *v34; // [rsp+28h] [rbp-D8h]
  __int64 v35; // [rsp+30h] [rbp-D0h]
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-70h] BYREF
  __int128 *v48; // [rsp+98h] [rbp-68h] BYREF
  __int128 v49; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v52[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v53; // [rsp+D0h] [rbp-30h] BYREF
  int v54; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v55[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v56; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  __int64 v60; // [rsp+120h] [rbp+20h]
  _BYTE v61[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v62[16]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v63[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v64[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v60 = a1;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v4 = operator new(0x70u);
  *v4 = v4;
  v4[1] = v4;
  *(_QWORD *)(a1 + 8) = v4;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 7;
  *(_QWORD *)(a1 + 56) = 8;
  *(_DWORD *)a1 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(
    a1 + 24,
    16,
    *(_QWORD *)(a1 + 8));
  v5 = 1;
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v44);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  if ( (_DWORD)v6 )
  {
    if ( *(_WORD *)(a2 + 2LL * (unsigned int)v6) )
      abort();
    LODWORD(v49) = 1;
    DWORD1(v49) = v6;
    v50 = a2;
    v48 = &v49;
  }
  else
  {
    v48 = 0;
  }
  v52[0] = &v48;
  v52[1] = &v44;
  v53 = &qword_18009CF78;
  _InterlockedAdd64(&qword_18009CF78, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> )
  {
    v7 = _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(
           v52,
           &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>);
    _InterlockedDecrement64(&qword_18009CF78);
  }
  else
  {
    _InterlockedDecrement64(&qword_18009CF78);
    v7 = winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::call<_lambda_216e461b0f2bafa6414b8faed9d5cbb6_ &>(
           v6,
           v52);
  }
  if ( !v7 )
  {
    v31 = wil::verify_hresult<long>(2205483015LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
      (const char *)v31,
      (int)"ProtocolConfigJson Parse Error",
      v34);
  }
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::GetView(
    &v44,
    &v46);
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
    &v46,
    &v39);
  v52[0] = 0;
  while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v39, v52) )
  {
    v38 = 0;
    v8 = v5 | 4;
    LODWORD(v48) = 0;
    v49 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, &v38);
    if ( v9 < 0 )
      winrt::throw_hresult((unsigned int)v9, &v48);
    winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
      &v38,
      &v43);
    winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(
      &v38,
      &v42);
    v5 = v8 & 0xFFFFFFE1 | 0x1A;
    LODWORD(v35) = v5;
    if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(&v42) != 5 )
    {
      winrt::hstring::c_str((winrt::hstring *)&v43);
      v32 = wil::verify_hresult<long>(2205483015LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
        (const char *)v32,
        (int)"ProtocolConfigJson Parse Error - Invalid Protocol Object: %ls",
        v33,
        v35);
    }
    v54 = 0;
    v55[0] = 0;
    v55[1] = 0;
    v10 = operator new(0x50u);
    *v10 = v10;
    v10[1] = v10;
    v55[0] = v10;
    v56 = 0;
    v57 = 0;
    v58 = 7;
    v59 = 8;
    v54 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(
      &v56,
      16,
      v10);
    ObjectW = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(
                &v42,
                &v51);
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::GetView(
      ObjectW,
      &v45);
    if ( v51 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
    winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(
      &v45,
      &v37);
    v53 = 0;
    while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(&v37, &v53) )
    {
      v36 = 0;
      v12 = v5 | 0x40;
      LODWORD(v48) = 0;
      v49 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL))(v37, &v36);
      if ( v13 < 0 )
        winrt::throw_hresult((unsigned int)v13, &v48);
      winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(
        &v36,
        &v41);
      winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(
        &v36,
        &v40);
      v5 = v12 & 0xFFFFFE1F | 0x1A0;
      LODWORD(v35) = v5;
      if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(&v40) == 3 )
      {
        lpMem = 0;
        LODWORD(v48) = 0;
        v49 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 64LL))(v40, &lpMem);
        if ( v14 < 0 )
          winrt::throw_hresult((unsigned int)v14, &v48);
        v15 = (volatile signed __int32 *)lpMem;
        v5 |= 0x200u;
        if ( lpMem )
          v16 = (const WCHAR *)*((_QWORD *)lpMem + 2);
        else
          v16 = &Name;
        v17 = Windows::Internal::CloudRequestor::Common::WideStringToLowerCase(v63, v16);
        if ( v41 )
          v18 = (const WCHAR *)*((_QWORD *)v41 + 2);
        else
          v18 = &Name;
        v19 = Windows::Internal::CloudRequestor::Common::WideStringToLowerCase(v64, v18);
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring,std::wstring>(
          &v54,
          v61,
          v19,
          v17);
        std::wstring::_Tidy_deallocate(v64);
        std::wstring::_Tidy_deallocate(v63);
        if ( v15 )
        {
          v20 = _InterlockedDecrement(v15 + 6);
          if ( v20 )
          {
            if ( v20 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
          }
        }
      }
      else if ( v41 )
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x3C,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
          (const char *)0x83750007LL,
          (int)"ProtocolConfigJson Parse Error - Expected String Value Type for Config: %ls",
          *((const char **)v41 + 2),
          v35);
      }
      else
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x3C,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\common\\jsonparser.cpp",
          (const char *)0x83750007LL,
          (int)"ProtocolConfigJson Parse Error - Expected String Value Type for Config: %ls",
          (const char *)&Name,
          v35);
      }
      if ( v40 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v40);
      v22 = v41;
      if ( v41 )
      {
        v23 = _InterlockedDecrement((volatile signed __int32 *)v41 + 6);
        if ( v23 )
        {
          if ( v23 < 0 )
            abort();
        }
        else
        {
          v24 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v24, 0, v22);
        }
        v41 = 0;
      }
      if ( v36 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
      winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(&v37);
    }
    if ( v37 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
    if ( v43 )
      v25 = (const WCHAR *)*((_QWORD *)v43 + 2);
    else
      v25 = &Name;
    v26 = Windows::Internal::CloudRequestor::Common::WideStringToLowerCase(v63, v25);
    ___emplace_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAV__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2_____Hash_V___Umap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2_V___Uhash_compare_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2__2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___2__0A__std___std__QEAA_AU__pair_V___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__2__std___std___std___std___N_1___QEAV__basic_string_GU__char_traits_G_std__V__allocator_G_2__1_AEAV__unordered_map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__hash_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_U__equal_to_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__1__Z(
      a1,
      v62,
      v26,
      &v54);
    std::wstring::_Tidy_deallocate(v63);
    if ( v45 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v45);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(&v56);
    std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v55);
    if ( v42 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v42);
    v27 = v43;
    if ( v43 )
    {
      v28 = _InterlockedDecrement((volatile signed __int32 *)v43 + 6);
      if ( v28 )
      {
        if ( v28 < 0 )
          abort();
      }
      else
      {
        v29 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v29, 0, v27);
      }
      v43 = 0;
    }
    if ( v38 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
    winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(&v39);
  }
  if ( v39 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v39);
  if ( v46 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v46);
  if ( v44 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
  return a1;
}

```

## disassembly

```asm
0x18006f340  push    rbp
0x18006f342  push    rbx
0x18006f343  push    rsi
0x18006f344  push    rdi
0x18006f345  push    r14
0x18006f347  push    r15
0x18006f349  lea     rbp, [rsp-0A8h]
0x18006f351  sub     rsp, 1A8h
0x18006f358  mov     rax, cs:__security_cookie
0x18006f35f  xor     rax, rsp
0x18006f362  mov     [rbp+0D0h+var_40], rax
0x18006f369  mov     rdi, rdx
0x18006f36c  mov     r14, rcx
0x18006f36f  mov     [rbp+0D0h+var_B0], rcx
0x18006f373  xor     r15d, r15d
0x18006f376  mov     dword ptr [rsp+1D0h+var_1A0], r15d
0x18006f37b  mov     [rcx], r15d
0x18006f37e  mov     [rcx+8], r15
0x18006f382  mov     [rcx+10h], r15
0x18006f386  lea     ecx, [r15+70h]; Size
0x18006f38a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f38f  mov     [rax], rax
0x18006f392  mov     [rax+8], rax
0x18006f396  mov     [r14+8], rax
0x18006f39a  lea     rcx, [r14+18h]
0x18006f39e  mov     [rcx], r15
0x18006f3a1  mov     [rcx+8], r15
0x18006f3a5  mov     [rcx+10h], r15
0x18006f3a9  mov     qword ptr [r14+30h], 7
0x18006f3b1  mov     qword ptr [r14+38h], 8
0x18006f3b9  mov     dword ptr [r14], 3F800000h
0x18006f3c0  mov     r8, [r14+8]
0x18006f3c4  lea     edx, [r15+10h]
0x18006f3c8  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>)
0x18006f3cd  nop
0x18006f3ce  lea     ebx, [r15+1]
0x18006f3d2  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f3d6  lea     rcx, [rsp+1D0h+var_158]; this
0x18006f3db  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18006f3e0  nop
0x18006f3e1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006f3e5  inc     rcx
0x18006f3e8  cmp     [rdi+rcx*2], r15w
0x18006f3ed  jnz     short loc_18006F3E5
0x18006f3ef  test    ecx, ecx
0x18006f3f1  jnz     short loc_18006F3F9
0x18006f3f3  mov     [rbp+0D0h+var_138], r15
0x18006f3f7  jmp     short loc_18006F41B
0x18006f3f9  mov     eax, ecx
0x18006f3fb  cmp     [rdi+rax*2], r15w
0x18006f400  jz      short loc_18006F409
0x18006f402  call    cs:__imp_abort
0x18006f409  mov     dword ptr [rbp+0D0h+var_130], ebx
0x18006f40c  mov     dword ptr [rbp+0D0h+var_130+4], ecx
0x18006f40f  mov     [rbp+0D0h+var_120], rdi
0x18006f413  lea     rax, [rbp+0D0h+var_130]
0x18006f417  mov     [rbp+0D0h+var_138], rax
0x18006f41b  lea     rax, [rbp+0D0h+var_138]
0x18006f41f  mov     [rbp+0D0h+var_110], rax
0x18006f423  lea     rax, [rsp+1D0h+var_158]
0x18006f428  mov     [rbp+0D0h+var_108], rax
0x18006f42c  lea     rax, qword_18009CF78
0x18006f433  mov     [rbp+0D0h+var_100], rax
0x18006f437  lock add cs:qword_18009CF78, rbx
0x18006f43f  cmp     cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A, r15; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18006f446  jz      short loc_18006F463
0x18006f448  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Data::Json::IJsonObjectStatics>
0x18006f44f  lea     rcx, [rbp+0D0h+var_110]
0x18006f453  call    ??R_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@QEBA@AEBUIJsonObjectStatics@Json@Data@Windows@winrt@@@Z; _lambda_216e461b0f2bafa6414b8faed9d5cbb6_::operator()(winrt::Windows::Data::Json::IJsonObjectStatics const &)
0x18006f458  nop
0x18006f459  lock dec cs:qword_18009CF78
0x18006f461  jmp     short loc_18006F474
0x18006f463  lock dec cs:qword_18009CF78
0x18006f46b  lea     rdx, [rbp+0D0h+var_110]
0x18006f46f  call    ??$call@AEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIJsonObjectStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_216e461b0f2bafa6414b8faed9d5cbb6_@@@Z
0x18006f474  test    al, al
0x18006f476  jz      loc_18006F938
0x18006f47c  lea     rdx, [rbp+0D0h+var_148]
0x18006f480  lea     rcx, [rsp+1D0h+var_158]
0x18006f485  call    ?GetView@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::GetView(void)
0x18006f48a  nop
0x18006f48b  lea     rdx, [rsp+1D0h+var_180]
0x18006f490  lea     rcx, [rbp+0D0h+var_148]
0x18006f494  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IMapView@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(void)
0x18006f499  nop
0x18006f49a  mov     [rbp+0D0h+var_110], r15
0x18006f49e  lea     rdx, [rbp+0D0h+var_110]
0x18006f4a2  lea     rcx, [rsp+1D0h+var_180]
0x18006f4a7  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18006f4ac  test    al, al
0x18006f4ae  jnz     loc_18006F8D7
0x18006f4b4  mov     [rsp+1D0h+var_188], r15
0x18006f4b9  or      ebx, 4
0x18006f4bc  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f4c0  mov     rcx, [rsp+1D0h+var_180]
0x18006f4c5  mov     dword ptr [rbp+0D0h+var_138], r15d
0x18006f4c9  xorps   xmm0, xmm0
0x18006f4cc  movdqu  [rbp+0D0h+var_130], xmm0
0x18006f4d1  mov     rax, [rcx]
0x18006f4d4  lea     rdx, [rsp+1D0h+var_188]
0x18006f4d9  mov     rax, [rax+30h]
0x18006f4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f4e2  test    eax, eax
0x18006f4e4  js      loc_18006F92C
0x18006f4ea  and     ebx, 0FFFFFFFBh
0x18006f4ed  or      ebx, 2
0x18006f4f0  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f4f4  lea     rdx, [rsp+1D0h+var_160]
0x18006f4f9  lea     rcx, [rsp+1D0h+var_188]
0x18006f4fe  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x18006f503  or      ebx, 8
0x18006f506  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f50a  lea     rdx, [rsp+1D0h+var_168]
0x18006f50f  lea     rcx, [rsp+1D0h+var_188]
0x18006f514  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(void)
0x18006f519  or      ebx, 10h
0x18006f51c  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f520  lea     rcx, [rsp+1D0h+var_168]
0x18006f525  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18006f52a  cmp     eax, 5
0x18006f52d  jnz     loc_18006F982
0x18006f533  mov     [rbp+0D0h+var_F0], 0
0x18006f53a  mov     [rbp+0D0h+var_E8], r15
0x18006f53e  mov     [rbp+0D0h+var_E0], r15
0x18006f542  lea     ecx, [rax+4Bh]; Size
0x18006f545  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006f54a  mov     [rax], rax
0x18006f54d  mov     [rax+8], rax
0x18006f551  mov     [rbp+0D0h+var_E8], rax
0x18006f555  mov     [rbp+0D0h+var_D8], r15
0x18006f559  xorps   xmm0, xmm0
0x18006f55c  movdqa  [rbp+0D0h+var_D0], xmm0
0x18006f561  mov     [rbp+0D0h+var_C0], 7
0x18006f569  mov     [rbp+0D0h+var_B8], 8
0x18006f571  mov     [rbp+0D0h+var_F0], 3F800000h
0x18006f578  mov     r8, rax
0x18006f57b  mov     edx, 10h
0x18006f580  lea     rcx, [rbp+0D0h+var_D8]
0x18006f584  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@U?$IMap@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@Collections@Foundation@Windows@2@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>)
0x18006f589  nop
0x18006f58a  lea     rdx, [rbp+0D0h+var_118]
0x18006f58e  lea     rcx, [rsp+1D0h+var_168]
0x18006f593  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x18006f598  nop
0x18006f599  lea     rdx, [rbp+0D0h+var_150]
0x18006f59d  mov     rcx, rax
0x18006f5a0  call    ?GetView@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::GetView(void)
0x18006f5a5  nop
0x18006f5a6  cmp     [rbp+0D0h+var_118], r15
0x18006f5aa  jz      short loc_18006F5B5
0x18006f5ac  lea     rcx, [rbp+0D0h+var_118]
0x18006f5b0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18006f5b5  lea     rdx, [rsp+1D0h+var_190]
0x18006f5ba  lea     rcx, [rbp+0D0h+var_150]
0x18006f5be  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IMapView@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::begin(void)
0x18006f5c3  nop
0x18006f5c4  mov     [rbp+0D0h+var_100], r15
0x18006f5c8  lea     rdx, [rbp+0D0h+var_100]
0x18006f5cc  lea     rcx, [rsp+1D0h+var_190]
0x18006f5d1  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18006f5d6  test    al, al
0x18006f5d8  jnz     loc_18006F7E8
0x18006f5de  mov     [rsp+1D0h+var_198], r15
0x18006f5e3  or      ebx, 40h
0x18006f5e6  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f5ea  mov     rcx, [rsp+1D0h+var_190]
0x18006f5ef  mov     dword ptr [rbp+0D0h+var_138], r15d
0x18006f5f3  xorps   xmm0, xmm0
0x18006f5f6  movdqu  [rbp+0D0h+var_130], xmm0
0x18006f5fb  mov     rax, [rcx]
0x18006f5fe  lea     rdx, [rsp+1D0h+var_198]
0x18006f603  mov     rax, [rax+30h]
0x18006f607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f60c  test    eax, eax
0x18006f60e  js      loc_18006F976
0x18006f614  and     ebx, 0FFFFFFBFh
0x18006f617  or      ebx, 20h
0x18006f61a  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f61e  lea     rdx, [rsp+1D0h+var_170]
0x18006f623  lea     rcx, [rsp+1D0h+var_198]
0x18006f628  call    ?Key@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Key(void)
0x18006f62d  bts     ebx, 7
0x18006f631  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f635  lea     rdx, [rsp+1D0h+var_178]
0x18006f63a  lea     rcx, [rsp+1D0h+var_198]
0x18006f63f  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@Uhstring@5@UIJsonValue@Json@Data@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::Value(void)
0x18006f644  bts     ebx, 8
0x18006f648  mov     esi, ebx
0x18006f64a  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f64e  lea     rcx, [rsp+1D0h+var_178]
0x18006f653  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18006f658  cmp     eax, 3
0x18006f65b  jz      short loc_18006F6A8
0x18006f65d  mov     rax, [rsp+1D0h+var_170]
0x18006f662  test    rax, rax
0x18006f665  jz      short loc_18006F66D
0x18006f667  mov     rdx, [rax+10h]
0x18006f66b  jmp     short loc_18006F674
0x18006f66d  lea     rdx, Name
0x18006f674  mov     rcx, [rbp+0D8h]; this
0x18006f67b  mov     [rsp+1D0h+var_1A8], rdx; char *
0x18006f680  lea     rax, aProtocolconfig; "ProtocolConfigJson Parse Error - Expect"...
0x18006f687  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18006f68c  mov     r9d, 83750007h; char *
0x18006f692  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\clouddirect\\common"...
0x18006f699  mov     edx, 3Ch ; '<'; void *
0x18006f69e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006f6a3  jmp     loc_18006F77D
0x18006f6a8  mov     [rbp+0D0h+lpMem], r15
0x18006f6ac  mov     rcx, [rsp+1D0h+var_178]
0x18006f6b1  mov     dword ptr [rbp+0D0h+var_138], r15d
0x18006f6b5  xorps   xmm0, xmm0
0x18006f6b8  movdqu  [rbp+0D0h+var_130], xmm0
0x18006f6bd  mov     rax, [rcx]
0x18006f6c0  lea     rdx, [rbp+0D0h+lpMem]
0x18006f6c4  mov     rax, [rax+40h]
0x18006f6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6cd  test    eax, eax
0x18006f6cf  js      loc_18006F96A
0x18006f6d5  mov     rdi, [rbp+0D0h+lpMem]
0x18006f6d9  mov     [rbp+0D0h+lpMem], rdi
0x18006f6dd  bts     esi, 9
0x18006f6e1  mov     ebx, esi
0x18006f6e3  mov     dword ptr [rsp+1D0h+var_1A0], ebx
0x18006f6e7  test    rdi, rdi
0x18006f6ea  jz      short loc_18006F6F2
0x18006f6ec  mov     rdx, [rdi+10h]
0x18006f6f0  jmp     short loc_18006F6F9
0x18006f6f2  lea     rdx, Name
0x18006f6f9  lea     rcx, [rbp+0D0h+var_80]
0x18006f6fd  call    ?WideStringToLowerCase@Common@CloudRequestor@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::CloudRequestor::Common::WideStringToLowerCase(ushort const *)
0x18006f702  mov     rsi, rax
0x18006f705  mov     rcx, [rsp+1D0h+var_170]
0x18006f70a  test    rcx, rcx
0x18006f70d  jz      short loc_18006F715
0x18006f70f  mov     rdx, [rcx+10h]
0x18006f713  jmp     short loc_18006F71C
0x18006f715  lea     rdx, Name
0x18006f71c  lea     rcx, [rbp+0D0h+var_60]
0x18006f720  call    ?WideStringToLowerCase@Common@CloudRequestor@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Windows::Internal::CloudRequestor::Common::WideStringToLowerCase(ushort const *)
0x18006f725  nop
0x18006f726  mov     r9, rsi
0x18006f729  mov     r8, rax
0x18006f72c  lea     rdx, [rbp+0D0h+var_A0]
0x18006f730  lea     rcx, [rbp+0D0h+var_F0]
0x18006f734  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::wstring,std::wstring>(std::wstring &&,std::wstring &&)
0x18006f739  nop
0x18006f73a  lea     rcx, [rbp+0D0h+var_60]
0x18006f73e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f743  nop
0x18006f744  lea     rcx, [rbp+0D0h+var_80]
0x18006f748  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f74d  nop
0x18006f74e  test    rdi, rdi
0x18006f751  jz      short loc_18006F77D
0x18006f753  or      eax, 0FFFFFFFFh
0x18006f756  lock xadd [rdi+18h], eax
0x18006f75b  sub     eax, 1
0x18006f75e  jnz     short loc_18006F775
0x18006f760  nop
0x18006f761  call    WINRT_IMPL_GetProcessHeap
0x18006f766  mov     rcx, rax; hHeap
0x18006f769  mov     r8, rdi; lpMem
0x18006f76c  xor     edx, edx; dwFlags
0x18006f76e  call    WINRT_IMPL_HeapFree
0x18006f773  jmp     short loc_18006F77D
0x18006f775  test    eax, eax
0x18006f777  js      loc_18006F8C2
0x18006f77d  cmp     [rsp+1D0h+var_178], r15
0x18006f782  jz      short loc_18006F78F
0x18006f784  lea     rcx, [rsp+1D0h+var_178]
0x18006f789  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18006f78e  nop
0x18006f78f  mov     rdi, [rsp+1D0h+var_170]
0x18006f794  test    rdi, rdi
0x18006f797  jz      short loc_18006F7C8
0x18006f799  or      eax, 0FFFFFFFFh
0x18006f79c  lock xadd [rdi+18h], eax
0x18006f7a1  sub     eax, 1
0x18006f7a4  jnz     short loc_18006F7BB
0x18006f7a6  nop
0x18006f7a7  call    WINRT_IMPL_GetProcessHeap
0x18006f7ac  mov     rcx, rax; hHeap
0x18006f7af  mov     r8, rdi; lpMem
0x18006f7b2  xor     edx, edx; dwFlags
0x18006f7b4  call    WINRT_IMPL_HeapFree
0x18006f7b9  jmp     short loc_18006F7C3
0x18006f7bb  test    eax, eax
0x18006f7bd  js      loc_18006F8C9
0x18006f7c3  mov     [rsp+1D0h+var_170], r15
0x18006f7c8  cmp     [rsp+1D0h+var_198], r15
0x18006f7cd  jz      short loc_18006F7D9
0x18006f7cf  lea     rcx, [rsp+1D0h+var_198]
0x18006f7d4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18006f7d9  lea     rcx, [rsp+1D0h+var_190]
0x18006f7de  call    ??E?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@2345@@impl@winrt@@QEAA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>::operator++(void)
0x18006f7e3  jmp     loc_18006F5C8
0x18006f7e8  cmp     [rsp+1D0h+var_190], r15
0x18006f7ed  jz      short loc_18006F7F9
0x18006f7ef  lea     rcx, [rsp+1D0h+var_190]
  ... truncated ...
```
