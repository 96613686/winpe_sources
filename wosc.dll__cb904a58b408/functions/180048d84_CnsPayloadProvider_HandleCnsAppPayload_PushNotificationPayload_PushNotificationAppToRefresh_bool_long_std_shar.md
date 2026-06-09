# CnsPayloadProvider::HandleCnsAppPayload(PushNotificationPayload &,PushNotificationAppToRefresh &,bool &,long (*)(std::shared_ptr<ClientState>,IPayloadHandler *,CnsFlightPayload &,bool &))

- ea: `0x180048d84`
- end: `0x1800492e3`
- name: `?HandleCnsAppPayload@CnsPayloadProvider@@AEAAJAEAUPushNotificationPayload@@AEAUPushNotificationAppToRefresh@@AEA_NP6AJV?$shared_ptr@VClientState@@@std@@PEAVIPayloadHandler@@AEAUCnsFlightPayload@@2@Z@Z`
- size: `1375`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800492fc`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x180009a60`
- `0x180009b4c`
- `0x180009fcc`
- `0x180009ff0`
- `0x18000a148`
- `0x18000a798`
- `0x18000a8f8`
- `0x18000a964`
- `0x1800101fc`
- `0x1800106c8`
- `0x1800116f8`
- `0x180011a44`
- `0x180014b2c`
- `0x180019e68`
- `0x18002a8c8`
- `0x180047d34`
- `0x1800481ec`
- `0x180048968`
- `0x180048d84`
- `0x1800499c8`
- `0x180049d40`
- `0x180049fe4`
- `0x18004a290`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180049170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049150`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049150`

## string_xrefs

- `0x1800491b7`: `OneSettingsTIP::reason::CompletedSuccessfully`
- `0x180049212`: `OneSettingsTIP::reason::CnsCompletedNoContent`
- `0x1800491f4`: `OneSettingsTIP::reason::CnsCompletedContentNotSupported`
- `0x1800491c6`: `OneSettingsTIP::reason::CnsCompletedNoChanges`

## pseudocode

