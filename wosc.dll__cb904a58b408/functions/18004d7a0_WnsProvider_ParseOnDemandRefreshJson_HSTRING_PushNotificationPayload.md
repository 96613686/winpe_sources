# WnsProvider::ParseOnDemandRefreshJson(HSTRING__ *,PushNotificationPayload &)

- ea: `0x18004d7a0`
- end: `0x18004dd0b`
- name: `?ParseOnDemandRefreshJson@WnsProvider@@CA_NPEAUHSTRING__@@AEAUPushNotificationPayload@@@Z`
- size: `1387`
- prototype: `char __fastcall(HSTRING, struct PushNotificationPayload *)`
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c1fc`
- `0x18004dd14`

## callees

- `0x180003110`
- `0x180005f50`
- `0x180006b9c`
- `0x180009384`
- `0x180009fcc`
- `0x18000b0bc`
- `0x1800101fc`
- `0x180011a44`
- `0x180013620`
- `0x180019e68`
- `0x180020748`
- `0x180047e24`
- `0x180049d40`
- `0x18004acac`
- `0x18004ae40`
- `0x18004aeb0`
- `0x18004af38`
- `0x18004b0c4`
- `0x18004b288`
- `0x18004b5fc`
- `0x18004b710`
- `0x18004b840`
- `0x18004c0c4`
- `0x18004d2c8`
- `0x18004d7a0`
- `0x18004ec0c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d9ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d9ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004daca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d987`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004daca`

## string_xrefs

- `0x18004dcf9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004d7e9`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
char __fastcall WnsProvider::ParseOnDemandRefreshJson(HSTRING a1, struct PushNotificationPayload *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING, __int64 *, __int64 *); // rbx
  int v7; // eax
  _DWORD *v8; // rbx
  __int64 v10; // rax
  int refreshed; // r12d
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v14; // rax
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // r14d
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, _QWORD); // rbx
  __int64 v22; // rax
  char v23; // si
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v26; // rax
  int v27; // eax
  PCWSTR v28; // rax
  __int64 v29; // r8
  int v30; // eax
  __m128i si128; // xmm6
  int i; // eax
  __int64 v33; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, HSTRING *); // rbx
  int v36; // eax
  __int64 v37; // rax
  unsigned int v38; // eax
  int v39; // [rsp+28h] [rbp-E0h]
  __int64 v40; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C8h] BYREF
  UINT32 length[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v44; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+68h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, HSTRING *); // [rsp+70h] [rbp-98h] BYREF
  HSTRING v48; // [rsp+78h] [rbp-90h] BYREF
  HSTRING v49; // [rsp+80h] [rbp-88h] BYREF
  int v50; // [rsp+88h] [rbp-80h]
  __int64 v51; // [rsp+90h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-70h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-58h]
  _OWORD v54[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v55; // [rsp+D8h] [rbp-30h]
  __m128i v56; // [rsp+E8h] [rbp-20h]
  int v57; // [rsp+F8h] [rbp-10h]
  __int64 v58; // [rsp+100h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v46 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v53,
         &v46);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36E,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
      (const char *)(unsigned int)v4,
      v39);
  v43 = 0;
  LOBYTE(v40) = 0;
  v5 = v46;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *, __int64 *))(*(_QWORD *)v46 + 56LL);
  wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(&v43);
  v7 = v6(v5, a1, &v43, &v40);
  LODWORD(v45) = v7;
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x374,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
      (const char *)(unsigned int)v7,
      v39);
  v8 = (_DWORD *)((char *)a2 + 64);
  if ( !(_BYTE)v40 )
  {
    *(_BYTE *)a2 = 0;
    *v8 = -1;
    *((_QWORD *)a2 + 6) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32) = 0;
    OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,unsigned short const (&)[8]>(&v45);
