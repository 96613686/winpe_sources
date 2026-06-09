# EndpointManager::LogAggregatedStagingState(void)

- ea: `0x180022a8c`
- end: `0x180022fff`
- name: `?LogAggregatedStagingState@EndpointManager@@SAXXZ`
- size: `1395`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c730`

## callees

- `0x180003110`
- `0x18000843c`
- `0x18000847c`
- `0x180008504`
- `0x180009fcc`
- `0x18000a0c4`
- `0x18000fe24`
- `0x180010130`
- `0x1800101fc`
- `0x180010278`
- `0x1800148e0`
- `0x180014928`
- `0x180019e68`
- `0x18001e7a0`
- `0x1800208bc`
- `0x180020ae0`
- `0x180020c9c`
- `0x18002178c`
- `0x1800218e4`
- `0x180021a20`
- `0x180021a4c`
- `0x180021ad8`
- `0x180021c88`
- `0x180021d6c`
- `0x180021f60`
- `0x180021fac`
- `0x180022070`
- `0x180022130`
- `0x180022738`
- `0x180022a8c`
- `0x1800231f4`
- `0x180023b24`
- `0x180023ccc`
- `0x180024514`
- `0x18002d720`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022d7e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022d7e`

## string_xrefs

- `0x180022fc3`: `onecore\base\flighting\onesettings\libs\configurationsmanager\endpointmanager.cpp`
- `0x180022fd8`: `onecore\base\flighting\onesettings\libs\configurationsmanager\endpointmanager.cpp`
- `0x180022fed`: `onecore\base\flighting\onesettings\libs\configurationsmanager\endpointmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void EndpointManager::LogAggregatedStagingState(void)
{
  _QWORD *FixedClients; // rdi
  _QWORD *v1; // rbx
  __int64 *DownloadedClients; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  _QWORD *v5; // rbx
  __int64 *v6; // rdi
  _QWORD *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  _QWORD *PayloadHandler; // rax
  __int64 v12; // rax
  __int64 *v13; // rbx
  EndpointManager *v14; // r8
  __int64 v15; // rdi
  HRESULT v16; // eax
  __int64 v17; // rax
  __int64 v18; // rsi
  __int64 v19; // rax
  __int64 (__fastcall *v20)(__int64, __int64, EndpointManager **); // r9
  __int64 v21; // r10
  int v22; // eax
  EndpointManager *v23; // rdi
  __int64 (__fastcall *v24)(EndpointManager *, const wchar_t *, __int64 *); // rbx
  int v25; // eax
  BOOL v26; // ebx
  __int64 v27; // rax
  __int64 v28; // rax
  const unsigned __int16 *v29; // rax
  __int64 v30; // r11
  struct OneSettingsClientTelemetryCore::Config *v31; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  char v33[8]; // [rsp+30h] [rbp-D0h] BYREF
  EndpointManager *v34; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h]
  _QWORD *v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h]
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  struct OneSettingsClientTelemetryCore::Config *v40[2]; // [rsp+68h] [rbp-98h] BYREF
  struct OneSettingsClientTelemetryCore::Config *v41; // [rsp+78h] [rbp-88h]
  LPVOID v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v43; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v44; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  _QWORD v48[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v49[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[32]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v51[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v52[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v53; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(&v37);
  std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(&v35);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager>::GetImpl'::`2'::impl) )
  {
    EndpointManager::CurrentEndpointManager(&v43, 0);
    FixedClients = (_QWORD *)EndpointManager::_GetFixedClients(v43);
    if ( &v37 != FixedClients )
    {
      v1 = v37;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(
        &v37,
        &v37,
        v37[1]);
      v1[1] = v1;
      *v1 = v1;
      v1[2] = v1;
      v38 = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(
        &v37,
        FixedClients);
    }
    DownloadedClients = EndpointManager::_GetDownloadedClients(v43, 0);
    if ( &v35 != (_QWORD **)DownloadedClients )
    {
      v3 = v35;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(
        &v35,
        &v35,
        v35[1]);
      v3[1] = v3;
      *v3 = v3;
      v3[2] = v3;
      v36 = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(
        &v35,
        DownloadedClients);
    }
    if ( v44 )
      std::_Ref_count_base::_Decref(v44);
  }
  else
  {
    v33[0] = 0;
    std::make_unique<EndpointManager,bool,0>(&v34, v33);
    v4 = (_QWORD *)EndpointManager::_GetFixedClients(v34);
    if ( &v37 != v4 )
    {
      v5 = v37;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(
        &v37,
        &v37,
        v37[1]);
      v5[1] = v5;
      *v5 = v5;
      v5[2] = v5;
      v38 = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(
        &v37,
        v4);
    }
    v6 = EndpointManager::_GetDownloadedClients((__int64 *)v34, 0);
    if ( &v35 != (_QWORD **)v6 )
    {
      v7 = v35;
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(
        &v35,
        &v35,
        v35[1]);
      v7[1] = v7;
      *v7 = v7;
      v7[2] = v7;
      v36 = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(
        &v35,
        v6);
    }
    std::unique_ptr<EndpointManager>::~unique_ptr<EndpointManager>(&v34);
  }
  std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(v48);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::merge<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>(
    v48,
    &v37);
  std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::merge<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>(
    v48,
    &v35);
  std::set<std::wstring>::set<std::wstring>(v49, v8, v9);
  v10 = *(_QWORD *)v48[0];
  v39 = *(_QWORD *)v48[0];
  while ( !*(_BYTE *)(v10 + 25) )
  {
    std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>(
      v52,
      v10 + 32);
    PayloadHandler = (_QWORD *)ClientEndpoint::GetPayloadHandler(v53, &v45);
    (*(void (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)*PayloadHandler + 72LL))(*PayloadHandler, v51);
    if ( v46 )
      std::_Ref_count_base::_Decref(v46);
    if ( *(_QWORD *)&v51[1] )
    {
      v12 = std::wstring::wstring((__int64)v50, (__int64)v51);
      FlightIdUtils::GetFlightIdsByType(&v43, v12);
      v13 = v43;
      v14 = (EndpointManager *)*v43;
      v34 = (EndpointManager *)*v43;
      v15 = v49[0];
      while ( v14 != (EndpointManager *)v13 )
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace_hint<std::wstring const &>(
          v49,
          v15,
          (char *)v14 + 32);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v34);
        v14 = v34;
      }
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v43);
    }
    std::wstring::_Tidy_deallocate(v51);
    std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>::~pair<std::wstring const,std::shared_ptr<CnsFlightState>>(v52);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v39);
    v10 = v39;
  }
  v42 = 0;
  v16 = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, &v42);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\endpointmanager.cpp",
      (const char *)(unsigned int)v16,
      ppv);
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v17 = *(_QWORD *)v49[0];
  v39 = *(_QWORD *)v49[0];
  while ( !*(_BYTE *)(v17 + 25) )
  {
    v18 = v17 + 32;
    v34 = 0;
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17 + 32);
    v22 = v20(v21, v19, &v34);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\endpointmanager.cpp",
        (const char *)(unsigned int)v22,
        ppv);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v23 = v34;
    v24 = *(__int64 (__fastcall **)(EndpointManager *, const wchar_t *, __int64 *))(*(_QWORD *)v34 + 72LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v45);
    v46 = (std::_Ref_count_base *)-1LL;
    v47 = -1;
    v25 = v24(v23, L"Triggered", &v45);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\endpointmanager.cpp",
        (const char *)(unsigned int)v25,
        ppv);
    v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
            &v45,
            L"1",
            -1) == 2;
    v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
    v28 = std::wstring::wstring((__int64)v50, v27);
    memset((char *)v51 + 4, 0, 24);
    LODWORD(v51[0]) = v26;
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    StringCchCopyW((unsigned __int16 *)v51 + 2, 0xCu, v29);
    std::wstring::_Tidy_deallocate(v30);
    v31 = v40[1];
    if ( v40[1] == v41 )
    {
      std::vector<OneSettingsClientTelemetryCore::Config>::_Emplace_reallocate<OneSettingsClientTelemetryCore::Config>(
        v40,
        (__int64)v40[1],
        v51);
    }
    else
    {
      *(_OWORD *)v40[1] = v51[0];
      *(_OWORD *)((char *)v31 + 12) = *(_OWORD *)((char *)v51 + 12);
      v40[1] = (struct OneSettingsClientTelemetryCore::Config *)((char *)v40[1] + 28);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v45);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v34);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v39);
    v17 = v39;
  }
  OneSettingsClientTelemetryCore::ReportAggregateStagingState(28087 * ((v40[1] - v40[0]) >> 2), v40[0]);
  if ( v40[0] )
  {
    std::_Deallocate<16>(v40[0], 4 * ((v41 - v40[0]) >> 2));
    *(_OWORD *)v40 = 0;
    v41 = 0;
  }
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v42);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v49);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    v48,
    v48);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    &v35,
    &v35);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>,void *>>>(
    &v37,
    &v37);
}

