# RefreshCacheTaskHandler::Worker(void)

- ea: `0x180047030`
- end: `0x1800472ca`
- name: `?Worker@RefreshCacheTaskHandler@@EEAAJXZ`
- size: `666`
- prototype: `__int64 __fastcall(RefreshCacheTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003110`
- `0x18000943c`
- `0x180009fcc`
- `0x18000b0bc`
- `0x18000ed34`
- `0x1800101fc`
- `0x180019e18`
- `0x180042b8c`
- `0x180042c38`
- `0x180042c7c`
- `0x180045b18`
- `0x180045bd8`
- `0x180045dfc`
- `0x180045f14`
- `0x180046b84`
- `0x180047030`
- `0x180047344`
- `0x180047380`
- `0x1800473c0`
- `0x180047400`
- `0x18004783c`
- `0x1800478a8`
- `0x18004c41c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800471cc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800471cc`

## string_xrefs

- `0x18004707f`: `onecore\base\flighting\onesettings\libs\refreshcachetask\refreshcachetaskhandler.cpp`
- `0x180047095`: `onecore\base\flighting\onesettings\libs\refreshcachetask\refreshcachetaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall RefreshCacheTaskHandler::Worker(RefreshCacheTaskHandler *this)
{
  int v1; // eax
  __int64 v2; // rdx
  int v3; // eax
  struct wil::ThreadErrorContext *v4; // r8
  int v5; // eax
  int ActivationFactory; // eax
  int v7; // eax
  char IsEnabled; // al
  __int64 v9; // r8
  __int64 v10; // rdx
  const char *v11; // r9
  __int64 result; // rax
  int v13[2]; // [rsp+20h] [rbp-198h] BYREF
  int v14; // [rsp+2Ch] [rbp-18Ch]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-188h] BYREF
  __int64 v16; // [rsp+48h] [rbp-170h]
  _QWORD v17[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::GetImpl'::`2'::impl) )
      {
        v1 = HandlePushNotificationRefresh();
        if ( v1 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2A,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\refreshcachetask\\refreshcachetaskhandler.cpp",
            (const char *)(unsigned int)v1,
            v13[0]);
      }
    }
    wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v17);
    v17[0] = &OneSettingsClientTelemetry::RefreshOneSettings::`vftable';
    OneSettingsClientTelemetry::RefreshOneSettings::StartActivity((OneSettingsClientTelemetry::RefreshOneSettings *)v17);
    hstringHeader.Reserved.Reserved1 = retaddr;
    *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = (unsigned __int64)"onecore\\base\\flighting\\onesettings\\libs\\ref"
                                                                        "reshcachetask\\refreshcachetaskhandler.cpp";
    LOWORD(v16) = 48;
    LOBYTE(v2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask>::GetImpl'::`2'::impl,
      v2);
    wil::ThreadErrorContext::ThreadErrorContext((wil::ThreadErrorContext *)v13);
    v3 = lambda_48cf96510ae3f944a9036d14ef9eea46_::operator()();
    if ( v3 < 0 )
      wil::details::ReportFeatureError(
        (wil::details *)(unsigned int)v3,
        (int)v13,
        v4,
        (unsigned int)&hstringHeader,
        *(const struct DiagnosticsInfo **)v13);
    if ( *(_QWORD *)v13 )
      *(_DWORD *)(*(_QWORD *)v13 + 16LL) = v14;
    wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::GetImpl'::`2'::impl) )
      {
        v5 = HandlePushNotificationRefresh();
        if ( v5 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x48,
            (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\refreshcachetask\\refreshcachetaskhandler.cpp",
            (const char *)(unsigned int)v5,
            v13[0]);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs>::GetImpl'::`2'::impl) )
    {
      *(_QWORD *)v13 = 0;
      v16 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.Flighting.OneSettings.OneSettingsManager",
        0x3Au,
        0x39u);
      ActivationFactory = RoGetActivationFactory(v16, &GUID_999c5339_6b49_433d_acbb_990566d91531, v13);
      if ( ActivationFactory < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\refreshcachetask\\refreshcachetaskhandler.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v13[0]);
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 48LL))(*(_QWORD *)v13);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x51,
          (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\refreshcachetask\\refreshcachetaskhandler.cpp",
          (const char *)(unsigned int)v7,
          v13[0]);
      wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v13);
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_PdSTestFcRl>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PdSTestFcRl>::GetImpl'::`2'::impl);
    LOBYTE(v9) = 1;
    LOBYTE(v10) = IsEnabled;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PdSTestFcRl>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_PdSTestFcRl>::GetImpl'::`2'::impl,
      v10,
      v9);
    ReportTestProxyUsage();
    v13[1] = 0;
    v13[0] = Feature_CFR_Child_UM_C__private_featureState;
    if ( (Feature_CFR_Child_UM_C__private_featureState & 0x10) == 0 )
      Feature_CFR_Child_UM_C__private_ReportUsageFallback(*(_QWORD *)v13, 3);
    v13[1] = 0;
    v13[0] = Feature_CFR_Parent_UM_C__private_featureState;
    if ( (Feature_CFR_Parent_UM_C__private_featureState & 0x10) == 0 )
      Feature_CFR_Parent_UM_C__private_ReportUsageFallback(*(_QWORD *)v13, 3);
    OneSettingsClientTelemetry::RefreshOneSettings::~RefreshOneSettings((OneSettingsClientTelemetry::RefreshOneSettings *)v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5A,
                           (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\refreshcachetask\\refreshcachetaskhandler.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180047030  push    rbx
0x180047032  sub     rsp, 1B0h
0x180047039  mov     rax, cs:__security_cookie
0x180047040  xor     rax, rsp
0x180047043  mov     [rsp+1B8h+var_18], rax
0x18004704b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::GetImpl(void)'::`2'::impl
0x180047052  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::__private_IsEnabled(void)
0x180047057  test    al, al
0x180047059  jnz     short loc_180047095
0x18004705b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::GetImpl(void)'::`2'::impl
0x180047062  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::__private_IsEnabled(void)
0x180047067  test    al, al
0x180047069  jz      short loc_180047095
0x18004706b  call    ?HandlePushNotificationRefresh@@YAJXZ; HandlePushNotificationRefresh(void)
0x180047070  mov     rcx, [rsp+1B8h]; this
0x180047078  test    eax, eax
0x18004707a  jns     short loc_180047095
0x18004707c  mov     r9d, eax; char *
0x18004707f  lea     rbx, aOnecoreBaseFli_19; "onecore\\base\\flighting\\onesettings\\"...
0x180047086  mov     r8, rbx; unsigned int
0x180047089  mov     edx, 2Ah ; '*'; void *
0x18004708e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047093  jmp     short loc_18004709C
0x180047095  lea     rbx, aOnecoreBaseFli_19; "onecore\\base\\flighting\\onesettings\\"...
0x18004709c  lea     rdx, aRefreshonesett_0; "RefreshOneSettings"
0x1800470a3  lea     rcx, [rsp+1B8h+var_168]; struct wil::details::IFailureCallback *
0x1800470a8  call    ??0?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800470ad  lea     rax, ??_7RefreshOneSettings@OneSettingsClientTelemetry@@6B@; const OneSettingsClientTelemetry::RefreshOneSettings::`vftable'
0x1800470b4  mov     [rsp+1B8h+var_168], rax
0x1800470b9  lea     rcx, [rsp+1B8h+var_168]; this
0x1800470be  call    ?StartActivity@RefreshOneSettings@OneSettingsClientTelemetry@@QEAAXXZ; OneSettingsClientTelemetry::RefreshOneSettings::StartActivity(void)
0x1800470c3  nop
0x1800470c4  mov     rax, [rsp+1B8h]
0x1800470cc  mov     qword ptr [rsp+1B8h+hstringHeader.Reserved], rax
0x1800470d1  mov     qword ptr [rsp+1B8h+hstringHeader.Reserved+8], rbx
0x1800470d6  mov     qword ptr [rsp+1B8h+hstringHeader.Reserved+10h], 0
0x1800470df  mov     eax, 30h ; '0'
0x1800470e4  mov     word ptr [rsp+1B8h+var_170], ax
0x1800470e9  mov     dl, 1
0x1800470eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask>::GetImpl(void)'::`2'::impl
0x1800470f2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClientRefreshCacheTask>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800470f7  lea     rcx, [rsp+1B8h+var_198]; this
0x1800470fc  call    ??0ThreadErrorContext@wil@@QEAA@XZ; wil::ThreadErrorContext::ThreadErrorContext(void)
0x180047101  nop
0x180047102  call    _lambda_48cf96510ae3f944a9036d14ef9eea46___operator__
0x180047107  test    eax, eax
0x180047109  jns     short loc_18004711D
0x18004710b  lea     r9, [rsp+1B8h+hstringHeader]; unsigned int
0x180047110  lea     rdx, [rsp+1B8h+var_198]; int
0x180047115  mov     ecx, eax; this
0x180047117  call    ?ReportFeatureError@details@wil@@YAXJAEAVThreadErrorContext@2@IAEBUDiagnosticsInfo@2@@Z; wil::details::ReportFeatureError(long,wil::ThreadErrorContext &,uint,wil::DiagnosticsInfo const &)
0x18004711c  nop
0x18004711d  mov     rdx, qword ptr [rsp+1B8h+var_198]
0x180047122  test    rdx, rdx
0x180047125  jz      short loc_18004712E
0x180047127  mov     eax, [rsp+1B8h+var_18C]
0x18004712b  mov     [rdx+10h], eax
0x18004712e  lea     rcx, [rsp+1B8h+var_168]
0x180047133  call    ?Stop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180047138  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::GetImpl(void)'::`2'::impl
0x18004713f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationProcessAfterMainRefresh>::__private_IsEnabled(void)
0x180047144  test    al, al
0x180047146  jz      short loc_180047179
0x180047148  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh> `wil::Feature<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::GetImpl(void)'::`2'::impl
0x18004714f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneSettingsClient_PushNotificationRefresh>::__private_IsEnabled(void)
0x180047154  test    al, al
0x180047156  jz      short loc_180047179
0x180047158  call    ?HandlePushNotificationRefresh@@YAJXZ; HandlePushNotificationRefresh(void)
0x18004715d  mov     rcx, [rsp+1B8h]; this
0x180047165  test    eax, eax
0x180047167  jns     short loc_180047179
0x180047169  mov     r9d, eax; char *
0x18004716c  mov     r8, rbx; unsigned int
0x18004716f  mov     edx, 48h ; 'H'; void *
0x180047174  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047179  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs>::GetImpl(void)'::`2'::impl
0x180047180  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PFVC_CleanUpStagedConfigs>::__private_IsEnabled(void)
0x180047185  test    al, al
0x180047187  jz      loc_18004720D
0x18004718d  mov     qword ptr [rsp+1B8h+var_198], 0; int
0x180047196  mov     [rsp+1B8h+var_170], 0
0x18004719f  mov     r9d, 39h ; '9'; unsigned int
0x1800471a5  lea     r8d, [r9+1]; unsigned int
0x1800471a9  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsManager@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x1800471b0  lea     rcx, [rsp+1B8h+hstringHeader]; hstringHeader
0x1800471b5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800471ba  nop
0x1800471bb  lea     r8, [rsp+1B8h+var_198]
0x1800471c0  lea     rdx, _GUID_999c5339_6b49_433d_acbb_990566d91531
0x1800471c7  mov     rcx, [rsp+1B8h+var_170]
0x1800471cc  call    cs:__imp_RoGetActivationFactory
0x1800471d2  mov     rcx, [rsp+1B8h]; this
0x1800471da  test    eax, eax
0x1800471dc  js      loc_1800472A7
0x1800471e2  mov     rcx, qword ptr [rsp+1B8h+var_198]
0x1800471e7  mov     rax, [rcx]
0x1800471ea  mov     rax, [rax+30h]
0x1800471ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471f3  mov     rcx, [rsp+1B8h]; this
0x1800471fb  test    eax, eax
0x1800471fd  js      loc_1800472B8
0x180047203  lea     rcx, [rsp+1B8h+var_198]
0x180047208  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x18004720d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PdSTestFcRl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PdSTestFcRl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PdSTestFcRl> `wil::Feature<__WilFeatureTraits_Feature_PdSTestFcRl>::GetImpl(void)'::`2'::impl
0x180047214  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PdSTestFcRl@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PdSTestFcRl>::__private_IsEnabled(wil::ReportingKind)
0x180047219  mov     r8b, 1
0x18004721c  mov     dl, al
0x18004721e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PdSTestFcRl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PdSTestFcRl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PdSTestFcRl> `wil::Feature<__WilFeatureTraits_Feature_PdSTestFcRl>::GetImpl(void)'::`2'::impl
0x180047225  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PdSTestFcRl@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PdSTestFcRl>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004722a  call    ?ReportTestProxyUsage@@YAXXZ; ReportTestProxyUsage(void)
0x18004722f  mov     qword ptr [rsp+1B8h+var_198], 0
0x180047238  mov     eax, cs:Feature_CFR_Child_UM_C__private_featureState
0x18004723e  mov     [rsp+1B8h+var_198], eax
0x180047242  test    al, 10h
0x180047244  jnz     short loc_180047255
0x180047246  mov     edx, 3
0x18004724b  mov     rcx, qword ptr [rsp+1B8h+var_198]
0x180047250  call    Feature_CFR_Child_UM_C__private_ReportUsageFallback
0x180047255  mov     qword ptr [rsp+1B8h+var_198], 0
0x18004725e  mov     eax, cs:Feature_CFR_Parent_UM_C__private_featureState
0x180047264  mov     [rsp+1B8h+var_198], eax
0x180047268  test    al, 10h
0x18004726a  jnz     short loc_18004727C
0x18004726c  mov     edx, 3
0x180047271  mov     rcx, qword ptr [rsp+1B8h+var_198]
0x180047276  call    Feature_CFR_Parent_UM_C__private_ReportUsageFallback
0x18004727b  nop
0x18004727c  lea     rcx, [rsp+1B8h+var_168]; this
0x180047281  call    ??1RefreshOneSettings@OneSettingsClientTelemetry@@QEAA@XZ; OneSettingsClientTelemetry::RefreshOneSettings::~RefreshOneSettings(void)
0x180047286  xor     eax, eax
0x180047288  jmp     short loc_18004728E
0x18004728a  mov     eax, [rsp+1B8h+var_198]
0x18004728e  mov     rcx, [rsp+1B8h+var_18]
0x180047296  xor     rcx, rsp; StackCookie
0x180047299  call    __security_check_cookie
0x18004729e  add     rsp, 1B0h
0x1800472a5  pop     rbx
0x1800472a6  retn
0x1800472a7  mov     r9d, eax; char *
0x1800472aa  mov     r8, rbx; unsigned int
0x1800472ad  mov     edx, 50h ; 'P'; void *
0x1800472b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800472b8  mov     r9d, eax; char *
0x1800472bb  mov     r8, rbx; unsigned int
0x1800472be  mov     edx, 51h ; 'Q'; void *
0x1800472c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