LABEL_5:
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v43);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    return 0;
  }
  v10 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
          &v44,
          &v43);
  refreshed = WnsProvider::GetOnDemandRefreshJsonVersion(v10);
  *(_BYTE *)a2 = 0;
  *v8 = refreshed;
  *((_QWORD *)a2 + 6) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)a2 + 32) = 0;
  length[0] = 10;
  OneSettingsClientTelemetry::WnsPushNotificationPayloadVersion<int &,int>((char *)a2 + 64, length);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl'::`2'::impl) )
  {
    string = 0;
    length[0] = 0;
    v12 = v43;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v43 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &WnsProvider::s_tagMsgId);
    v15 = v13(v12, *(_QWORD *)(v14 + 24), &string);
    LODWORD(v45) = v15;
    if ( v15 < 0 )
    {
      if ( v15 != -2089484279 )
      {
        OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,unsigned short const * const &>(
          &v45,
          &WnsProvider::s_tagMsgId);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_5;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, length);
      v17 = -1;
      do
        ++v17;
      while ( StringRawBuffer[v17] );
      std::wstring::_Assign<unsigned short>((char *)a2 + 32, StringRawBuffer);
    }
    WindowsDeleteString(string);
  }
  else
  {
    v44 = 0;
    LODWORD(string) = 0;
    v24 = v43;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v43 + 80LL);
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &WnsProvider::s_tagMsgId);
    v27 = v25(v24, *(_QWORD *)(v26 + 24), &v44);
    LODWORD(v45) = v27;
    if ( v27 < 0 )
    {
      if ( v27 != -2089484279 )
      {
        OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,unsigned short const * const &>(
          &v45,
          &WnsProvider::s_tagMsgId);
        v23 = 0;
        goto LABEL_16;
      }
    }
    else
    {
      v28 = WindowsGetStringRawBuffer(v44, (UINT32 *)&string);
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      std::wstring::_Assign<unsigned short>((char *)a2 + 32, v28);
    }
  }
  v19 = 0;
  length[0] = 0;
  if ( refreshed == -1 )
    goto LABEL_5;
  if ( refreshed )
  {
    v38 = wil::verify_hresult<long>(2147549183LL, v18);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3DB,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
      (const char *)v38,
      v39);
  }
  v47 = 0;
  v20 = v43;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 72LL);
  v47 = 0;
  v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &WnsProvider::s_tagAppsArray);
  LODWORD(v45) = v21(v20, *(_QWORD *)(v22 + 24), &v47);
  if ( (int)v45 >= 0 )
  {
    v48 = 0;
    v30 = (**v47)(v47, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v48);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v30,
        v39);
    v44 = v48;
    v49 = v48;
    v50 = 0;
    v51 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::end(
      &v44,
      &hstringHeader);
    v23 = 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    for ( i = v50; i != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; i = ++v50 )
    {
      v33 = wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::vector_iterator::operator*(&v49);
      string = 0;
      v34 = *(_QWORD *)v33;
      v35 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v33 + 96LL);
      wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(&string);
      v36 = v35(v34, &string);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3C0,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\wnsprovider\\wnsprovider.cpp",
          (const char *)(unsigned int)v36,
          v39);
      v54[0] = 0;
      v54[1] = si128;
      LOWORD(v54[0]) = 0;
      v55 = 0;
      v56 = si128;
      LOWORD(v55) = 0;
      v57 = 0;
      v58 = 0;
      v37 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
              &v44,
              &string);
      if ( (unsigned __int8)WnsProvider::ParseAppToRefresh(v37, v54) )
      {
        if ( *((_QWORD *)a2 + 2) == *((_QWORD *)a2 + 3) )
        {
          std::vector<PushNotificationAppToRefresh>::_Emplace_reallocate<PushNotificationAppToRefresh const &>(
            (char *)a2 + 8,
            *((_QWORD *)a2 + 2),
            v54);
        }
        else
        {
          PushNotificationAppToRefresh::PushNotificationAppToRefresh(
            *((PushNotificationAppToRefresh **)a2 + 2),
            (const struct PushNotificationAppToRefresh *)v54);
          *((_QWORD *)a2 + 2) += 80LL;
        }
        *(_BYTE *)a2 = 1;
        length[0] = ++v19;
      }
      PushNotificationAppToRefresh::~PushNotificationAppToRefresh((PushNotificationAppToRefresh *)v54);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&string);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v48);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v47);
    OneSettingsClientTelemetry::WnsPushNotificationPayloadAppCount<unsigned long &>(length);
  }
  else
  {
    OneSettingsClientTelemetry::WnsPushNotificationPayloadMissingAppsArray<long &>(&v45);
    wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v47);
    v23 = 1;
  }
LABEL_16:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v43);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  return v23;
}

