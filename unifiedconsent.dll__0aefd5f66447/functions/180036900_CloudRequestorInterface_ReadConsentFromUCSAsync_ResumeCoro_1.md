# CloudRequestorInterface::ReadConsentFromUCSAsync$_ResumeCoro$1

- ea: `0x180036900`
- end: `0x180038148`
- name: `CloudRequestorInterface::ReadConsentFromUCSAsync$_ResumeCoro$1`
- size: `6216`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038150`

## callees

- `0x180002810`
- `0x180002834`
- `0x180002840`
- `0x180002884`
- `0x180003390`
- `0x180003905`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fb28`
- `0x1800131f8`
- `0x180016498`
- `0x180018290`
- `0x1800194ec`
- `0x18001962c`
- `0x18001bed0`
- `0x18001c1d4`
- `0x18001cb64`
- `0x18001eb88`
- `0x18002d8ec`
- `0x180030a70`
- `0x180030b2c`
- `0x180030e10`
- `0x1800313a4`
- `0x180031d58`
- `0x1800320c8`
- `0x1800323b8`
- `0x1800325a8`
- `0x180032768`
- `0x180032890`
- `0x180032ab0`
- `0x18003585c`
- `0x180036900`
- `0x1800385e4`
- `0x180038b50`
- `0x1800391a0`
- `0x18003bd18`
- `0x18003ead8`
- `0x180040e3c`
- `0x180040fa0`
- `0x18004b544`
- `0x18004e6f0`
- `0x180051f38`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800380bf`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800380bf`
- `msvcp_win!_Thrd_yield` at `0x180037727`
- `msvcp_win!_Thrd_yield` at `0x180037b42`
- `msvcp_win!_Thrd_yield` at `0x180037727`
- `msvcp_win!_Thrd_yield` at `0x180037b42`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800376f3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800376f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037fe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037fe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036b2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003758a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037bf1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036a86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036b2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003758a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037bf1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037c1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037c1c`

## string_xrefs

- `0x180036c9c`: `https://consent.config.office.com/`
- `0x1800369da`: `CloudRequestorInterface::ReadConsentFromUCSAsync`
- `0x180037043`: `Initiating consent read to Cloud Requestor`
- `0x180036bbf`: `CloudRequestorInterface - creating service configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=37 #try_helpers=2
void __fastcall CloudRequestorInterface::ReadConsentFromUCSAsync__ResumeCoro_1(__int64 a1)
{
  _QWORD *v2; // r8
  __int64 v3; // rdx
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  _QWORD *v6; // rax
  _DWORD *v7; // rbx
  __int64 *v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // r12
  __int64 v11; // r8
  _QWORD *v12; // rax
  void **v13; // rcx
  unsigned __int64 v14; // rdx
  char *v15; // r15
  __int64 v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rbx
  __int64 (__fastcall ***v19)(_QWORD, __int64 *, __int64); // rcx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  _QWORD *v23; // rax
  _QWORD *v24; // rbx
  unsigned int v25; // edx
  _QWORD *v26; // r12
  bool v27; // zf
  __int64 v28; // rax
  __int64 *TokenBroker; // rax
  __int64 v30; // rcx
  __int64 v31; // r15
  volatile signed __int32 *v32; // rbx
  _QWORD *v33; // rcx
  volatile signed __int32 *v34; // rbx
  char *v35; // rbx
  _OWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  _QWORD *v39; // r9
  _QWORD *v40; // r8
  _QWORD *v41; // rdx
  __int64 v42; // rax
  __int64 v43; // r13
  __int64 v44; // r15
  void *v45; // rax
  __int64 v46; // r15
  __int64 *v47; // rax
  __int64 v48; // rbx
  unsigned int v49; // edx
  _QWORD *v50; // rax
  __int64 v51; // rbx
  struct winrt::impl::shared_hstring_header *v52; // r15
  __int64 v53; // rax
  const struct winrt::impl::slim_source_location *v54; // rax
  volatile __int64 *v55; // rbx
  volatile signed __int32 *v56; // rbx
  volatile signed __int32 *v57; // rbx
  volatile signed __int32 *v58; // rbx
  volatile signed __int32 *v59; // rbx
  volatile signed __int32 *v60; // rbx
  volatile signed __int32 *v61; // rbx
  volatile signed __int32 *v62; // rbx
  volatile signed __int32 *v63; // rbx
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rbx
  __int64 v66; // rcx
  const struct winrt::impl::slim_source_location *v67; // rax
  __int64 *v68; // r15
  volatile __int64 *v69; // rbx
  struct _RTL_CRITICAL_SECTION **v70; // r12
  __int64 *v71; // rax
  __int64 v72; // rbx
  __int64 p_LockCount; // rbx
  struct _RTL_CRITICAL_SECTION *v74; // r13
  _QWORD *v75; // rbx
  __int64 v76; // rax
  volatile signed __int32 *v77; // rbx
  volatile signed __int32 *v78; // rbx
  volatile signed __int32 *v79; // rbx
  volatile signed __int32 *v80; // rbx
  volatile signed __int32 *v81; // rbx
  volatile signed __int32 *v82; // rbx
  volatile signed __int32 *v83; // rbx
  volatile signed __int32 *v84; // rbx
  struct _RTL_CRITICAL_SECTION *v85; // rbx
  volatile signed __int32 *v86; // rbx
  __int64 v87; // [rsp+50h] [rbp-2E8h]
  struct _RTL_CRITICAL_SECTION *v88; // [rsp+78h] [rbp-2C0h]
  struct winrt::impl::shared_hstring_header *v89; // [rsp+80h] [rbp-2B8h]
  _QWORD *v90; // [rsp+88h] [rbp-2B0h]
  __int64 v91; // [rsp+90h] [rbp-2A8h]
  _WORD *v92; // [rsp+B0h] [rbp-288h]
  _BYTE pExceptionObject[24]; // [rsp+1B8h] [rbp-180h] BYREF
  _BYTE v94[24]; // [rsp+1D0h] [rbp-168h] BYREF
  char *v95; // [rsp+1E8h] [rbp-150h]
  __int64 v96; // [rsp+1F8h] [rbp-140h]

  v92 = (_WORD *)(a1 + 8);
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 8u )
  {
LABEL_201:
    __debugbreak();
  }
  else
  {
    switch ( *(_WORD *)(a1 + 8) )
    {
      case 0xFFFF:
      case 1:
      case 3:
        goto LABEL_191;
      case 0:
      case 4:
      case 5:
        goto LABEL_201;
      case 2:
        v2 = *(_QWORD **)(a1 + 1432);
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        v3 = v2[1];
        if ( !v3 )
          goto LABEL_82;
        v4 = *(_DWORD *)(v3 + 8);
        do
        {
          if ( !v4 )
LABEL_82:
            std::_Throw_bad_weak_ptr();
          v5 = v4;
          v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v4 + 1, v4);
        }
        while ( v5 != v4 );
        *(_QWORD *)(a1 + 16) = *v2;
        *(_QWORD *)(a1 + 24) = v2[1];
        *(_BYTE *)(a1 - 64) = 1;
        UnifiedConsentLogging::TraceLoggingInfo("CloudRequestorInterface::ReadConsentFromUCSAsync");
        *(_QWORD *)(a1 + 32) = 0;
        v6 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(a1 + 32);
        tip2::details::shared_data<0,0,0>::start(*v6 + 8LL, a1 + 40);
        v7 = operator new(0xA0u);
        *(_QWORD *)(a1 + 1256) = v7;
        v7[2] = 1;
        v7[3] = 1;
        *(_QWORD *)v7 = &std::_Ref_count_obj2<TraceLoggingCorrelationVector>::`vftable';
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v7 + 4);
        *(_QWORD *)(a1 + 56) = v7 + 4;
        *(_QWORD *)(a1 + 64) = v7;
        v95 = (char *)(v7 + 4);
        TraceLoggingCorrelationVector::ToStringW(
          (TraceLoggingCorrelationVector *)(v7 + 4),
          (unsigned __int16 *)(a1 + 80));
        v8 = (__int64 *)tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(a1 + 32);
        v9 = *v8;
        v10 = (_QWORD *)(a1 + 352);
        *(_QWORD *)(a1 + 352) = *v8;
        if ( v9 )
          _InterlockedAdd((volatile signed __int32 *)(v9 + 312), 1u);
        EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
        ++*(_DWORD *)(v9 + 240);
        v12 = (_QWORD *)*v10;
        v13 = (void **)(*v10 + 272LL);
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(a1 + 80 + 2 * v14) );
        if ( v14 > v12[37] )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v13,
            v14,
            v11,
            a1 + 80);
        }
        else
        {
          if ( v12[37] <= 7u )
            v15 = (char *)(v12 + 34);
          else
            v15 = (char *)*v13;
          v12[36] = v14;
          v16 = 2 * v14;
          memmove_0(v15, (const void *)(a1 + 80), 2 * v14);
          *(_WORD *)&v15[v16] = 0;
        }
        tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(a1 + 352);
        v17 = (__int64 *)tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(a1 + 32);
        v18 = *v17;
        *(_QWORD *)(a1 + 360) = *v17;
        if ( v18 )
          _InterlockedIncrement((volatile signed __int32 *)(v18 + 312));
        EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 200));
        ++*(_DWORD *)(v18 + 240);
        *(_DWORD *)(*(_QWORD *)(a1 + 360) + 304LL) = 2;
        tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(a1 + 360);
        v19 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 1440);
        if ( v19 )
        {
          *(_QWORD *)(a1 + 1264) = 0;
          *(_DWORD *)(a1 + 1272) = 0;
          *(_QWORD *)(a1 + 1280) = 0;
          *(_QWORD *)(a1 + 1288) = 0;
          v21 = (**v19)(v19, winrt::impl::guid_v<winrt::Windows::Security::Credentials::IWebAccount>, a1 + 1264);
          if ( v21 < 0 )
            winrt::throw_hresult((unsigned int)v21, a1 + 1272);
          v20 = *(_QWORD *)(a1 + 1264);
        }
        else
        {
          v20 = 0;
        }
        *(_QWORD *)(a1 + 368) = v20;
        UnifiedConsentLogging::TraceLoggingInfo("CloudRequestorInterface - creating service configuration");
        *(_QWORD *)(a1 + 384) = a1 + 376;
        std::pair<winrt::hstring const,winrt::hstring>::pair<winrt::hstring const,winrt::hstring>(
          a1 + 472,
          &CloudRequestorInterface::c_ucsConsentScopeName,
          &CloudRequestorInterface::c_ucsConsentScopeValue);
        *(_QWORD *)(a1 + 1216) = a1 + 472;
        *(_QWORD *)(a1 + 1224) = a1 + 488;
        v22 = std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(a1 + 408);
        v23 = (_QWORD *)winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(
                          a1 + 488,
                          v22);
        *(_BYTE *)(a1 + 400) = 0;
        v24 = (_QWORD *)(a1 + 392);
        *(_QWORD *)(a1 + 392) = *v23;
        if ( aProd[4] )
          goto LABEL_81;
        *(_DWORD *)(a1 + 504) = 1;
        *(_DWORD *)(a1 + 508) = 4;
        *(_QWORD *)(a1 + 520) = L"prod";
        *(_QWORD *)(a1 + 496) = a1 + 504;
        if ( aHttpsConsentCo[34]
          || (*(_DWORD *)(a1 + 536) = 1,
              *(_DWORD *)(a1 + 540) = 34,
              *(_QWORD *)(a1 + 552) = L"https://consent.config.office.com/",
              *(_QWORD *)(a1 + 528) = a1 + 536,
              a76058868F3974b[36]) )
        {
LABEL_81:
          abort();
        }
        *(_DWORD *)(a1 + 568) = 1;
        *(_DWORD *)(a1 + 572) = 36;
        *(_QWORD *)(a1 + 584) = L"76058868-f397-4bdc-bf2c-ee6fedd44410";
        *(_QWORD *)(a1 + 560) = a1 + 568;
        v87 = winrt::Windows::Internal::CloudRequestor::EnvironmentConfig::EnvironmentConfig(
                (int)a1 + 376,
                (int)a1 + 560,
                (int)a1 + 528,
                (int)a1 + 496,
                a1 + 392);
        v89 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)3, v25);
        memcpy_s((char *)v89 + 28, 6u, L"ucs", 6u);
        *(_QWORD *)(a1 + 592) = v89;
        v26 = (_QWORD *)(a1 + 600);
        Windows::Internal::CloudRequestor::CreateServiceConfiguration(a1 + 600, a1 + 592, v87);
        if ( !*(_BYTE *)(a1 + 400) )
          *v24 = 0;
        if ( *v24 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 392);
        if ( *(_QWORD *)(a1 + 488) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 488);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 432);
        std::list<std::pair<winrt::hstring const,winrt::hstring>>::~list<std::pair<winrt::hstring const,winrt::hstring>>(a1 + 416);
        `eh vector destructor iterator'(
          (void *)(a1 + 472),
          0x10u,
          1u,
          std::pair<winrt::hstring const,winrt::hstring>::~pair<winrt::hstring const,winrt::hstring>);
        *(_QWORD *)(a1 + 616) = 0;
        *(_QWORD *)(a1 + 624) = 0;
        v27 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl'::`2'::impl) == 0;
        v28 = *(_QWORD *)(a1 + 608);
        if ( v27 )
        {
          v33 = (_QWORD *)(a1 + 664);
          *(_QWORD *)(a1 + 664) = 0;
          *(_QWORD *)(a1 + 672) = 0;
          if ( v28 )
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 608) + 8LL), 1u);
          *v33 = *v26;
          *(_QWORD *)(a1 + 672) = *(_QWORD *)(a1 + 608);
          *(_QWORD *)(a1 + 1248) = v33;
          *(_QWORD *)(a1 + 1296) = 0;
          *(_QWORD *)(a1 + 1304) = 0;
          if ( *(_QWORD *)(a1 + 608) )
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 608) + 8LL), 1u);
          *(_QWORD *)(a1 + 1296) = *v33;
          *(_QWORD *)(a1 + 1304) = *(_QWORD *)(a1 + 672);
          Windows::Internal::CloudRequestor::TokenBrokerHandler::CreateTokenBrokerSingleton(a1 + 680);
          if ( *(_QWORD *)(a1 + 672) )
          {
            v34 = *(volatile signed __int32 **)(a1 + 672);
            if ( _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
              if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
            }
          }
          v31 = *(_QWORD *)(a1 + 688);
          *(_QWORD *)(a1 + 616) = *(_QWORD *)(a1 + 680);
          *(_QWORD *)(a1 + 624) = v31;
        }
        else
        {
          *(_QWORD *)(a1 + 632) = 0;
          *(_QWORD *)(a1 + 640) = 0;
          if ( v28 )
            _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 608) + 8LL), 1u);
          *(_QWORD *)(a1 + 632) = *v26;
          *(_QWORD *)(a1 + 640) = *(_QWORD *)(a1 + 608);
          TokenBroker = (__int64 *)Windows::Internal::CloudRequestor::CreateTokenBroker(a1 + 648);
          v30 = *TokenBroker;
          v31 = TokenBroker[1];
          *TokenBroker = 0;
          TokenBroker[1] = 0;
          *(_QWORD *)(a1 + 616) = v30;
          *(_QWORD *)(a1 + 624) = v31;
          if ( *(_QWORD *)(a1 + 656) )
          {
            v32 = *(volatile signed __int32 **)(a1 + 656);
            if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
              if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            }
          }
        }
        v35 = (char *)operator new(0x18u);
        *(_QWORD *)(a1 + 1312) = v35;
        *((_DWORD *)v35 + 2) = 1;
        *((_DWORD *)v35 + 3) = 1;
        *(_QWORD *)v35 = &std::_Ref_count_obj2<Windows::Internal::CloudRequestor::Common::RegistryUtils>::`vftable';
        *((_QWORD *)v35 + 2) = &UnifiedConsentLogging::CRLogging::`vftable';
        UnifiedConsentLogging::TraceLoggingInfo("Initiating consent read to Cloud Requestor");
        *(_QWORD *)(a1 + 696) = v35 + 16;
        *(_QWORD *)(a1 + 704) = v35;
        *(_QWORD *)(a1 + 712) = 0;
        *(_QWORD *)(a1 + 720) = 0;
        _InterlockedIncrement((volatile signed __int32 *)v35 + 2);
        *(_QWORD *)(a1 + 712) = v35 + 16;
        *(_QWORD *)(a1 + 720) = v35;
        *(_QWORD *)(a1 + 728) = 0;
        *(_QWORD *)(a1 + 736) = 0;
        if ( v31 )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 624) + 8LL));
        *(_QWORD *)(a1 + 728) = *(_QWORD *)(a1 + 616);
        *(_QWORD *)(a1 + 736) = *(_QWORD *)(a1 + 624);
        *(_QWORD *)(a1 + 744) = 0;
        *(_QWORD *)(a1 + 752) = 0;
        if ( *(_QWORD *)(a1 + 608) )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 608) + 8LL));
        *(_QWORD *)(a1 + 744) = *v26;
        *(_QWORD *)(a1 + 752) = *(_QWORD *)(a1 + 608);
        Windows::Internal::CloudRequestor::CreateRequestResponseHandler(a1 + 760);
        Windows::Internal::CloudRequestor::CreateHttpClient(a1 + 776);
        v36 = operator new(0x28u);
        *(_QWORD *)(a1 + 1320) = v36;
        *v36 = 0;
        *(_DWORD *)(*(_QWORD *)(a1 + 1320) + 8LL) = 1;
        *(_DWORD *)(*(_QWORD *)(a1 + 1320) + 12LL) = 1;
        **(_QWORD **)(a1 + 1320) = &std::_Ref_count_obj2<Windows::Internal::CloudRequestor::ServiceInfo>::`vftable';
        std::_Construct_in_place<Windows::Internal::CloudRequestor::ServiceInfo,unsigned short const * const &,unsigned short const * const &,unsigned short const * const &>(
          *(_QWORD *)(a1 + 1320) + 16LL,
          &CloudRequestorInterface::c_ucsServiceName,
          &CloudRequestorInterface::c_ucsEnvName,
          &CloudRequestorInterface::c_ucsConsentScopeName);
        *(_QWORD *)(a1 + 792) = *(_QWORD *)(a1 + 1320) + 16LL;
        *(_QWORD *)(a1 + 800) = *(_QWORD *)(a1 + 1320);
        v37 = *(_QWORD *)(a1 + 368);
        *(_QWORD *)(a1 + 808) = v37;
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
        *(_QWORD *)(a1 + 816) = 0;
        *(_QWORD *)(a1 + 824) = 0;
        v38 = *(_QWORD *)(a1 + 1312);
        _InterlockedIncrement((volatile signed __int32 *)(v38 + 8));
        *(_QWORD *)(a1 + 816) = v35 + 16;
        *(_QWORD *)(a1 + 824) = v38;
        *(_QWORD *)(a1 + 832) = 0;
        *(_QWORD *)(a1 + 840) = 0;
        if ( *(_QWORD *)(a1 + 784) )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 784) + 8LL));
        *(_QWORD *)(a1 + 832) = *(_QWORD *)(a1 + 776);
        *(_QWORD *)(a1 + 840) = *(_QWORD *)(a1 + 784);
        v39 = (_QWORD *)(a1 + 848);
        *(_QWORD *)(a1 + 848) = 0;
        *(_QWORD *)(a1 + 856) = 0;
        if ( *(_QWORD *)(a1 + 608) )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 608) + 8LL));
        *v39 = *(_QWORD *)(a1 + 600);
        *(_QWORD *)(a1 + 856) = *(_QWORD *)(a1 + 608);
        v40 = (_QWORD *)(a1 + 864);
        *(_QWORD *)(a1 + 864) = 0;
        *(_QWORD *)(a1 + 872) = 0;
        if ( *(_QWORD *)(a1 + 624) )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 624) + 8LL));
        *v40 = *(_QWORD *)(a1 + 616);
        *(_QWORD *)(a1 + 872) = *(_QWORD *)(a1 + 624);
        v41 = (_QWORD *)(a1 + 880);
        *(_QWORD *)(a1 + 880) = 0;
        *(_QWORD *)(a1 + 888) = 0;
        if ( *(_QWORD *)(a1 + 768) )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 768) + 8LL));
        *v41 = *(_QWORD *)(a1 + 760);
        *(_QWORD *)(a1 + 888) = *(_QWORD *)(a1 + 768);
        Windows::Internal::CloudRequestor::CreateCommonHTTPInterface(
          a1 + 896,
          (_DWORD)v41,
          (_DWORD)v40,
          (_DWORD)v39,
          a1 + 832,
          a1 + 816,
          a1 + 808,
          300000000,
          a1 + 792,
          1);
        UnifiedConsentLogging::TraceLoggingInfo("CloudRequestorInterface - creating request");
        std::pair<winrt::hstring const,winrt::hstring>::pair<winrt::hstring const,winrt::hstring>(
          a1 + 976,
          &CloudRequestorInterface::c_ucsHeaderAppId,
          &CloudRequestorInterface::c_ccAppId);
        std::pair<winrt::hstring const,winrt::hstring>::pair<winrt::hstring const,winrt::hstring>(
          a1 + 992,
          &CloudRequestorInterface::c_ucsHeaderAcceptLanguage,
          &CloudRequestorInterface::c_ucsHeaderAcceptLanguageValue);
        *(_QWORD *)(a1 + 1232) = a1 + 976;
        *(_QWORD *)(a1 + 1240) = a1 + 1008;
        v42 = std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(a1 + 912);
        v43 = winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(
                a1 + 1008,
                v42);
        v44 = winrt::Windows::Web::Http::HttpMethod::Get();
        v45 = operator new(0x38u);
        *(_QWORD *)(a1 + 1336) = v45;
        v46 = std::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>::_Ref_count_obj2<Windows::Internal::CloudRequestor::RequestItem>(
                v45,
                v44,
                v43);
        *(_QWORD *)(a1 + 1328) = v46;
        *(_QWORD *)(a1 + 1024) = v46 + 16;
        *(_QWORD *)(a1 + 1032) = v46;
        if ( *(_QWORD *)(a1 + 1016) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1016);
        if ( *(_QWORD *)(a1 + 1008) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1008);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(a1 + 936);
        std::list<std::pair<winrt::hstring const,winrt::hstring>>::~list<std::pair<winrt::hstring const,winrt::hstring>>(a1 + 920);
        `eh vector destructor iterator'(
          (void *)(a1 + 976),
          0x10u,
          2u,
          std::pair<winrt::hstring const,winrt::hstring>::~pair<winrt::hstring const,winrt::hstring>);
        UnifiedConsentLogging::TraceLoggingInfo("CloudRequestorInterface - sending request");
        v47 = (__int64 *)tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(a1 + 32);
        v48 = *v47;
        *(_QWORD *)(a1 + 1040) = *v47;
        if ( v48 )
          _InterlockedIncrement((volatile signed __int32 *)(v48 + 312));
        EnterCriticalSection((LPCRITICAL_SECTION)(v48 + 200));
        ++*(_DWORD *)(v48 + 240);
        *(_DWORD *)(*(_QWORD *)(a1 + 1040) + 304LL) = 3;
        tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(a1 + 1040);
        v50 = *(_QWORD **)(a1 + 896);
        v90 = v50;
        v91 = *v50;
        *(_QWORD *)(a1 + 1064) = a1 + 1048;
        *(_QWORD *)(a1 + 1048) = 0;
        *(_QWORD *)(a1 + 1056) = 0;
        if ( v46 )
          _InterlockedIncrement((volatile signed __int32 *)(v46 + 8));
        v96 = v46 + 16;
        *(_QWORD *)(a1 + 1048) = v46 + 16;
        *(_QWORD *)(a1 + 1056) = v46;
        v51 = -1;
        do
          ++v51;
        while ( *(_WORD *)(a1 + 2 * v51 + 80) );
        if ( (_DWORD)v51 )
        {
          v52 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v51, v49);
          memcpy_s((char *)v52 + 28, 2LL * (unsigned int)v51, (const void *const)(a1 + 80), 2LL * (unsigned int)v51);
          v50 = v90;
        }
        else
        {
          v52 = 0;
        }
        *(_QWORD *)(a1 + 1072) = v52;
        v53 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, __int64))(v91 + 8))(
                v50,
                a1 + 1080,
                a1 + 1072,
                a1 + 1048);
        if ( *(_DWORD *)(a1 - 16) == 2 )
        {
          v54 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1344);
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v54);
          throw (winrt::hresult_canceled *)pExceptionObject;
        }
        *(_QWORD *)(a1 + 1088) = 0;
        *(_QWORD *)(a1 + 1096) = v53;
        *(_QWORD *)(a1 + 1104) = 0;
        *(_BYTE *)(a1 + 1112) = 1;
        *v92 = 6;
        if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type>(
                                 a1 + 1088,
                                 a1) )
        {
LABEL_128:
          *(_DWORD *)(a1 + 1368) = 0;
          *(_QWORD *)(a1 + 1376) = 0;
          *(_QWORD *)(a1 + 1384) = 0;
          v66 = *(unsigned int *)(a1 + 1108);
          if ( (int)v66 < 0 )
            winrt::throw_hresult(v66, a1 + 1368);
          if ( *(_DWORD *)(a1 + 1104) == 2 )
          {
            v67 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1392);
            winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v94, v67);
            throw (winrt::hresult_canceled *)v94;
          }
          v68 = (__int64 *)(a1 + 1120);
          winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::GetResults(
            *(_QWORD *)(a1 + 1096),
            a1 + 1120);
          if ( *(_QWORD *)(a1 + 1088) )
          {
            v69 = *(volatile __int64 **)(a1 + 1088);
            while ( _InterlockedExchange64(v69, 0) == 1 )
              _Thrd_yield();
          }
          if ( *(_QWORD *)(a1 + 1080) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1080);
          v70 = (struct _RTL_CRITICAL_SECTION **)(a1 + 32);
          v71 = (__int64 *)tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(a1 + 32);
          v72 = *v71;
          *(_QWORD *)(a1 + 1128) = *v71;
          if ( v72 )
            _InterlockedIncrement((volatile signed __int32 *)(v72 + 312));
          EnterCriticalSection((LPCRITICAL_SECTION)(v72 + 200));
          ++*(_DWORD *)(v72 + 240);
          *(_DWORD *)(*(_QWORD *)(a1 + 1128) + 304LL) = 4;
          tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(a1 + 1128);
          if ( *v70 )
          {
            v88 = *v70;
            p_LockCount = (__int64)&(*v70)->LockCount;
            v74 = *v70 + 5;
            EnterCriticalSection(v74);
            LODWORD(v88[1].SpinCount) |= 0x300u;
            if ( *(_QWORD *)(p_LockCount + 240) )
              tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 2);
            if ( v74 )
              LeaveCriticalSection(v74);
          }
          UnifiedConsentLogging::TraceLoggingInfo("CloudRequestorInterface - Received response");
          v75 = (_QWORD *)(a1 - 8);
          if ( (__int64 *)(a1 - 8) != v68 )
          {
            if ( *v75 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 8);
            v76 = *v68;
            *v68 = 0;
            *v75 = v76;
          }
          if ( *v68 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1120);
          v77 = *(volatile signed __int32 **)(a1 + 1328);
          if ( v77 )
          {
            if ( _InterlockedExchangeAdd(v77 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
              if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
            }
          }
          if ( *(_QWORD *)(a1 + 904) )
          {
            v78 = *(volatile signed __int32 **)(a1 + 904);
            if ( _InterlockedExchangeAdd(v78 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
              if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
            }
          }
          if ( *(_QWORD *)(a1 + 784) )
          {
            v79 = *(volatile signed __int32 **)(a1 + 784);
            if ( _InterlockedExchangeAdd(v79 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v79)(v79);
              if ( _InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v79 + 8LL))(v79);
            }
          }
          if ( *(_QWORD *)(a1 + 768) )
          {
            v80 = *(volatile signed __int32 **)(a1 + 768);
            if ( _InterlockedExchangeAdd(v80 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v80)(v80);
              if ( _InterlockedExchangeAdd(v80 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v80 + 8LL))(v80);
            }
          }
          v81 = *(volatile signed __int32 **)(a1 + 1312);
          if ( _InterlockedExchangeAdd(v81 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v81)(v81);
            if ( _InterlockedExchangeAdd(v81 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v81 + 8LL))(v81);
          }
          if ( *(_QWORD *)(a1 + 624) )
          {
            v82 = *(volatile signed __int32 **)(a1 + 624);
            if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
              if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
            }
          }
          if ( *(_QWORD *)(a1 + 608) )
          {
            v83 = *(volatile signed __int32 **)(a1 + 608);
            if ( _InterlockedExchangeAdd(v83 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
              if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
            }
          }
          if ( *(_QWORD *)(a1 + 368) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 368);
          v84 = *(volatile signed __int32 **)(a1 + 1256);
          if ( _InterlockedExchangeAdd(v84 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v84)(v84);
            if ( _InterlockedExchangeAdd(v84 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v84 + 8LL))(v84);
          }
          if ( *v70 )
          {
            v85 = *v70;
            if ( !_InterlockedDecrement((volatile signed __int32 *)&(*v70)[7].SpinCount) )
            {
              tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(v85);
              CoTaskMemFree(v85);
            }
          }
          if ( *(_QWORD *)(a1 + 24) )
          {
            v86 = *(volatile signed __int32 **)(a1 + 24);
            if ( _InterlockedExchangeAdd(v86 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v86)(v86);
              if ( _InterlockedExchangeAdd(v86 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v86 + 8LL))(v86);
            }
          }
          *(_QWORD *)(a1 + 1200) = a1 - 112;
          *v92 = 0;
          if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::final_suspend_awaiter::await_suspend() )
          {
LABEL_191:
            if ( *(_QWORD *)(a1 - 8) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 8);
            if ( *(_QWORD *)(a1 - 24) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
            if ( *(_QWORD *)(a1 - 32) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 32);
            __ExceptionPtrDestroy((void *)(a1 - 56));
            __1__root_implements_U__map_impl_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_V__unordered_map_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_U__hash_Uhstring_winrt___std__U__equal_to_Uhstring_winrt___8_V__allocator_U__pair___CBUhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__std___8__std__Umulti_threaded_collection_base_impl_2__impl_winrt__U__IMap_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_3_U__IMapView_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__5673_U__IIterable_U__IKeyValuePair_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_winrt___5673__impl_winrt__MEAA_XZ(a1 - 112);
            if ( *(_QWORD *)(a1 + 1440) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1440);
            if ( *(_WORD *)(a1 + 10) )
              operator delete((void *)(a1 - 112), 0x620u);
          }
        }
        break;
      case 6:
        goto LABEL_128;
      case 7:
        if ( *(_QWORD *)(a1 + 1088) )
        {
          v55 = *(volatile __int64 **)(a1 + 1088);
          while ( _InterlockedExchange64(v55, 0) == 1 )
            _Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 1080) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1080);
        v56 = *(volatile signed __int32 **)(a1 + 1328);
        if ( v56 )
        {
          if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
            if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
          }
        }
        if ( *(_QWORD *)(a1 + 904) )
        {
          v57 = *(volatile signed __int32 **)(a1 + 904);
          if ( _InterlockedExchangeAdd(v57 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
            if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
          }
        }
        if ( *(_QWORD *)(a1 + 784) )
        {
          v58 = *(volatile signed __int32 **)(a1 + 784);
          if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
            if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
          }
        }
        if ( *(_QWORD *)(a1 + 768) )
        {
          v59 = *(volatile signed __int32 **)(a1 + 768);
          if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
            if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
          }
        }
        v60 = *(volatile signed __int32 **)(a1 + 1312);
        if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
          if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
        }
        if ( *(_QWORD *)(a1 + 624) )
        {
          v61 = *(volatile signed __int32 **)(a1 + 624);
          if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
            if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
          }
        }
        if ( *(_QWORD *)(a1 + 608) )
        {
          v62 = *(volatile signed __int32 **)(a1 + 608);
          if ( _InterlockedExchangeAdd(v62 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
            if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
          }
        }
        if ( *(_QWORD *)(a1 + 368) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 368);
        v63 = *(volatile signed __int32 **)(a1 + 1256);
        if ( _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
          if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
        }
        if ( *(_QWORD *)(a1 + 32) )
        {
          v64 = *(volatile signed __int32 **)(a1 + 32);
          if ( !_InterlockedDecrement(v64 + 78) )
          {
            tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>::~merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>(v64);
            CoTaskMemFree((LPVOID)v64);
          }
        }
        if ( *(_QWORD *)(a1 + 24) )
        {
          v65 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
            if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
          }
        }
        goto LABEL_191;
    }
  }
}

