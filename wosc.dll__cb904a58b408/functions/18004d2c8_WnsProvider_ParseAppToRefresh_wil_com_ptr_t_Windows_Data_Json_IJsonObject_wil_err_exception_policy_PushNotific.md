# WnsProvider::ParseAppToRefresh(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,PushNotificationAppToRefresh &)

- ea: `0x18004d2c8`
- end: `0x18004d53a`
- name: `?ParseAppToRefresh@WnsProvider@@CA_NV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUPushNotificationAppToRefresh@@@Z`
- size: `626`
- prototype: `char __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d7a0`

## callees

- `0x180003110`
- `0x180006b9c`
- `0x180009fcc`
- `0x180019e68`
- `0x180019ff0`
- `0x180020748`
- `0x180047e24`
- `0x18004add0`
- `0x18004af38`
- `0x18004d174`
- `0x18004d2c8`
- `0x18004d540`
- `0x18004d654`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d3fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d320`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d363`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004d3fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d382`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d45c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d382`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d45c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d4ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
char __fastcall WnsProvider::ParseAppToRefresh(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  HSTRING v7; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  char v14; // al
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v17; // rax
  PCWSTR v18; // rax
  __int64 v19; // r14
  __int64 v20; // r8
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v23; // rax
  int v24; // eax
  char v25; // bl
  PCWSTR v26; // rax
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  HSTRING v28; // [rsp+28h] [rbp-48h] BYREF
  UINT32 length; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v30; // [rsp+38h] [rbp-38h]
  _BYTE v31[32]; // [rsp+40h] [rbp-30h] BYREF

  v30 = a1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl'::`2'::impl) )
  {
    string = 0;
    v4 = *a1;
    v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &WnsProvider::s_tagAppId);
    length = v5(v4, *(_QWORD *)(v6 + 24), &string);
    if ( (length & 0x80000000) != 0 )
    {
      OneSettingsClientTelemetry::WnsPushNotificationPayloadMissingAppId<long &>(&length);
LABEL_4:
      v7 = string;
LABEL_5:
      WindowsDeleteString(v7);
      string = 0;
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(a1);
      return 0;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = -1;
    do
      ++v10;
    while ( StringRawBuffer[v10] );
    std::wstring::_Assign<unsigned short>(a2, StringRawBuffer);
    v11 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
            &v28,
            a1);
    if ( !(unsigned __int8)WnsProvider::ParseAppVersion(v11, a2) )
      goto LABEL_4;
    v12 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
            &v28,
            a1);
    if ( !(unsigned __int8)WnsProvider::ParseCnsInstructions(v12, a2) )
      goto LABEL_4;
    v13 = wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(
            &v28,
            a1);
    v14 = WnsProvider::ParseAppPayload(v13, a2);
    v7 = string;
    if ( !v14 )
      goto LABEL_5;
    WindowsDeleteString(string);
    goto LABEL_24;
  }
  v28 = 0;
  length = 0;
  v15 = *a1;
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &WnsProvider::s_tagAppId);
  LODWORD(string) = v16(v15, *(_QWORD *)(v17 + 24), &v28);
  if ( (int)string >= 0 )
  {
    v18 = WindowsGetStringRawBuffer(v28, &length);
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( v18[v20] );
    std::wstring::_Assign<unsigned short>(a2, v18);
    v21 = *a1;
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)*a1 + 80LL);
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v31, &WnsProvider::s_tagAppVersion);
    v24 = v22(v21, *(_QWORD *)(v23 + 24), &v28);
    LODWORD(string) = v24;
    if ( v24 == -2089484279 )
    {
      *(_QWORD *)(a2 + 48) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 32) = 0;
    }
    else
    {
      if ( v24 < 0 )
      {
        OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,unsigned short const * const &>(
          &string,
          &WnsProvider::s_tagAppVersion);
        goto LABEL_20;
      }
      v26 = WindowsGetStringRawBuffer(v28, &length);
      do
        ++v19;
      while ( v26[v19] );
      std::wstring::_Assign<unsigned short>(a2 + 32, v26);
    }
LABEL_24:
    v25 = 1;
    goto LABEL_25;
  }
  OneSettingsClientTelemetry::WnsPushNotificationPayloadMissingAppId<long &>(&string);
LABEL_20:
  v25 = 0;
LABEL_25:
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(a1);
  return v25;
}