```

## disassembly

```asm
0x180022a8c  push    rbp
0x180022a8e  push    rbx
0x180022a8f  push    rsi
0x180022a90  push    rdi
0x180022a91  push    r14
0x180022a93  push    r15
0x180022a95  lea     rbp, [rsp-58h]
0x180022a9a  sub     rsp, 158h
0x180022aa1  mov     rax, cs:__security_cookie
0x180022aa8  xor     rax, rsp
0x180022aab  mov     [rbp+80h+var_40], rax
0x180022aaf  lea     rcx, [rsp+180h+var_130]
0x180022ab4  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(void)
0x180022ab9  nop
0x180022aba  lea     rcx, [rsp+180h+var_140]
0x180022abf  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(void)
0x180022ac4  nop
0x180022ac5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager>::GetImpl(void)'::`2'::impl
0x180022acc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscCacheEndpointManager>::__private_IsEnabled(void)
0x180022ad1  xor     r14d, r14d
0x180022ad4  test    al, al
0x180022ad6  jz      loc_180022B98
0x180022adc  xor     edx, edx
0x180022ade  lea     rcx, [rbp+80h+var_F8]
0x180022ae2  call    ?CurrentEndpointManager@EndpointManager@@CA?AV?$shared_ptr@VEndpointManager@@@std@@_N@Z; EndpointManager::CurrentEndpointManager(bool)
0x180022ae7  nop
0x180022ae8  mov     rcx, [rbp+80h+var_F8]
0x180022aec  call    ?_GetFixedClients@EndpointManager@@AEAAAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@XZ; EndpointManager::_GetFixedClients(void)
0x180022af1  mov     rdi, rax
0x180022af4  lea     rax, [rsp+180h+var_130]
0x180022af9  cmp     rax, rdi
0x180022afc  jz      short loc_180022B33
0x180022afe  mov     rbx, [rsp+180h+var_130]
0x180022b03  mov     r8, [rbx+8]
0x180022b07  lea     rdx, [rsp+180h+var_130]
0x180022b0c  lea     rcx, [rsp+180h+var_130]
0x180022b11  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *> *)
0x180022b16  mov     [rbx+8], rbx
0x180022b1a  mov     [rbx], rbx
0x180022b1d  mov     [rbx+10h], rbx
0x180022b21  mov     [rsp+180h+var_128], r14
0x180022b26  mov     rdx, rdi
0x180022b29  lea     rcx, [rsp+180h+var_130]
0x180022b2e  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>> const &)
0x180022b33  xor     edx, edx
0x180022b35  mov     rcx, [rbp+80h+var_F8]
0x180022b39  call    ?_GetDownloadedClients@EndpointManager@@AEAAAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@E@Z; EndpointManager::_GetDownloadedClients(uchar)
0x180022b3e  mov     rdi, rax
0x180022b41  lea     rax, [rsp+180h+var_140]
0x180022b46  cmp     rax, rdi
0x180022b49  jz      short loc_180022B81
0x180022b4b  mov     rbx, [rsp+180h+var_140]
0x180022b50  mov     r8, [rbx+8]
0x180022b54  lea     rdx, [rsp+180h+var_140]
0x180022b59  lea     rcx, [rsp+180h+var_140]
0x180022b5e  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *> *)
0x180022b63  mov     [rbx+8], rbx
0x180022b67  mov     [rbx], rbx
0x180022b6a  mov     [rbx+10h], rbx
0x180022b6e  mov     [rsp+180h+var_138], r14
0x180022b73  mov     rdx, rdi
0x180022b76  lea     rcx, [rsp+180h+var_140]
0x180022b7b  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>> const &)
0x180022b80  nop
0x180022b81  mov     rcx, [rbp+80h+var_F0]; this
0x180022b85  test    rcx, rcx
0x180022b88  jz      loc_180022C52
0x180022b8e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022b93  jmp     loc_180022C52
0x180022b98  mov     [rsp+180h+var_150], r14b
0x180022b9d  lea     rdx, [rsp+180h+var_150]
0x180022ba2  lea     rcx, [rsp+180h+var_148]
0x180022ba7  call    ??$make_unique@VEndpointManager@@_N$0A@@std@@YA?AV?$unique_ptr@VEndpointManager@@U?$default_delete@VEndpointManager@@@std@@@0@$$QEA_N@Z; std::make_unique<EndpointManager,bool,0>(bool &&)
0x180022bac  nop
0x180022bad  mov     rcx, [rsp+180h+var_148]
0x180022bb2  call    ?_GetFixedClients@EndpointManager@@AEAAAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@XZ; EndpointManager::_GetFixedClients(void)
0x180022bb7  mov     rdi, rax
0x180022bba  lea     rax, [rsp+180h+var_130]
0x180022bbf  cmp     rax, rdi
0x180022bc2  jz      short loc_180022BF9
0x180022bc4  mov     rbx, [rsp+180h+var_130]
0x180022bc9  mov     r8, [rbx+8]
0x180022bcd  lea     rdx, [rsp+180h+var_130]
0x180022bd2  lea     rcx, [rsp+180h+var_130]
0x180022bd7  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *> *)
0x180022bdc  mov     [rbx+8], rbx
0x180022be0  mov     [rbx], rbx
0x180022be3  mov     [rbx+10h], rbx
0x180022be7  mov     [rsp+180h+var_128], r14
0x180022bec  mov     rdx, rdi
0x180022bef  lea     rcx, [rsp+180h+var_130]
0x180022bf4  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>> const &)
0x180022bf9  xor     edx, edx
0x180022bfb  mov     rcx, [rsp+180h+var_148]
0x180022c00  call    ?_GetDownloadedClients@EndpointManager@@AEAAAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@E@Z; EndpointManager::_GetDownloadedClients(uchar)
0x180022c05  mov     rdi, rax
0x180022c08  lea     rax, [rsp+180h+var_140]
0x180022c0d  cmp     rax, rdi
0x180022c10  jz      short loc_180022C48
0x180022c12  mov     rbx, [rsp+180h+var_140]
0x180022c17  mov     r8, [rbx+8]
0x180022c1b  lea     rdx, [rsp+180h+var_140]
0x180022c20  lea     rcx, [rsp+180h+var_140]
0x180022c25  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>,void *> *)
0x180022c2a  mov     [rbx+8], rbx
0x180022c2e  mov     [rbx], rbx
0x180022c31  mov     [rbx+10h], rbx
0x180022c35  mov     [rsp+180h+var_138], r14
0x180022c3a  mov     rdx, rdi
0x180022c3d  lea     rcx, [rsp+180h+var_140]
0x180022c42  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>> const &)
0x180022c47  nop
0x180022c48  lea     rcx, [rsp+180h+var_148]
0x180022c4d  call    ??1?$unique_ptr@VEndpointManager@@U?$default_delete@VEndpointManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<EndpointManager>::~unique_ptr<EndpointManager>(void)
0x180022c52  lea     rcx, [rbp+80h+var_D0]
0x180022c56  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::shared_ptr<ClientEndpoint>>::map<std::wstring,std::shared_ptr<ClientEndpoint>>(void)
0x180022c5b  nop
0x180022c5c  lea     rdx, [rsp+180h+var_130]
0x180022c61  lea     rcx, [rbp+80h+var_D0]
0x180022c65  call    ??$merge@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@QEAAXAEAV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::merge<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>> &)
0x180022c6a  lea     rdx, [rsp+180h+var_140]
0x180022c6f  lea     rcx, [rbp+80h+var_D0]
0x180022c73  call    ??$merge@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@@2@$0A@@std@@@std@@QEAAXAEAV01@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>::merge<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<ClientEndpoint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>>,0>> &)
0x180022c78  lea     rcx, [rbp+80h+var_C0]
0x180022c7c  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180022c81  nop
0x180022c82  mov     rdx, [rbp+80h+var_D0]
0x180022c86  mov     rdx, [rdx]
0x180022c89  mov     [rsp+180h+var_120], rdx
0x180022c8e  cmp     [rdx+19h], r14b
0x180022c92  jnz     loc_180022D5D
0x180022c98  add     rdx, 20h ; ' '
0x180022c9c  lea     rcx, [rbp+80h+var_70]
0x180022ca0  call    ??0?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VClientEndpoint@@@2@@std@@QEAA@AEBU01@@Z; std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>::pair<std::wstring const,std::shared_ptr<ClientEndpoint>>(std::pair<std::wstring const,std::shared_ptr<ClientEndpoint>> const &)
0x180022ca5  nop
0x180022ca6  lea     rdx, [rbp+80h+var_E8]
0x180022caa  mov     rcx, [rbp+80h+var_50]
0x180022cae  call    ?GetPayloadHandler@ClientEndpoint@@QEBA?AV?$shared_ptr@VIPayloadHandler@@@std@@XZ; ClientEndpoint::GetPayloadHandler(void)
0x180022cb3  nop
0x180022cb4  mov     rcx, [rax]
0x180022cb7  mov     rax, [rcx]
0x180022cba  lea     rdx, [rbp+80h+var_90]
0x180022cbe  mov     rax, [rax+48h]
0x180022cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cc7  nop
0x180022cc8  mov     rcx, [rbp+80h+var_E0]; this
0x180022ccc  test    rcx, rcx
0x180022ccf  jz      short loc_180022CD6
0x180022cd1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180022cd6  cmp     [rbp+80h+var_80], r14
0x180022cda  jz      short loc_180022D36
0x180022cdc  lea     rdx, [rbp+80h+var_90]
0x180022ce0  lea     rcx, [rbp+80h+var_B0]
0x180022ce4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022ce9  mov     rdx, rax
0x180022cec  lea     rcx, [rbp+80h+var_F8]
0x180022cf0  call    ?GetFlightIdsByType@FlightIdUtils@@YA?AV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; FlightIdUtils::GetFlightIdsByType(std::wstring)
0x180022cf5  nop
0x180022cf6  mov     rbx, [rbp+80h+var_F8]
0x180022cfa  mov     r8, [rbx]
0x180022cfd  mov     [rsp+180h+var_148], r8
0x180022d02  mov     rdi, [rbp+80h+var_C0]
0x180022d06  cmp     r8, rbx
0x180022d09  jz      short loc_180022D2C
0x180022d0b  add     r8, 20h ; ' '
0x180022d0f  mov     rdx, rdi
0x180022d12  lea     rcx, [rbp+80h+var_C0]
0x180022d16  call    ??$_Emplace_hint@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@QEAU21@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace_hint<std::wstring const &>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x180022d1b  lea     rcx, [rsp+180h+var_148]
0x180022d20  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180022d25  mov     r8, [rsp+180h+var_148]
0x180022d2a  jmp     short loc_180022D06
0x180022d2c  lea     rcx, [rbp+80h+var_F8]
0x180022d30  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180022d35  nop
0x180022d36  lea     rcx, [rbp+80h+var_90]
0x180022d3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d3f  nop
0x180022d40  lea     rcx, [rbp+80h+var_70]
0x180022d44  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>::~pair<std::wstring const,std::shared_ptr<CnsFlightState>>(void)
0x180022d49  lea     rcx, [rsp+180h+var_120]
0x180022d4e  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x180022d53  mov     rdx, [rsp+180h+var_120]
0x180022d58  jmp     loc_180022C8E
0x180022d5d  mov     [rbp+80h+var_100], r14
0x180022d61  lea     rax, [rbp+80h+var_100]
0x180022d65  mov     qword ptr [rsp+180h+ppv], rax; int
0x180022d6a  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x180022d71  xor     edx, edx; pUnkOuter
0x180022d73  lea     r8d, [rdx+1]; dwClsContext
0x180022d77  lea     rcx, CLSID_FlightClientAPI; rclsid
0x180022d7e  call    cs:__imp_CoCreateInstance
0x180022d84  mov     rcx, [rbp+88h]; this
0x180022d8b  test    eax, eax
0x180022d8d  js      loc_180022FD5
0x180022d93  xorps   xmm0, xmm0
0x180022d96  movdqu  xmmword ptr [rsp+180h+var_118], xmm0
0x180022d9c  mov     [rsp+180h+var_108], r14
0x180022da1  mov     rax, [rbp+80h+var_C0]
0x180022da5  mov     rax, [rax]
0x180022da8  mov     [rsp+180h+var_120], rax
0x180022dad  or      r15, 0FFFFFFFFFFFFFFFFh
0x180022db1  cmp     [rax+19h], r14b
0x180022db5  jnz     loc_180022F0D
0x180022dbb  lea     rsi, [rax+20h]
0x180022dbf  mov     [rsp+180h+var_148], r14
0x180022dc4  mov     r10, [rbp+80h+var_100]
0x180022dc8  mov     rax, [r10]
0x180022dcb  mov     r9, [rax+88h]
0x180022dd2  mov     [rsp+180h+var_148], r14
0x180022dd7  mov     rcx, rsi
0x180022dda  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022ddf  lea     r8, [rsp+180h+var_148]
0x180022de4  mov     rdx, rax
0x180022de7  mov     rcx, r10
0x180022dea  mov     rax, r9
0x180022ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022df2  mov     rcx, [rbp+88h]; this
0x180022df9  test    eax, eax
0x180022dfb  js      loc_180022FC0
0x180022e01  mov     [rbp+80h+var_E8], r14
0x180022e05  mov     [rbp+80h+var_E0], r14
0x180022e09  mov     [rbp+80h+var_D8], r14
0x180022e0d  mov     rdi, [rsp+180h+var_148]
0x180022e12  mov     rax, [rdi]
0x180022e15  mov     rbx, [rax+48h]
0x180022e19  lea     rcx, [rbp+80h+var_E8]
0x180022e1d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180022e22  mov     [rbp+80h+var_E0], r15
0x180022e26  mov     [rbp+80h+var_D8], r15
0x180022e2a  lea     r8, [rbp+80h+var_E8]
0x180022e2e  lea     rdx, aTriggered; "Triggered"
0x180022e35  mov     rcx, rdi
0x180022e38  mov     rax, rbx
0x180022e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e40  mov     rcx, [rbp+88h]; this
0x180022e47  test    eax, eax
0x180022e49  js      loc_180022FEA
0x180022e4f  mov     r8, r15
0x180022e52  lea     rdx, a1; "1"
0x180022e59  lea     rcx, [rbp+80h+var_E8]
0x180022e5d  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(ushort const *,unsigned __int64)
0x180022e62  mov     ebx, r14d
0x180022e65  cmp     eax, 2
0x180022e68  setz    bl
0x180022e6b  mov     rcx, rsi
0x180022e6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022e73  mov     rdx, rax
0x180022e76  lea     rcx, [rbp+80h+var_B0]
0x180022e7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180022e7f  mov     r11, rax
0x180022e82  xorps   xmm0, xmm0
0x180022e85  xor     eax, eax
0x180022e87  movups  xmmword ptr [rbp-0Ch], xmm0
0x180022e8b  mov     [rbp+80h+var_80+4], rax
0x180022e8f  mov     dword ptr [rbp+80h+var_90], ebx
0x180022e92  mov     rcx, r11
0x180022e95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180022e9a  mov     r8, rax; unsigned __int16 *
0x180022e9d  mov     edx, 0Ch; unsigned __int64
0x180022ea2  lea     rcx, [rbp+80h+var_90+4]; unsigned __int16 *
0x180022ea6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022eab  mov     rcx, r11
0x180022eae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022eb3  mov     rdx, [rsp+180h+var_118+8]
0x180022eb8  cmp     rdx, [rsp+180h+var_108]
0x180022ebd  jz      short loc_180022ED6
0x180022ebf  movups  xmm0, xmmword ptr [rbp+80h+var_90]
0x180022ec3  movups  xmmword ptr [rdx], xmm0
0x180022ec6  movups  xmm1, xmmword ptr [rbp+80h+var_90+0Ch]
0x180022eca  movups  xmmword ptr [rdx+0Ch], xmm1
0x180022ece  add     [rsp+180h+var_118+8], 1Ch
0x180022ed4  jmp     short loc_180022EE5
0x180022ed6  lea     r8, [rbp+80h+var_90]
0x180022eda  lea     rcx, [rsp+180h+var_118]
0x180022edf  call    ??$_Emplace_reallocate@UConfig@OneSettingsClientTelemetryCore@@@?$vector@UConfig@OneSettingsClientTelemetryCore@@V?$allocator@UConfig@OneSettingsClientTelemetryCore@@@std@@@std@@AEAAPEAUConfig@OneSettingsClientTelemetryCore@@QEAU23@$$QEAU23@@Z; std::vector<OneSettingsClientTelemetryCore::Config>::_Emplace_reallocate<OneSettingsClientTelemetryCore::Config>(OneSettingsClientTelemetryCore::Config * const,OneSettingsClientTelemetryCore::Config &&)
0x180022ee4  nop
0x180022ee5  lea     rcx, [rbp+80h+var_E8]
0x180022ee9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180022eee  nop
0x180022eef  lea     rcx, [rsp+180h+var_148]
0x180022ef4  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180022ef9  lea     rcx, [rsp+180h+var_120]
0x180022efe  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x180022f03  mov     rax, [rsp+180h+var_120]
0x180022f08  jmp     loc_180022DB1
0x180022f0d  mov     rcx, [rsp+180h+var_118+8]
0x180022f12  mov     rdx, [rsp+180h+var_118]; struct OneSettingsClientTelemetryCore::Config *
0x180022f17  sub     rcx, rdx
0x180022f1a  sar     rcx, 2
0x180022f1e  mov     rbx, 6DB6DB6DB6DB6DB7h
0x180022f28  imul    rcx, rbx; unsigned __int16
0x180022f2c  call    ?ReportAggregateStagingState@OneSettingsClientTelemetryCore@@SAXGPEAUConfig@1@@Z; OneSettingsClientTelemetryCore::ReportAggregateStagingState(ushort,OneSettingsClientTelemetryCore::Config *)
0x180022f31  nop
0x180022f32  mov     rcx, [rsp+180h+var_118]
0x180022f37  test    rcx, rcx
0x180022f3a  jz      short loc_180022F63
0x180022f3c  mov     rax, [rsp+180h+var_108]
0x180022f41  sub     rax, rcx
0x180022f44  sar     rax, 2
  ... truncated ...
```