```c
__int64 __fastcall CnsPayloadProvider::HandleCnsAppPayload(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  const char *v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, _QWORD); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 (__fastcall **v15)(_QWORD, GUID *, __int64 *); // rax
  int v16; // eax
  const char *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rsi
  __m128i si128; // xmm6
  HSTRING *v21; // rdi
  HSTRING v22; // rcx
  int CnsFlightPayloadFromKvp; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  char v29; // al
  HSTRING v30; // rdi
  int (__fastcall *v31)(HSTRING, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  const char *v33; // rdx
  char *v34; // rcx
  const char *v35; // rax
  __int64 v36; // r8
  __int64 v37; // rdx
  HSTRING v38; // r10
  HSTRING v39; // rcx
  const char *v40; // rax
  __int64 v41; // rdx
  int v43; // [rsp+28h] [rbp-E0h]
  int v44; // [rsp+28h] [rbp-E0h]
  int v45[2]; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+68h] [rbp-A0h] BYREF
  void **v52; // [rsp+78h] [rbp-90h] BYREF
  char v53[48]; // [rsp+80h] [rbp-88h] BYREF
  HSTRING v54; // [rsp+B0h] [rbp-58h]
  char v55[8]; // [rsp+B8h] [rbp-50h] BYREF
  int v56; // [rsp+C0h] [rbp-48h]
  _BYTE v57[16]; // [rsp+D0h] [rbp-38h] BYREF
  char v58[16]; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-18h] BYREF
  int v60; // [rsp+F8h] [rbp-10h]
  __int64 v61; // [rsp+100h] [rbp-8h]
  _BYTE v62[16]; // [rsp+118h] [rbp+10h] BYREF
  __int128 v63; // [rsp+128h] [rbp+20h]
  __m128i v64; // [rsp+138h] [rbp+30h]
  __int128 v65; // [rsp+148h] [rbp+40h]
  __m128i v66; // [rsp+158h] [rbp+50h]
  _OWORD v67[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v68; // [rsp+188h] [rbp+80h]
  __m128i v69; // [rsp+198h] [rbp+90h]
  _OWORD v70[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+230h] [rbp+128h]

  string = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsAppPayload_attributes,tip2::test_data_basic>>::start(
    &string,
    v57);
  v52 = &tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v53,
    (struct wil::details::IFailureCallback *)&v52,
    0,
    1);
  v54 = string;
  if ( string )
    _InterlockedAdd((volatile signed __int32 *)string + 84, 1u);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&string);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl) )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 32);
    tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
      &v52,
      "MsgId='%ws'",
      v8);
  }
  v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
    &v52,
    "AppId='%ws'",
    v9);
  *a4 = 0;
  v47 = 0;
  v11 = *(_QWORD *)(a3 + 72);
  if ( !v11
    || (v12 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL),
        wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(&v47),
        v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v59, &CnsPayloadProvider::s_tagCnsContent),
        v14 = v12(v11, *(_QWORD *)(v13 + 24), &v47),
        v14 == -2089484279) )
  {
    v40 = tip2::details::reason_string((tip2::details *)"OneSettingsTIP::reason::CnsCompletedNoContent", v10);
    LOBYTE(v41) = 1;
    tip2::details::shared_data<0,0,1>::complete_without_lock(v54 + 2, v41, 20, v40);
  }
  else
  {
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB4,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v14,
        v43);
    v48 = 0;
    v15 = *v47;
    v48 = 0;
    v16 = (*v15)(v47, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, &v48);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
        (const char *)(unsigned int)v16,
        v43);
    v18 = *(_QWORD *)(a1 + 8);
    v19 = *(_QWORD *)(v18 + 288);
    if ( !v19 || (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v19 + 64LL))(*(_QWORD *)(v18 + 288)) )
    {
      v35 = tip2::details::reason_string(
              (tip2::details *)"OneSettingsTIP::reason::CnsCompletedContentNotSupported",
              v17);
      v36 = 21;
      v39 = v54 + 2;
      LOBYTE(v37) = 2;
    }
    else
    {
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(
        v55,
        v48);
      v59 = 0;
      v60 = -1;
      v61 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      while ( v56 != -1 )
      {
        v21 = (HSTRING *)wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(v55);
        v63 = 0;
        v64 = si128;
        LOWORD(v63) = 0;
        v65 = 0;
        v66 = si128;
        LOWORD(v65) = 0;
        v67[0] = 0;
        v67[1] = si128;
        LOWORD(v67[0]) = 0;
        v68 = 0;
        v69 = si128;
        LOWORD(v68) = 0;
        v70[0] = 0;
        v70[1] = si128;
        LOWORD(v70[0]) = 0;
        LOBYTE(v45[0]) = 0;
        v22 = *v21;
        string = v22;
        if ( v22 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v22 + 8LL))(v22);
        CnsFlightPayloadFromKvp = CnsPayloadProvider::GetCnsFlightPayloadFromKvp(
                                    a2,
                                    a3,
                                    (unsigned int)&string,
                                    (unsigned int)v62,
                                    (__int64)v45);
        if ( CnsFlightPayloadFromKvp < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCC,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
            (const char *)(unsigned int)CnsFlightPayloadFromKvp,
            v44);
        if ( LOBYTE(v45[0]) )
        {
          LOBYTE(v45[0]) = 0;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl) )
          {
            v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67);
            tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
              &v52,
              "Storing payloadKey='%ws'",
              v24);
            v25 = std::shared_ptr<ClientEndpoint>::shared_ptr<ClientEndpoint>(v58, a1 + 8);
            v26 = CnsPayloadProvider::StoreOneFlightPayloadCallback(v25, v19, v62, v45);
            if ( v26 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xD3,
                (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
                (const char *)(unsigned int)v26,
                v44);
            string = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v70);
            v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v67);
            v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
            v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 32);
            OneSettingsClientTelemetry::WnsCnsAppFlightPayloadStored<unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *>(
              &v49,
              &v51,
              &v50,
              &string);
          }
          else
          {
            v27 = std::shared_ptr<ClientEndpoint>::shared_ptr<ClientEndpoint>(v57, a1 + 8);
            v28 = CnsPayloadProvider::StoreOneFlightPayloadCallback(v27, v19, v62, v45);
            if ( v28 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0xDC,
                (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\cnspayloadprovider.cpp",
                (const char *)(unsigned int)v28,
                v44);
          }
          if ( *a4 || (v29 = 0, LOBYTE(v45[0])) )
            v29 = 1;
          *a4 = v29;
        }
        else
        {
          string = 0;
          v30 = *v21;
          v31 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v30 + 48LL);
          WindowsDeleteString(0);
          string = 0;
          if ( v31(v30, &string) >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(
              &v52,
              "Key '%ws' no payload found",
              StringRawBuffer);
          }
          WindowsDeleteString(string);
        }
        CnsFlightPayload::~CnsFlightPayload((CnsFlightPayload *)v62);
        wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator++(v55);
      }
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(&v59);
      wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(v55);
      if ( *a4 )
      {
        ClientState::SaveCnsState(*(ClientState **)(a1 + 8), 0);
        v34 = "OneSettingsTIP::reason::CompletedSuccessfully";
      }
      else
      {
        v34 = "OneSettingsTIP::reason::CnsCompletedNoChanges";
      }
      v35 = tip2::details::reason_string((tip2::details *)v34, v33);
      LOBYTE(v37) = 1;
      v39 = v38;
    }
    tip2::details::shared_data<0,0,1>::complete_without_lock(v39, v37, v36, v35);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v48);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v47);
  tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(&v52);
  return 0;
}

```