```

## disassembly

```asm
0x18004d2c8  mov     [rsp-28h+arg_10], rbx
0x18004d2cd  mov     [rsp-28h+arg_18], rsi
0x18004d2d2  push    rbp
0x18004d2d3  push    rdi
0x18004d2d4  push    r12
0x18004d2d6  push    r14
0x18004d2d8  push    r15
0x18004d2da  mov     rbp, rsp
0x18004d2dd  sub     rsp, 70h
0x18004d2e1  mov     rax, cs:__security_cookie
0x18004d2e8  xor     rax, rsp
0x18004d2eb  mov     [rbp+var_10], rax
0x18004d2ef  mov     r15, rdx
0x18004d2f2  mov     rsi, rcx
0x18004d2f5  mov     [rbp+var_38], rcx
0x18004d2f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::GetImpl(void)'::`2'::impl
0x18004d300  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationPayload>::__private_IsEnabled(void)
0x18004d305  xor     r12d, r12d
0x18004d308  test    al, al
0x18004d30a  jz      loc_18004D409
0x18004d310  mov     [rbp+string], r12
0x18004d314  mov     rdi, [rsi]
0x18004d317  mov     rax, [rdi]
0x18004d31a  mov     rbx, [rax+50h]
0x18004d31e  xor     ecx, ecx; string
0x18004d320  call    cs:__imp_WindowsDeleteString
0x18004d326  mov     [rbp+string], r12
0x18004d32a  lea     rdx, ?s_tagAppId@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppId
0x18004d331  lea     rcx, [rbp+var_30]
0x18004d335  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d33a  nop
0x18004d33b  lea     r8, [rbp+string]
0x18004d33f  mov     rdx, [rax+18h]
0x18004d343  mov     rcx, rdi
0x18004d346  mov     rax, rbx
0x18004d349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d34e  mov     [rbp+length], eax
0x18004d351  test    eax, eax
0x18004d353  jns     short loc_18004D37C
0x18004d355  lea     rcx, [rbp+length]
0x18004d359  call    ??$WnsPushNotificationPayloadMissingAppId@AEAJ@OneSettingsClientTelemetry@@SAXAEAJ@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadMissingAppId<long &>(long &)
0x18004d35e  nop
0x18004d35f  mov     rcx, [rbp+string]; string
0x18004d363  call    cs:__imp_WindowsDeleteString
0x18004d369  mov     [rbp+string], r12
0x18004d36d  mov     rcx, rsi
0x18004d370  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004d375  xor     al, al
0x18004d377  jmp     loc_18004D515
0x18004d37c  xor     edx, edx; length
0x18004d37e  mov     rcx, [rbp+string]; string
0x18004d382  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d388  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004d38c  inc     r14
0x18004d38f  cmp     [rax+r14*2], r12w
0x18004d394  jnz     short loc_18004D38C
0x18004d396  mov     r8, r14
0x18004d399  mov     rdx, rax
0x18004d39c  mov     rcx, r15
0x18004d39f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d3a4  mov     rdx, rsi
0x18004d3a7  lea     rcx, [rbp+var_48]
0x18004d3ab  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18004d3b0  mov     rdx, r15
0x18004d3b3  mov     rcx, rax
0x18004d3b6  call    ?ParseAppVersion@WnsProvider@@CA_NV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUPushNotificationAppToRefresh@@@Z; WnsProvider::ParseAppVersion(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,PushNotificationAppToRefresh &)
0x18004d3bb  test    al, al
0x18004d3bd  jz      short loc_18004D35F
0x18004d3bf  mov     rdx, rsi
0x18004d3c2  lea     rcx, [rbp+var_48]
0x18004d3c6  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18004d3cb  mov     rdx, r15
0x18004d3ce  mov     rcx, rax
0x18004d3d1  call    ?ParseCnsInstructions@WnsProvider@@CA_NV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUPushNotificationAppToRefresh@@@Z; WnsProvider::ParseCnsInstructions(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,PushNotificationAppToRefresh &)
0x18004d3d6  test    al, al
0x18004d3d8  jz      short loc_18004D35F
0x18004d3da  mov     rdx, rsi
0x18004d3dd  lea     rcx, [rbp+var_48]
0x18004d3e1  call    ??0?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &)
0x18004d3e6  mov     rdx, r15
0x18004d3e9  mov     rcx, rax
0x18004d3ec  call    ?ParseAppPayload@WnsProvider@@CA_NV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@AEAUPushNotificationAppToRefresh@@@Z; WnsProvider::ParseAppPayload(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy>,PushNotificationAppToRefresh &)
0x18004d3f1  nop
0x18004d3f2  mov     rcx, [rbp+string]; string
0x18004d3f6  test    al, al
0x18004d3f8  jz      loc_18004D363
0x18004d3fe  call    cs:__imp_WindowsDeleteString
0x18004d404  jmp     loc_18004D509
0x18004d409  mov     [rbp+var_48], r12
0x18004d40d  mov     [rbp+length], r12d
0x18004d411  mov     rdi, [rsi]
0x18004d414  mov     rax, [rdi]
0x18004d417  mov     rbx, [rax+50h]
0x18004d41b  lea     rdx, ?s_tagAppId@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppId
0x18004d422  lea     rcx, [rbp+var_30]
0x18004d426  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d42b  nop
0x18004d42c  lea     r8, [rbp+var_48]
0x18004d430  mov     rdx, [rax+18h]
0x18004d434  mov     rcx, rdi
0x18004d437  mov     rax, rbx
0x18004d43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d43f  mov     dword ptr [rbp+string], eax
0x18004d442  test    eax, eax
0x18004d444  jns     short loc_18004D454
0x18004d446  lea     rcx, [rbp+string]
0x18004d44a  call    ??$WnsPushNotificationPayloadMissingAppId@AEAJ@OneSettingsClientTelemetry@@SAXAEAJ@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadMissingAppId<long &>(long &)
0x18004d44f  jmp     loc_18004D4DD
0x18004d454  lea     rdx, [rbp+length]; length
0x18004d458  mov     rcx, [rbp+var_48]; string
0x18004d45c  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d462  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004d466  mov     r8, r14
0x18004d469  inc     r8
0x18004d46c  cmp     [rax+r8*2], r12w
0x18004d471  jnz     short loc_18004D469
0x18004d473  mov     rdx, rax
0x18004d476  mov     rcx, r15
0x18004d479  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d47e  mov     rdi, [rsi]
0x18004d481  mov     rax, [rdi]
0x18004d484  mov     rbx, [rax+50h]
0x18004d488  lea     rdx, ?s_tagAppVersion@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppVersion
0x18004d48f  lea     rcx, [rbp+var_30]
0x18004d493  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004d498  nop
0x18004d499  lea     r8, [rbp+var_48]
0x18004d49d  mov     rdx, [rax+18h]
0x18004d4a1  mov     rcx, rdi
0x18004d4a4  mov     rax, rbx
0x18004d4a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d4ac  mov     dword ptr [rbp+string], eax
0x18004d4af  cmp     eax, 83750009h
0x18004d4b4  jnz     short loc_18004D4C9
0x18004d4b6  lea     rcx, [r15+20h]
0x18004d4ba  mov     [rcx+10h], r12
0x18004d4be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004d4c3  mov     [rax], r12w
0x18004d4c7  jmp     short loc_18004D509
0x18004d4c9  test    eax, eax
0x18004d4cb  jns     short loc_18004D4E2
0x18004d4cd  lea     rdx, ?s_tagAppVersion@WnsProvider@@0QEBGEB; ushort const * const WnsProvider::s_tagAppVersion
0x18004d4d4  lea     rcx, [rbp+string]
0x18004d4d8  call    ??$WnsPushNotificationPayloadParsingFailed@AEAJAEBQEBG@OneSettingsClientTelemetry@@SAXAEAJAEBQEBG@Z; OneSettingsClientTelemetry::WnsPushNotificationPayloadParsingFailed<long &,ushort const * const &>(long &,ushort const * const &)
0x18004d4dd  mov     bl, r12b
0x18004d4e0  jmp     short loc_18004D50B
0x18004d4e2  lea     rdx, [rbp+length]; length
0x18004d4e6  mov     rcx, [rbp+var_48]; string
0x18004d4ea  call    cs:__imp_WindowsGetStringRawBuffer
0x18004d4f0  inc     r14
0x18004d4f3  cmp     [rax+r14*2], r12w
0x18004d4f8  jnz     short loc_18004D4F0
0x18004d4fa  lea     rcx, [r15+20h]
0x18004d4fe  mov     r8, r14
0x18004d501  mov     rdx, rax
0x18004d504  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004d509  mov     bl, 1
0x18004d50b  mov     rcx, rsi
0x18004d50e  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004d513  mov     al, bl
0x18004d515  mov     rcx, [rbp+var_10]
0x18004d519  xor     rcx, rsp; StackCookie
0x18004d51c  call    __security_check_cookie
0x18004d521  lea     r11, [rsp+70h+var_s0]
0x18004d526  mov     rbx, [r11+40h]
0x18004d52a  mov     rsi, [r11+48h]
0x18004d52e  mov     rsp, r11
0x18004d531  pop     r15
0x18004d533  pop     r14
0x18004d535  pop     r12
0x18004d537  pop     rdi
0x18004d538  pop     rbp
0x18004d539  retn
```