```

## disassembly

```asm
0x18004d7a0  mov     rax, rsp
0x18004d7a3  mov     [rax+18h], rbx
0x18004d7a7  push    rbp
0x18004d7a8  push    rsi
0x18004d7a9  push    rdi
0x18004d7aa  push    r12
0x18004d7ac  push    r13
0x18004d7ae  push    r14
0x18004d7b0  push    r15
0x18004d7b2  lea     rbp, [rax-58h]
0x18004d7b6  sub     rsp, 120h
0x18004d7bd  movaps  xmmword ptr [rax-48h], xmm6
0x18004d7c1  mov     rax, cs:__security_cookie
0x18004d7c8  xor     rax, rsp
0x18004d7cb  mov     [rbp+50h+var_50], rax
0x18004d7cf  mov     r15, rdx
0x18004d7d2  mov     rsi, rcx
0x18004d7d5  xor     r13d, r13d
0x18004d7d8  mov     [rsp+150h+var_F0], r13
0x18004d7dd  mov     [rbp+50h+var_A8], r13
0x18004d7e1  lea     r9d, [r13+1Ch]; unsigned int
0x18004d7e5  lea     r8d, [r13+1Dh]; unsigned int
0x18004d7e9  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18004d7f0  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x18004d7f4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004d7f9  lea     rdx, [rsp+150h+var_F0]
0x18004d7fe  mov     rcx, [rbp+50h+var_A8]
0x18004d802  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x18004d807  mov     rcx, [rbp+58h]; this
0x18004d80b  test    eax, eax
0x18004d80d  js      loc_18004DCA9
0x18004d813  mov     [rsp+150h+var_108], r13
0x18004d818  mov     byte ptr [rsp+150h+var_120], r13b
0x18004d81d  mov     rdi, [rsp+150h+var_F0]
0x18004d822  mov     rax, [rdi]
0x18004d825  mov     rbx, [rax+38h]
0x18004d829  lea     rcx, [rsp+150h+var_108]
0x18004d82e  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x18004d833  lea     r9, [rsp+150h+var_120]
0x18004d838  lea     r8, [rsp+150h+var_108]
0x18004d83d  mov     rdx, rsi
0x18004d840  mov     rcx, rdi
0x18004d843  mov     rax, rbx
0x18004d846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d84b  mov     dword ptr [rsp+150h+var_F8], eax
0x18004d84f  mov     rcx, [rbp+58h]; this
0x18004d853  test    eax, eax
0x18004d855  js      loc_18004DCBE
0x18004d85b  lea     rbx, [r15+40h]
0x18004d85f  lea     rsi, [r15+20h]
0x18004d863  cmp     byte ptr [rsp+150h+var_120], r13b
0x18004d868  jnz     short loc_18004D8D1
0x18004d86a  mov     [r15], r13b
0x18004d86d  mov     dword ptr [rbx], 0FFFFFFFFh
0x18004d873  mov     [rsi+10h], r13
0x18004d877  mov     rcx, rsi
0x18004d87a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d87f  mov     [rax], r13w
0x18004d883  lea     rcx, [rsp+150h+var_F8]
0x18004d888  call    ??$WnsPushNotificationPayloadParsingFailed@AEAJAEAY07$$CBG@OneSettingsClientTelemetry@@SAXAEAJAEAY07$$CBG@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,ushort const (&)[8]>(long &,ushort const (&)[8])
0x18004d88d  nop
0x18004d88e  lea     rcx, [rsp+150h+var_108]
0x18004d893  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004d898  nop
0x18004d899  lea     rcx, [rsp+150h+var_F0]
0x18004d89e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8a3  xor     al, al
0x18004d8a5  mov     rcx, [rbp+50h+var_50]
0x18004d8a9  xor     rcx, rsp; StackCookie
0x18004d8ac  call    __security_check_cookie
0x18004d8b1  lea     r11, [rsp+150h+var_30]
0x18004d8b9  mov     rbx, [r11+50h]
0x18004d8bd  movaps  xmm6, xmmword ptr [r11-10h]
0x18004d8c2  mov     rsp, r11
0x18004d8c5  pop     r15
0x18004d8c7  pop     r14
0x18004d8c9  pop     r13
0x18004d8cb  pop     r12
0x18004d8cd  pop     rdi
0x18004d8ce  pop     rsi
0x18004d8cf  pop     rbp
0x18004d8d0  retn
0x18004d8d1  lea     rdx, [rsp+150h+var_108]
0x18004d8d6  lea     rcx, [rsp+150h+var_100]
0x18004d8db  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18004d8e0  mov     rcx, rax
0x18004d8e3  call    ?GetOnDemandRefreshJsonVersion@WnsProvider@@CA?AW4WnsPayloadVersion@@V?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@@Z; WnsProvider::GetOnDemandRefreshJsonVersion(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>)
0x18004d8e8  mov     r12d, eax
0x18004d8eb  mov     [r15], r13b
0x18004d8ee  mov     [rbx], eax
0x18004d8f0  mov     [rsi+10h], r13
0x18004d8f4  mov     rcx, rsi
0x18004d8f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d8fc  mov     [rax], r13w
0x18004d900  mov     [rsp+150h+length], 0Ah
0x18004d908  lea     rdx, [rsp+150h+length]
0x18004d90d  mov     rcx, rbx
0x18004d910  call    ??$WnsPushNotificationPayloadVersion@AEAHH@OneSettingsClientTelemetry@@SAXAEAH$$QEAH@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadVersion<int &,int>(int &,int &&)
0x18004d915  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::GetImpl(void)'::`2'::impl
0x18004d91c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationCleared>::__private_IsEnabled(void)
0x18004d921  test    al, al
0x18004d923  jz      loc_18004DA7D
0x18004d929  mov     [rsp+150h+string], r13
0x18004d92e  mov     [rsp+150h+length], r13d
0x18004d933  mov     rdi, [rsp+150h+var_108]
0x18004d938  mov     rax, [rdi]
0x18004d93b  mov     rbx, [rax+50h]
0x18004d93f  xor     ecx, ecx; string
0x18004d941  call    cs:__imp_WindowsDeleteString
0x18004d947  mov     [rsp+150h+string], r13
0x18004d94c  lea     rdx, ?s_tagMsgId@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagMsgId
0x18004d953  lea     rcx, [rbp+50h+hstringHeader]
0x18004d957  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d95c  nop
0x18004d95d  lea     r8, [rsp+150h+string]
0x18004d962  mov     rdx, [rax+18h]
0x18004d966  mov     rcx, rdi
0x18004d969  mov     rax, rbx
0x18004d96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d971  mov     dword ptr [rsp+150h+var_F8], eax
0x18004d975  test    eax, eax
0x18004d977  js      loc_18004DA4B
0x18004d97d  lea     rdx, [rsp+150h+length]; length
0x18004d982  mov     rcx, [rsp+150h+string]; string
0x18004d987  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d98d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004d991  inc     r8
0x18004d994  cmp     [rax+r8*2], r13w
0x18004d999  jnz     short loc_18004D991
0x18004d99b  mov     rdx, rax
0x18004d99e  mov     rcx, rsi
0x18004d9a1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d9a6  nop
0x18004d9a7  mov     rcx, [rsp+150h+string]; string
0x18004d9ac  call    cs:__imp_WindowsDeleteString
0x18004d9b2  mov     r14d, r13d
0x18004d9b5  mov     [rsp+150h+length], r13d
0x18004d9ba  cmp     r12d, 0FFFFFFFFh
0x18004d9be  jz      loc_18004D88E
0x18004d9c4  test    r12d, r12d
0x18004d9c7  jnz     loc_18004DCD3
0x18004d9cd  mov     [rsp+150h+var_E8], r13
0x18004d9d2  mov     rdi, [rsp+150h+var_108]
0x18004d9d7  mov     rax, [rdi]
0x18004d9da  mov     rbx, [rax+48h]
0x18004d9de  mov     [rsp+150h+var_E8], r13
0x18004d9e3  lea     rdx, ?s_tagAppsArray@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppsArray
0x18004d9ea  lea     rcx, [rbp+50h+hstringHeader]
0x18004d9ee  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d9f3  nop
0x18004d9f4  lea     r8, [rsp+150h+var_E8]
0x18004d9f9  mov     rdx, [rax+18h]
0x18004d9fd  mov     rcx, rdi
0x18004da00  mov     rax, rbx
0x18004da03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004da08  mov     dword ptr [rsp+150h+var_F8], eax
0x18004da0c  test    eax, eax
0x18004da0e  jns     loc_18004DB12
0x18004da14  lea     rcx, [rsp+150h+var_F8]
0x18004da19  call    ??$WnsPushNotificationPayloadMissingAppsArray@AEAJ@OneSettingsClientTelemetry@@SAXAEAJ@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadMissingAppsArray<long &>(long &)
0x18004da1e  nop
0x18004da1f  lea     rcx, [rsp+150h+var_E8]
0x18004da24  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004da29  mov     esi, 1
0x18004da2e  lea     rcx, [rsp+150h+var_108]
0x18004da33  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004da38  nop
0x18004da39  lea     rcx, [rsp+150h+var_F0]
0x18004da3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004da43  mov     al, sil
0x18004da46  jmp     loc_18004D8A5
0x18004da4b  cmp     eax, 83750009h
0x18004da50  jz      loc_18004D9A7
0x18004da56  lea     rdx, ?s_tagMsgId@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagMsgId
0x18004da5d  lea     rcx, [rsp+150h+var_F8]
0x18004da62  call    ??$WnsPushNotificationPayloadParsingFailed@AEAJAEBQEBG@OneSettingsClientTelemetry@@SAXAEAJAEBQEBG@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,ushort const * const &>(long &,ushort const * const &)
0x18004da67  nop
0x18004da68  mov     rcx, [rsp+150h+string]; string
0x18004da6d  call    cs:__imp_WindowsDeleteString
0x18004da73  mov     [rsp+150h+string], r13
0x18004da78  jmp     loc_18004D88E
0x18004da7d  mov     [rsp+150h+var_100], r13
0x18004da82  mov     dword ptr [rsp+150h+string], r13d
0x18004da87  mov     rdi, [rsp+150h+var_108]
0x18004da8c  mov     rax, [rdi]
0x18004da8f  mov     rbx, [rax+50h]
0x18004da93  lea     rdx, ?s_tagMsgId@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagMsgId
0x18004da9a  lea     rcx, [rbp+50h+hstringHeader]
0x18004da9e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004daa3  nop
0x18004daa4  lea     r8, [rsp+150h+var_100]
0x18004daa9  mov     rdx, [rax+18h]
0x18004daad  mov     rcx, rdi
0x18004dab0  mov     rax, rbx
0x18004dab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dab8  mov     dword ptr [rsp+150h+var_F8], eax
0x18004dabc  test    eax, eax
0x18004dabe  js      short loc_18004DAEE
0x18004dac0  lea     rdx, [rsp+150h+string]; length
0x18004dac5  mov     rcx, [rsp+150h+var_100]; string
0x18004daca  call    cs:__imp_WindowsGetStringRawBuffer
0x18004dad0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004dad4  inc     r8
0x18004dad7  cmp     [rax+r8*2], r13w
0x18004dadc  jnz     short loc_18004DAD4
0x18004dade  mov     rdx, rax
0x18004dae1  mov     rcx, rsi
0x18004dae4  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004dae9  jmp     loc_18004D9B2
0x18004daee  cmp     eax, 83750009h
0x18004daf3  jz      loc_18004D9B2
0x18004daf9  lea     rdx, ?s_tagMsgId@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagMsgId
0x18004db00  lea     rcx, [rsp+150h+var_F8]
0x18004db05  call    ??$WnsPushNotificationPayloadParsingFailed@AEAJAEBQEBG@OneSettingsClientTelemetry@@SAXAEAJAEBQEBG@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,ushort const * const &>(long &,ushort const * const &)
0x18004db0a  mov     sil, r13b
0x18004db0d  jmp     loc_18004DA2E
0x18004db12  mov     rcx, [rsp+150h+var_E8]
0x18004db17  mov     [rsp+150h+var_E0], r13
0x18004db1c  mov     rax, [rcx]
0x18004db1f  lea     r8, [rsp+150h+var_E0]
0x18004db24  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x18004db2b  mov     rax, [rax]
0x18004db2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db33  mov     rcx, [rbp+58h]; this
0x18004db37  test    eax, eax
0x18004db39  js      loc_18004DCF6
0x18004db3f  mov     rax, [rsp+150h+var_E0]
0x18004db44  mov     [rsp+150h+var_100], rax
0x18004db49  mov     [rsp+150h+var_D8], rax
0x18004db4e  mov     [rbp+50h+var_D0], r13d
0x18004db52  mov     [rbp+50h+var_C8], r13
0x18004db56  lea     rdx, [rbp+50h+hstringHeader]
0x18004db5a  lea     rcx, [rsp+150h+var_100]
0x18004db5f  call    ?end@?$vector_range@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::end(void)
0x18004db64  nop
0x18004db65  mov     esi, 1
0x18004db6a  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18004db72  mov     eax, [rbp+50h+var_D0]
0x18004db75  cmp     eax, dword ptr [rbp+50h+hstringHeader.Reserved+8]
0x18004db78  jz      loc_18004DC5C
0x18004db7e  lea     rcx, [rsp+150h+var_D8]
0x18004db83  call    ??Dvector_iterator@?$vector_range@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18004db88  mov     [rsp+150h+string], r13
0x18004db8d  mov     rdi, [rax]
0x18004db90  mov     rax, [rdi]
0x18004db93  mov     rbx, [rax+60h]
0x18004db97  lea     rcx, [rsp+150h+string]
0x18004db9c  call    ?reset@?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::reset(void)
0x18004dba1  lea     rdx, [rsp+150h+string]
0x18004dba6  mov     rcx, rdi
0x18004dba9  mov     rax, rbx
0x18004dbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbb1  mov     rcx, [rbp+58h]; this
0x18004dbb5  test    eax, eax
0x18004dbb7  js      loc_18004DC94
0x18004dbbd  xorps   xmm0, xmm0
0x18004dbc0  movups  [rbp+50h+var_A0], xmm0
0x18004dbc4  movdqa  [rbp+50h+var_90], xmm6
0x18004dbc9  mov     word ptr [rbp+50h+var_A0], r13w
0x18004dbce  movups  [rbp+50h+var_80], xmm0
0x18004dbd2  movdqa  [rbp+50h+var_70], xmm6
0x18004dbd7  mov     word ptr [rbp+50h+var_80], r13w
0x18004dbdc  mov     [rbp+50h+var_60], r13d
0x18004dbe0  mov     [rbp+50h+var_58], r13
0x18004dbe4  lea     rdx, [rsp+150h+string]
0x18004dbe9  lea     rcx, [rsp+150h+var_100]
0x18004dbee  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18004dbf3  lea     rdx, [rbp+50h+var_A0]
0x18004dbf7  mov     rcx, rax
0x18004dbfa  call    ?ParseAppToRefresh@WnsProvider@@CA_NV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUPushNotificationAppToRefresh@@@Z; WnsProvider::ParseAppToRefresh(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,PushNotificationAppToRefresh &)
0x18004dbff  test    al, al
0x18004dc01  jz      short loc_18004DC3B
0x18004dc03  mov     rax, [r15+10h]
0x18004dc07  cmp     rax, [r15+18h]
0x18004dc0b  jz      short loc_18004DC20
0x18004dc0d  lea     rdx, [rbp+50h+var_A0]; struct PushNotificationAppToRefresh *
0x18004dc11  mov     rcx, rax; this
0x18004dc14  call    ??0PushNotificationAppToRefresh@@QEAA@AEBU0@@Z; PushNotificationAppToRefresh::PushNotificationAppToRefresh(PushNotificationAppToRefresh const &)
0x18004dc19  add     qword ptr [r15+10h], 50h ; 'P'
0x18004dc1e  jmp     short loc_18004DC30
0x18004dc20  lea     r8, [rbp+50h+var_A0]
0x18004dc24  mov     rdx, rax
0x18004dc27  lea     rcx, [r15+8]
0x18004dc2b  call    ??$_Emplace_reallocate@AEBUPushNotificationAppToRefresh@@@?$vector@UPushNotificationAppToRefresh@@V?$allocator@UPushNotificationAppToRefresh@@@std@@@std@@AEAAPEAUPushNotificationAppToRefresh@@QEAU2@AEBU2@@Z; std::vector<PushNotificationAppToRefresh>::_Emplace_reallocate<PushNotificationAppToRefresh const &>(PushNotificationAppToRefresh * const,PushNotificationAppToRefresh const &)
0x18004dc30  mov     [r15], sil
0x18004dc33  add     r14d, esi
0x18004dc36  mov     [rsp+150h+length], r14d
0x18004dc3b  lea     rcx, [rbp+50h+var_A0]; this
0x18004dc3f  call    ??1PushNotificationAppToRefresh@@QEAA@XZ; PushNotificationAppToRefresh::~PushNotificationAppToRefresh(void)
0x18004dc44  nop
0x18004dc45  lea     rcx, [rsp+150h+string]
0x18004dc4a  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004dc4f  mov     eax, [rbp+50h+var_D0]
0x18004dc52  add     eax, esi
0x18004dc54  mov     [rbp+50h+var_D0], eax
0x18004dc57  jmp     loc_18004DB75
0x18004dc5c  lea     rcx, [rbp+50h+hstringHeader.Reserved+10h]
0x18004dc60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004dc65  nop
0x18004dc66  lea     rcx, [rbp+50h+var_C8]
  ... truncated ...
```