## disassembly

```asm
0x180048d84  mov     rax, rsp
0x180048d87  push    rbp
0x180048d88  push    rbx
0x180048d89  push    rsi
0x180048d8a  push    rdi
0x180048d8b  push    r12
0x180048d8d  push    r13
0x180048d8f  push    r14
0x180048d91  push    r15
0x180048d93  lea     rbp, [rax-128h]
0x180048d9a  sub     rsp, 1E8h
0x180048da1  movaps  xmmword ptr [rax-58h], xmm6
0x180048da5  mov     rax, cs:__security_cookie
0x180048dac  xor     rax, rsp
0x180048daf  mov     [rbp+120h+var_60], rax
0x180048db6  mov     r14, r9
0x180048db9  mov     r13, r8
0x180048dbc  mov     r12, rdx
0x180048dbf  mov     r15, rcx
0x180048dc2  xor     ebx, ebx
0x180048dc4  mov     [rsp+220h+string], rbx
0x180048dc9  lea     rdx, [rbp+120h+var_158]
0x180048dcd  lea     rcx, [rsp+220h+string]
0x180048dd2  call    ?start@?$tip_test@V?$merged_data@U_tip_WOSC_TIP_HandleCnsAppPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsAppPayload_attributes,tip2::test_data_basic>>::start(void)
0x180048dd7  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettingsCtacOverrides_attributes,tip2::test_data_basic>>::`vftable'
0x180048dde  mov     [rsp+220h+var_1B0], rax
0x180048de3  lea     esi, [rbx+1]
0x180048de6  mov     r9b, sil; bool
0x180048de9  xor     r8d, r8d; struct wil::CallContextInfo *
0x180048dec  lea     rdx, [rsp+220h+var_1B0]; struct wil::details::IFailureCallback *
0x180048df1  lea     rcx, [rsp+220h+var_1A8]; this
0x180048df6  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180048dfb  mov     rax, [rsp+220h+string]
0x180048e00  mov     [rbp+120h+var_178], rax
0x180048e04  test    rax, rax
0x180048e07  jz      short loc_180048E10
0x180048e09  lock add [rax+150h], esi
0x180048e10  lea     rcx, [rsp+220h+string]
0x180048e15  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x180048e1a  nop
0x180048e1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x180048e22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x180048e27  test    al, al
0x180048e29  jz      short loc_180048E49
0x180048e2b  lea     rcx, [r12+20h]
0x180048e30  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048e35  mov     r8, rax
0x180048e38  lea     rdx, aMsgidWs; "MsgId='%ws'"
0x180048e3f  lea     rcx, [rsp+220h+var_1B0]
0x180048e44  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x180048e49  mov     rcx, r13
0x180048e4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048e51  mov     r8, rax
0x180048e54  lea     rdx, aAppidWs; "AppId='%ws'"
0x180048e5b  lea     rcx, [rsp+220h+var_1B0]
0x180048e60  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x180048e65  mov     [r14], bl
0x180048e68  mov     [rsp+220h+var_1E0], rbx
0x180048e6d  mov     rdi, [r13+48h]
0x180048e71  test    rdi, rdi
0x180048e74  jz      loc_180049212
0x180048e7a  mov     rax, [rdi]
0x180048e7d  mov     rbx, [rax+40h]
0x180048e81  lea     rcx, [rsp+220h+var_1E0]
0x180048e86  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x180048e8b  lea     rdx, ?s_tagCnsContent@CnsPayloadProvider@@0QEBGEB; ushort const * const CnsPayloadProvider::s_tagCnsContent
0x180048e92  lea     rcx, [rbp+120h+var_138]
0x180048e96  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180048e9b  nop
0x180048e9c  lea     r8, [rsp+220h+var_1E0]
0x180048ea1  mov     rdx, [rax+18h]
0x180048ea5  mov     rcx, rdi
0x180048ea8  mov     rax, rbx
0x180048eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048eb0  nop
0x180048eb1  cmp     eax, 83750009h
0x180048eb6  jz      loc_180049212
0x180048ebc  mov     rcx, [rbp+128h]; this
0x180048ec3  xor     ebx, ebx
0x180048ec5  test    eax, eax
0x180048ec7  js      loc_18004928F
0x180048ecd  mov     [rsp+220h+var_1D8], rbx
0x180048ed2  mov     rcx, [rsp+220h+var_1E0]
0x180048ed7  mov     rax, [rcx]
0x180048eda  mov     [rsp+220h+var_1D8], rbx
0x180048edf  lea     r8, [rsp+220h+var_1D8]
0x180048ee4  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x180048eeb  mov     rax, [rax]
0x180048eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ef3  mov     rcx, [rbp+128h]; this
0x180048efa  test    eax, eax
0x180048efc  js      loc_1800492A4
0x180048f02  mov     rax, [r15+8]
0x180048f06  mov     rsi, [rax+120h]
0x180048f0d  test    rsi, rsi
0x180048f10  jz      loc_1800491F4
0x180048f16  mov     rax, [rsi]
0x180048f19  mov     rcx, rsi
0x180048f1c  mov     rax, [rax+40h]
0x180048f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f25  test    eax, eax
0x180048f27  jnz     loc_1800491F4
0x180048f2d  mov     rdx, [rsp+220h+var_1D8]
0x180048f32  lea     rcx, [rbp+120h+var_170]
0x180048f36  call    ??0iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAU?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@Z; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::iterable_iterator(Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *> *)
0x180048f3b  nop
0x180048f3c  mov     [rbp+120h+var_138], rbx
0x180048f40  mov     [rbp+120h+var_130], 0FFFFFFFFh
0x180048f47  mov     [rbp+120h+var_128], rbx
0x180048f4b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180048f53  cmp     [rbp+120h+var_168], 0FFFFFFFFh
0x180048f57  jz      loc_18004918E
0x180048f5d  lea     rcx, [rbp+120h+var_170]
0x180048f61  call    ??Diterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator*(void)
0x180048f66  mov     rdi, rax
0x180048f69  xorps   xmm0, xmm0
0x180048f6c  movups  [rbp+120h+var_100], xmm0
0x180048f70  movdqa  [rbp+120h+var_F0], xmm6
0x180048f75  mov     word ptr [rbp+120h+var_100], bx
0x180048f79  movups  [rbp+120h+var_E0], xmm0
0x180048f7d  movdqa  [rbp+120h+var_D0], xmm6
0x180048f82  mov     word ptr [rbp+120h+var_E0], bx
0x180048f86  movups  [rbp+120h+var_C0], xmm0
0x180048f8a  movdqa  [rbp+120h+var_B0], xmm6
0x180048f8f  mov     word ptr [rbp+120h+var_C0], bx
0x180048f93  movups  [rbp+120h+var_A0], xmm0
0x180048f9a  movdqa  [rbp+120h+var_90], xmm6
0x180048fa2  mov     word ptr [rbp+120h+var_A0], bx
0x180048fa9  movups  [rbp+120h+var_80], xmm0
0x180048fb0  movdqa  [rbp+120h+var_70], xmm6
0x180048fb8  mov     word ptr [rbp+120h+var_80], bx
0x180048fbf  mov     byte ptr [rsp+220h+var_1F0], bl
0x180048fc3  mov     rcx, [rax]
0x180048fc6  mov     [rsp+220h+string], rcx
0x180048fcb  test    rcx, rcx
0x180048fce  jz      short loc_180048FDD
0x180048fd0  mov     rax, [rcx]
0x180048fd3  mov     rax, [rax+8]
0x180048fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fdc  nop
0x180048fdd  lea     rax, [rsp+220h+var_1F0]
0x180048fe2  mov     [rsp+20h], rax; int
0x180048fe7  lea     r9, [rbp+120h+var_110]
0x180048feb  lea     r8, [rsp+220h+string]
0x180048ff0  mov     rdx, r13
0x180048ff3  mov     rcx, r12
0x180048ff6  call    ?GetCnsFlightPayloadFromKvp@CnsPayloadProvider@@CAJAEAUPushNotificationPayload@@AEAUPushNotificationAppToRefresh@@V?$ComPtr@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEAUCnsFlightPayload@@AEA_N@Z; CnsPayloadProvider::GetCnsFlightPayloadFromKvp(PushNotificationPayload &,PushNotificationAppToRefresh &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *>>,CnsFlightPayload &,bool &)
0x180048ffb  mov     rcx, [rbp+128h]; this
0x180049002  test    eax, eax
0x180049004  js      loc_18004927A
0x18004900a  cmp     byte ptr [rsp+220h+var_1F0], bl
0x18004900e  jz      loc_180049113
0x180049014  mov     byte ptr [rsp+220h+var_1F0], bl
0x180049018  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x18004901f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x180049024  test    al, al
0x180049026  jz      loc_1800490CF
0x18004902c  lea     rcx, [rbp+120h+var_C0]
0x180049030  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049035  mov     r8, rax
0x180049038  lea     rdx, aStoringPayload; "Storing payloadKey='%ws'"
0x18004903f  lea     rcx, [rsp+220h+var_1B0]
0x180049044  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x180049049  lea     rdx, [r15+8]
0x18004904d  lea     rcx, [rbp+120h+var_148]
0x180049051  call    ??0?$shared_ptr@VClientEndpoint@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ClientEndpoint>::shared_ptr<ClientEndpoint>(std::shared_ptr<ClientEndpoint> const &)
0x180049056  lea     r9, [rsp+220h+var_1F0]
0x18004905b  lea     r8, [rbp+120h+var_110]
0x18004905f  mov     rdx, rsi
0x180049062  mov     rcx, rax
0x180049065  call    ?StoreOneFlightPayloadCallback@CnsPayloadProvider@@CAJV?$shared_ptr@VClientState@@@std@@PEAVIPayloadHandler@@AEAUCnsFlightPayload@@AEA_N@Z; CnsPayloadProvider::StoreOneFlightPayloadCallback(std::shared_ptr<ClientState>,IPayloadHandler *,CnsFlightPayload &,bool &)
0x18004906a  mov     rcx, [rbp+128h]; this
0x180049071  test    eax, eax
0x180049073  js      loc_1800492B9
0x180049079  lea     rcx, [rbp+120h+var_80]
0x180049080  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049085  mov     [rsp+220h+string], rax
0x18004908a  lea     rcx, [rbp+120h+var_C0]
0x18004908e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049093  mov     [rsp+220h+var_1C8], rax
0x180049098  mov     rcx, r13
0x18004909b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800490a0  mov     [rsp+220h+var_1C0], rax
0x1800490a5  lea     rcx, [r12+20h]
0x1800490aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800490af  mov     [rsp+220h+var_1D0], rax
0x1800490b4  lea     r9, [rsp+220h+string]
0x1800490b9  lea     r8, [rsp+220h+var_1C8]
0x1800490be  lea     rdx, [rsp+220h+var_1C0]
0x1800490c3  lea     rcx, [rsp+220h+var_1D0]
0x1800490c8  call    ??$WnsCnsAppFlightPayloadStored@PEBGPEBGPEBGPEBG@OneSettingsClientTelemetry@@SAX$$QEAPEBG000@Z; OneSettingsClientTelemetry::WnsCnsAppFlightPayloadStored<ushort const *,ushort const *,ushort const *,ushort const *>(ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&)
0x1800490cd  jmp     short loc_1800490FF
0x1800490cf  lea     rdx, [r15+8]
0x1800490d3  lea     rcx, [rbp+120h+var_158]
0x1800490d7  call    ??0?$shared_ptr@VClientEndpoint@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ClientEndpoint>::shared_ptr<ClientEndpoint>(std::shared_ptr<ClientEndpoint> const &)
0x1800490dc  lea     r9, [rsp+220h+var_1F0]
0x1800490e1  lea     r8, [rbp+120h+var_110]
0x1800490e5  mov     rdx, rsi
0x1800490e8  mov     rcx, rax
0x1800490eb  call    ?StoreOneFlightPayloadCallback@CnsPayloadProvider@@CAJV?$shared_ptr@VClientState@@@std@@PEAVIPayloadHandler@@AEAUCnsFlightPayload@@AEA_N@Z; CnsPayloadProvider::StoreOneFlightPayloadCallback(std::shared_ptr<ClientState>,IPayloadHandler *,CnsFlightPayload &,bool &)
0x1800490f0  mov     rcx, [rbp+128h]; this
0x1800490f7  test    eax, eax
0x1800490f9  js      loc_1800492CE
0x1800490ff  cmp     [r14], bl
0x180049102  jnz     short loc_18004910C
0x180049104  cmp     byte ptr [rsp+220h+var_1F0], bl
0x180049108  mov     al, bl
0x18004910a  jz      short loc_18004910E
0x18004910c  mov     al, 1
0x18004910e  mov     [r14], al
0x180049111  jmp     short loc_180049177
0x180049113  mov     [rsp+220h+string], rbx
0x180049118  mov     rdi, [rdi]
0x18004911b  mov     rax, [rdi]
0x18004911e  mov     rbx, [rax+30h]
0x180049122  xor     ecx, ecx; string
0x180049124  call    cs:__imp_WindowsDeleteString
0x18004912a  mov     [rsp+220h+string], 0
0x180049133  lea     rdx, [rsp+220h+string]
0x180049138  mov     rcx, rdi
0x18004913b  mov     rax, rbx
0x18004913e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049143  xor     ebx, ebx
0x180049145  test    eax, eax
0x180049147  js      short loc_18004916B
0x180049149  xor     edx, edx; length
0x18004914b  mov     rcx, [rsp+220h+string]; string
0x180049150  call    cs:__imp_WindowsGetStringRawBuffer
0x180049156  mov     r8, rax
0x180049159  lea     rdx, aKeyWsNoPayload; "Key '%ws' no payload found"
0x180049160  lea     rcx, [rsp+220h+var_1B0]
0x180049165  call    ?logf@?$test_watcher@V?$merged_data@U_tip_WOSC_TIP_HandleCnsPayload_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAAXPEBDZZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_TIP_HandleCnsPayload_attributes,tip2::test_data_basic>>::logf(char const *,...)
0x18004916a  nop
0x18004916b  mov     rcx, [rsp+220h+string]; string
0x180049170  call    cs:__imp_WindowsDeleteString
0x180049176  nop
0x180049177  lea     rcx, [rbp+120h+var_110]; this
0x18004917b  call    ??1CnsFlightPayload@@QEAA@XZ; CnsFlightPayload::~CnsFlightPayload(void)
0x180049180  lea     rcx, [rbp+120h+var_170]
0x180049184  call    ??Eiterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV012@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::operator++(void)
0x180049189  jmp     loc_180048F53
0x18004918e  lea     rcx, [rbp+120h+var_138]
0x180049192  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x180049197  nop
0x180049198  lea     rcx, [rbp+120h+var_170]
0x18004919c  call    ??1iterable_iterator@?$iterable_range@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::iterable_range<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *,wil::err_exception_policy>::iterable_iterator::~iterable_iterator(void)
0x1800491a1  cmp     [r14], bl
0x1800491a4  jz      short loc_1800491C0
0x1800491a6  xor     edx, edx; bool
0x1800491a8  mov     rcx, [r15+8]; this
0x1800491ac  call    ?SaveCnsState@ClientState@@QEAAX_N@Z; ClientState::SaveCnsState(bool)
0x1800491b1  mov     r8d, 1
0x1800491b7  lea     rcx, aOnesettingstip_2; "OneSettingsTIP::reason::CompletedSucces"...
0x1800491be  jmp     short loc_1800491CD
0x1800491c0  mov     r8d, 0Ah
0x1800491c6  lea     rcx, aOnesettingstip_4; "OneSettingsTIP::reason::CnsCompletedNoC"...
0x1800491cd  mov     r10, [rbp+120h+var_178]
0x1800491d1  add     r10, 8
0x1800491d5  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800491da  mov     dl, 1
0x1800491dc  mov     rcx, r10
0x1800491df  mov     r9, rax
0x1800491e2  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800491e7  nop
0x1800491e8  lea     rcx, [rsp+220h+var_1D8]
0x1800491ed  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x1800491f2  jmp     short loc_180049238
0x1800491f4  lea     rcx, aOnesettingstip_7; "OneSettingsTIP::reason::CnsCompletedCon"...
0x1800491fb  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180049200  mov     r8d, 15h
0x180049206  mov     rcx, [rbp+120h+var_178]
0x18004920a  add     rcx, 8
0x18004920e  mov     dl, 2
0x180049210  jmp     short loc_1800491DF
0x180049212  lea     rcx, aOnesettingstip_0; "OneSettingsTIP::reason::CnsCompletedNoC"...
0x180049219  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x18004921e  mov     r9, rax
0x180049221  mov     r8d, 14h
0x180049227  mov     rcx, [rbp+120h+var_178]
0x18004922b  add     rcx, 8
0x18004922f  mov     dl, sil
0x180049232  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180049237  nop
0x180049238  lea     rcx, [rsp+220h+var_1E0]
0x18004923d  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180049242  nop
0x180049243  lea     rcx, [rsp+220h+var_1B0]
0x180049248  call    ??1?$test_watcher@V?$merged_data@U_tip_WOSC_ForceRefreshOneSettings_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_WOSC_ForceRefreshOneSettings_attributes,tip2::test_data_basic>>(void)
0x18004924d  xor     eax, eax
0x18004924f  mov     rcx, [rbp+120h+var_60]
0x180049256  xor     rcx, rsp; StackCookie
0x180049259  call    __security_check_cookie
0x18004925e  movaps  xmm6, [rsp+220h+var_58+8]
0x180049266  add     rsp, 1E8h
0x18004926d  pop     r15
0x18004926f  pop     r14
0x180049271  pop     r13
0x180049273  pop     r12
0x180049275  pop     rdi
0x180049276  pop     rsi
  ... truncated ...
```