```

## disassembly

```asm
0x180036900  mov     r11, rsp
0x180036903  mov     [r11+10h], rbx
0x180036907  mov     [r11+18h], rsi
0x18003690b  mov     [r11+8], rcx
0x18003690f  push    rdi
0x180036910  push    r12
0x180036912  push    r13
0x180036914  push    r14
0x180036916  push    r15
0x180036918  sub     rsp, 310h
0x18003691f  mov     rax, cs:__security_cookie
0x180036926  xor     rax, rsp
0x180036929  mov     [rsp+338h+var_30], rax
0x180036931  mov     rdi, rcx
0x180036934  mov     [rsp+338h+var_290], rcx
0x18003693c  lea     rdx, [rdi+8]
0x180036940  mov     [rsp+338h+var_288], rdx
0x180036948  movzx   eax, word ptr [rdx]
0x18003694b  mov     [rsp+338h+var_280], ax
0x180036953  mov     r15d, 1
0x180036959  add     ax, r15w
0x18003695d  lea     ebx, [r15+7]
0x180036961  cmp     ax, bx
0x180036964  ja      loc_1800380F5; jumptable 0000000180036988 cases 1,5,6
0x18003696a  mov     [rsp+338h+var_250], rdx
0x180036972  movsx   rax, ax
0x180036976  lea     r8, cs:180000000h
0x18003697d  mov     ecx, ds:(jpt_180036988 - 180000000h)[r8+rax*4]; switch 9 cases
0x180036985  add     rcx, r8
0x180036988  jmp     rcx; switch jump
0x18003698a  xor     esi, esi; jumptable 0000000180036988 case 4
0x18003698c  jmp     loc_180038091
0x180036991  xor     esi, esi; jumptable 0000000180036988 case 3
0x180036993  mov     r8, [rdx+590h]
0x18003699a  mov     [rdi+10h], rsi
0x18003699e  mov     [rdi+18h], rsi
0x1800369a2  mov     rdx, [r8+8]
0x1800369a6  test    rdx, rdx
0x1800369a9  jz      loc_1800376FA
0x1800369af  mov     eax, [rdx+8]
0x1800369b2  jmp     short loc_1800369BE
0x1800369b4  lea     ecx, [rax+1]
0x1800369b7  lock cmpxchg [rdx+8], ecx
0x1800369bc  jz      short loc_1800369C7
0x1800369be  test    eax, eax
0x1800369c0  jnz     short loc_1800369B4
0x1800369c2  jmp     loc_1800376FA
0x1800369c7  mov     rax, [r8]
0x1800369ca  mov     [rdi+10h], rax
0x1800369ce  mov     rax, [r8+8]
0x1800369d2  mov     [rdi+18h], rax
0x1800369d6  mov     [rdi-40h], r15b
0x1800369da  lea     rcx, aCloudrequestor; "CloudRequestorInterface::ReadConsentFro"...
0x1800369e1  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x1800369e6  lea     r14, [rdi+20h]
0x1800369ea  mov     [r14], rsi
0x1800369ed  mov     rcx, r14
0x1800369f0  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(void)
0x1800369f5  lea     rdx, [rdi+28h]
0x1800369f9  mov     rcx, [rax]
0x1800369fc  add     rcx, rbx
0x1800369ff  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180036a04  nop
0x180036a05  mov     ecx, 0A0h; Size
0x180036a0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180036a0f  mov     rbx, rax
0x180036a12  mov     [rdi+4E8h], rax
0x180036a19  mov     [rax+8], r15d
0x180036a1d  mov     [rax+0Ch], r15d
0x180036a21  lea     rax, ??_7?$_Ref_count_obj2@VTraceLoggingCorrelationVector@@@std@@6B@; const std::_Ref_count_obj2<TraceLoggingCorrelationVector>::`vftable'
0x180036a28  mov     [rbx], rax
0x180036a2b  lea     rcx, [rbx+10h]
0x180036a2f  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x180036a34  lea     rcx, [rbx+10h]; this
0x180036a38  mov     [rdi+38h], rcx
0x180036a3c  mov     [rdi+40h], rbx
0x180036a40  lea     r13, [rdi+50h]
0x180036a44  mov     [rsp+338h+var_150], rcx
0x180036a4c  mov     rdx, r13; unsigned __int16 *
0x180036a4f  call    ?ToStringW@TraceLoggingCorrelationVector@@QEAA_NPEAG@Z; TraceLoggingCorrelationVector::ToStringW(ushort *)
0x180036a54  mov     rcx, r14
0x180036a57  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(void)
0x180036a5c  mov     rbx, [rax]
0x180036a5f  lea     r12, [rdi+160h]
0x180036a66  mov     [r12], rbx
0x180036a6a  test    rbx, rbx
0x180036a6d  jz      short loc_180036A77
0x180036a6f  lock add [rbx+138h], r15d
0x180036a77  mov     [rsp+338h+var_210], rbx
0x180036a7f  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180036a86  call    cs:__imp_EnterCriticalSection
0x180036a8c  add     [rbx+0F0h], r15d
0x180036a93  mov     rax, [r12]
0x180036a97  mov     [rsp+338h+var_210], rax
0x180036a9f  lea     rcx, [rax+110h]
0x180036aa6  or      r14, 0FFFFFFFFFFFFFFFFh
0x180036aaa  mov     rdx, r14
0x180036aad  inc     rdx
0x180036ab0  cmp     [r13+rdx*2+0], si
0x180036ab6  jnz     short loc_180036AAD
0x180036ab8  cmp     rdx, [rcx+18h]
0x180036abc  ja      short loc_180036AEC
0x180036abe  cmp     qword ptr [rcx+18h], 7
0x180036ac3  jbe     short loc_180036ACA
0x180036ac5  mov     r15, [rcx]
0x180036ac8  jmp     short loc_180036ACD
0x180036aca  mov     r15, rcx
0x180036acd  mov     [rcx+10h], rdx
0x180036ad1  lea     rbx, [rdx+rdx]
0x180036ad5  mov     r8, rbx; Size
0x180036ad8  mov     rdx, r13; Src
0x180036adb  mov     rcx, r15; void *
0x180036ade  call    memmove_0
0x180036ae3  xor     eax, eax
0x180036ae5  mov     [r15+rbx], ax
0x180036aea  jmp     short loc_180036AF5
0x180036aec  mov     r9, r13
0x180036aef  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180036af4  nop
0x180036af5  mov     rcx, r12
0x180036af8  call    ??1?$test_data_control@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(void)
0x180036afd  lea     rcx, [rdi+20h]
0x180036b01  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::ensure_data(void)
0x180036b06  mov     rbx, [rax]
0x180036b09  lea     r15, [rdi+168h]
0x180036b10  mov     [r15], rbx
0x180036b13  test    rbx, rbx
0x180036b16  jz      short loc_180036B1F
0x180036b18  lock inc dword ptr [rbx+138h]
0x180036b1f  mov     [rsp+338h+var_208], rbx
0x180036b27  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180036b2e  call    cs:__imp_EnterCriticalSection
0x180036b34  inc     dword ptr [rbx+0F0h]
0x180036b3a  mov     rax, [r15]
0x180036b3d  mov     [rsp+338h+var_208], rax
0x180036b45  mov     dword ptr [rax+130h], 2
0x180036b4f  mov     rcx, r15
0x180036b52  call    ??1?$test_data_control@V?$merged_data@U_tip_CloudRequestorInterfaceTip@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip,ConsentCoordinationTip::_tip_CloudRequestorInterfaceTip>>(void)
0x180036b57  mov     rcx, [rdi+5A0h]
0x180036b5e  test    rcx, rcx
0x180036b61  jnz     short loc_180036B68
0x180036b63  mov     rax, rsi
0x180036b66  jmp     short loc_180036BB8
0x180036b68  lea     rbx, [rdi+4F0h]
0x180036b6f  mov     [rbx], rsi
0x180036b72  lea     r15, [rdi+4F8h]
0x180036b79  mov     [r15], esi
0x180036b7c  mov     [rdi+500h], rsi
0x180036b83  mov     [rdi+508h], rsi
0x180036b8a  mov     rax, [rcx]
0x180036b8d  mov     r8, rbx
0x180036b90  lea     rdx, ??$guid_v@UIWebAccount@Credentials@Security@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Security::Credentials::IWebAccount>
0x180036b97  mov     rax, [rax]
0x180036b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b9f  test    eax, eax
0x180036ba1  jns     short loc_180036BAD
0x180036ba3  mov     rdx, r15
0x180036ba6  mov     ecx, eax
0x180036ba8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180036bad  mov     rax, [rbx]
0x180036bb0  mov     [rsp+338h+var_1B8], rax
0x180036bb8  mov     [rdi+170h], rax
0x180036bbf  lea     rcx, aCloudrequestor_3; "CloudRequestorInterface - creating serv"...
0x180036bc6  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180036bcb  lea     r12, [rdi+178h]
0x180036bd2  mov     [rdi+180h], r12
0x180036bd9  lea     r13, [rdi+1D8h]
0x180036be0  lea     r8, ?c_ucsConsentScopeValue@CloudRequestorInterface@@0QEBGEB; ushort const * const CloudRequestorInterface::c_ucsConsentScopeValue
0x180036be7  lea     rdx, ?c_ucsConsentScopeName@CloudRequestorInterface@@0QEBGEB; ushort const * const CloudRequestorInterface::c_ucsConsentScopeName
0x180036bee  mov     rcx, r13
0x180036bf1  call    ??$?0AEBQEBGAEBQEBG$0A@@?$pair@$$CBUhstring@winrt@@U12@@std@@QEAA@AEBQEBG0@Z; std::pair<winrt::hstring const,winrt::hstring>::pair<winrt::hstring const,winrt::hstring>(ushort const * const &,ushort const * const &)
0x180036bf6  nop
0x180036bf7  lea     rdx, [rdi+4C0h]
0x180036bfe  mov     [rdx], r13
0x180036c01  lea     r15, [rdi+1E8h]
0x180036c08  mov     [rdi+4C8h], r15
0x180036c0f  lea     rcx, [rdi+198h]
0x180036c16  call    ??0?$unordered_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@QEAA@V?$initializer_list@U?$pair@$$CBUhstring@winrt@@U12@@std@@@1@@Z; std::unordered_map<winrt::hstring,winrt::hstring>::unordered_map<winrt::hstring,winrt::hstring>(std::initializer_list<std::pair<winrt::hstring const,winrt::hstring>>)
0x180036c1b  nop
0x180036c1c  mov     rdx, rax
0x180036c1f  mov     rcx, r15
0x180036c22  call    ??$single_threaded_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@winrt@@YA?AU?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@Windows@0@$$QEAV?$unordered_map@Uhstring@winrt@@U12@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@@Z; winrt::single_threaded_map<winrt::hstring,winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::hstring>>>(std::unordered_map<winrt::hstring,winrt::hstring> &&)
0x180036c27  nop
0x180036c28  mov     [rdi+190h], sil
0x180036c2f  lea     rbx, [rdi+188h]
0x180036c36  mov     rax, [rax]
0x180036c39  mov     [rbx], rax
0x180036c3c  cmp     word ptr cs:aProd+8, si; ""
0x180036c43  jnz     loc_1800376F3
0x180036c49  lea     rax, [rdi+1F8h]
0x180036c50  mov     dword ptr [rax], 1
0x180036c56  mov     dword ptr [rdi+1FCh], 4
0x180036c60  lea     rcx, aProd; "prod"
0x180036c67  mov     [rdi+208h], rcx
0x180036c6e  lea     r9, [rdi+1F0h]
0x180036c75  mov     [r9], rax
0x180036c78  cmp     word ptr cs:aHttpsConsentCo+44h, si; ""
0x180036c7f  jnz     loc_1800376F3
0x180036c85  lea     rax, [rdi+218h]
0x180036c8c  mov     dword ptr [rax], 1
0x180036c92  mov     dword ptr [rdi+21Ch], 22h ; '"'
0x180036c9c  lea     rcx, aHttpsConsentCo; "https://consent.config.office.com/"
0x180036ca3  mov     [rdi+228h], rcx
0x180036caa  lea     r8, [rdi+210h]
0x180036cb1  mov     [r8], rax
0x180036cb4  cmp     word ptr cs:a76058868F3974b+48h, si; ""
0x180036cbb  jnz     loc_1800376F3
0x180036cc1  lea     rax, [rdi+238h]
0x180036cc8  mov     dword ptr [rax], 1
0x180036cce  mov     dword ptr [rdi+23Ch], 24h ; '$'
0x180036cd8  lea     rcx, a76058868F3974b; "76058868-f397-4bdc-bf2c-ee6fedd44410"
0x180036cdf  mov     [rdi+248h], rcx
0x180036ce6  lea     rdx, [rdi+230h]
0x180036ced  mov     [rdx], rax
0x180036cf0  mov     [rsp+338h+var_318], rbx
0x180036cf5  mov     rcx, r12
0x180036cf8  call    ??0EnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@QEAA@AEBUhstring@param@4@00AEBU?$map@Uhstring@winrt@@U12@@64@@Z; winrt::Windows::Internal::CloudRequestor::EnvironmentConfig::EnvironmentConfig(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::map<winrt::hstring,winrt::hstring> const &)
0x180036cfd  mov     [rsp+338h+var_2E8], rax
0x180036d02  lea     r12, [rdi+250h]
0x180036d09  mov     ecx, 3; this
0x180036d0e  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180036d13  mov     [rsp+338h+var_2B8], rax
0x180036d1b  lea     rcx, [rax+1Ch]; Destination
0x180036d1f  mov     eax, 6
0x180036d24  mov     r9d, eax; SourceSize
0x180036d27  lea     r8, aUcs; "ucs"
0x180036d2e  mov     edx, eax; DestinationSize
0x180036d30  call    memcpy_s
0x180036d35  mov     rax, [rsp+338h+var_2B8]
0x180036d3d  mov     [r12], rax
0x180036d41  mov     r8, [rsp+338h+var_2E8]
0x180036d46  mov     rdx, r12
0x180036d49  lea     r12, [rdi+258h]
0x180036d50  mov     rcx, r12
0x180036d53  call    ?CreateServiceConfiguration@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@std@@Uhstring@winrt@@UEnvironmentConfig@1237@@Z; Windows::Internal::CloudRequestor::CreateServiceConfiguration(winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig)
0x180036d58  nop
0x180036d59  mov     al, [rdi+190h]
0x180036d5f  mov     [rsp+338h+var_1A0], al
0x180036d66  test    al, al
0x180036d68  jnz     short loc_180036D6D
0x180036d6a  mov     [rbx], rsi
0x180036d6d  mov     rax, [rbx]
0x180036d70  mov     [rsp+338h+var_1A8], rax
0x180036d78  test    rax, rax
0x180036d7b  jz      short loc_180036D86
0x180036d7d  mov     rcx, rbx
0x180036d80  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180036d85  nop
0x180036d86  mov     rax, [r15]
0x180036d89  mov     [rsp+338h+var_1C8], rax
0x180036d91  test    rax, rax
0x180036d94  jz      short loc_180036D9F
0x180036d96  mov     rcx, r15
0x180036d99  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180036d9e  nop
0x180036d9f  lea     rcx, [rdi+1B0h]
0x180036da6  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<winrt::hstring const,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>>>>>>(void)
0x180036dab  lea     rcx, [rdi+1A0h]
0x180036db2  call    ??1?$list@U?$pair@$$CBUhstring@winrt@@U12@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<winrt::hstring const,winrt::hstring>>::~list<std::pair<winrt::hstring const,winrt::hstring>>(void)
0x180036db7  nop
0x180036db8  lea     r9, ??1?$pair@$$CBUhstring@winrt@@U12@@std@@QEAA@XZ; void (*)(void *)
0x180036dbf  mov     ebx, 1
0x180036dc4  mov     r8d, ebx; unsigned __int64
0x180036dc7  lea     edx, [rbx+0Fh]; unsigned __int64
0x180036dca  mov     rcx, r13; void *
0x180036dcd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180036dd2  mov     [rdi+268h], rsi
0x180036dd9  mov     [rdi+270h], rsi
0x180036de0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification> `wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl(void)'::`2'::impl
0x180036de7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(void)
0x180036dec  test    al, al
0x180036dee  mov     rax, [rdi+260h]
0x180036df5  mov     [rsp+338h+var_2C8], rax
0x180036dfa  jz      loc_180036ED8
0x180036e00  lea     rdx, [rdi+278h]
0x180036e07  mov     [rdx], rsi
0x180036e0a  mov     [rdi+280h], rsi
0x180036e11  test    rax, rax
0x180036e14  jz      short loc_180036E26
0x180036e16  mov     rax, [rdi+260h]
0x180036e1d  mov     [rsp+338h+var_2C8], rax
0x180036e22  lock add [rax+8], ebx
0x180036e26  mov     rax, [r12]
0x180036e2a  mov     [rsp+338h+var_2D0], rax
0x180036e2f  mov     [rdx], rax
0x180036e32  mov     rax, [rdi+260h]
0x180036e39  mov     [rsp+338h+var_2C8], rax
0x180036e3e  mov     [rdi+280h], rax
0x180036e45  lea     rcx, [rdi+288h]
0x180036e4c  call    ?CreateTokenBroker@CloudRequestor@Internal@Windows@@YA?AV?$shared_ptr@VITokenBroker@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@5@@Z; Windows::Internal::CloudRequestor::CreateTokenBroker(std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>)
0x180036e51  mov     rcx, [rax]
0x180036e54  mov     r15, [rax+8]
0x180036e58  mov     [rax], rsi
0x180036e5b  mov     [rax+8], rsi
0x180036e5f  mov     [rdi+268h], rcx
0x180036e66  mov     [rdi+270h], r15
0x180036e6d  mov     rax, [rdi+290h]
0x180036e74  mov     [rsp+338h+var_228], rax
0x180036e7c  test    rax, rax
0x180036e7f  jz      loc_18003700C
  ... truncated ...
```
