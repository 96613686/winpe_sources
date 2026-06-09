# winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UpdateDefaultAccountAsync$_ResumeCoro$1

- ea: `0x18002be40`
- end: `0x18002cdf4`
- name: `winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UpdateDefaultAccountAsync$_ResumeCoro$1`
- size: `4020`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ce5c`

## callees

- `0x180002834`
- `0x180003390`
- `0x1800034f7`
- `0x1800035ab`
- `0x180005d24`
- `0x180007364`
- `0x18000d440`
- `0x18000e70c`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fb28`
- `0x1800131f8`
- `0x180013e40`
- `0x180013efc`
- `0x180014364`
- `0x180018144`
- `0x180018290`
- `0x18001962c`
- `0x18001c1d4`
- `0x18001cb0c`
- `0x18001cb64`
- `0x18001e608`
- `0x18001ef30`
- `0x18001f04c`
- `0x18001f3fc`
- `0x180021124`
- `0x1800229ac`
- `0x180022c78`
- `0x180023648`
- `0x1800237d0`
- `0x1800272dc`
- `0x18002770c`
- `0x18002bd60`
- `0x18002be40`
- `0x18002d1a0`
- `0x18002d284`
- `0x18002d4a0`
- `0x18002d760`
- `0x18002d81c`
- `0x18002d8b4`
- `0x18002d994`
- `0x1800307ec`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002cd8d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002cd8d`
- `msvcp_win!_Thrd_yield` at `0x18002c42e`
- `msvcp_win!_Thrd_yield` at `0x18002c4a0`
- `msvcp_win!_Thrd_yield` at `0x18002c585`
- `msvcp_win!_Thrd_yield` at `0x18002c653`
- `msvcp_win!_Thrd_yield` at `0x18002c42e`
- `msvcp_win!_Thrd_yield` at `0x18002c4a0`
- `msvcp_win!_Thrd_yield` at `0x18002c585`
- `msvcp_win!_Thrd_yield` at `0x18002c653`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c5eb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c701`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c9c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca14`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cb82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c5eb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c701`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c9c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca14`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cb82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c3fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c3fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c2b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c362`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c3a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c2b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c362`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c3a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c3cb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c943`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002ccaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c943`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002ccaa`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c95a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002ccc1`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c95a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002ccc1`

## string_xrefs

- `0x18002c89e`: `Web Account was removed. Delete default path.`
- `0x18002cc47`: `Account ID doesn't match primary account ID. Delete default path.`
- `0x18002ca4a`: `Adding isAad to registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::UpdateDefaultAccountAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // r15
  __int64 v3; // rdx
  signed __int64 v4; // rax
  signed __int64 v5; // rtt
  __int64 v6; // rcx
  const struct winrt::impl::slim_source_location *v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // r14
  __int64 CloudStoreAsync; // rax
  const struct winrt::impl::slim_source_location *v14; // rax
  wil::details *v15; // rcx
  unsigned int v16; // r13d
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64, __int64, __int64); // r10
  int v18; // r15d
  int v19; // ebx
  int v20; // edx
  unsigned __int64 v21; // r15
  char v22; // r11
  unsigned int v23; // r8d
  unsigned __int64 v24; // rax
  LPVOID v25; // rtt
  __int64 v26; // rbx
  __int64 v27; // rdx
  char v28; // r15
  __int64 v29; // rbx
  volatile signed __int32 *v30; // rbx
  struct _RTL_CRITICAL_SECTION *v31; // r15
  volatile signed __int32 *v32; // rbx
  volatile __int64 *v33; // rbx
  volatile __int64 *v34; // rbx
  __int64 PrimaryIdAsync; // rax
  const struct winrt::impl::slim_source_location *v36; // rax
  volatile __int64 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  int v39; // r14d
  HANDLE v40; // rax
  __int64 *v41; // r15
  volatile __int64 *v42; // rbx
  __int64 v43; // r13
  int v44; // eax
  __int64 v45; // rcx
  __int64 v46; // rax
  unsigned int v47; // edx
  volatile signed __int32 *v48; // rbx
  int v49; // eax
  HANDLE v50; // rax
  volatile signed __int32 *v51; // rbx
  int v52; // r14d
  HANDLE ProcessHeap; // rax
  _WORD *v54; // rax
  struct winrt::impl::shared_hstring_header *v55; // rbx
  int v56; // eax
  HANDLE v57; // rax
  volatile signed __int32 *v58; // rbx
  int v59; // r14d
  HANDLE v60; // rax
  unsigned int v61; // edx
  volatile signed __int32 *v62; // r13
  __int64 *v63; // r12
  int v64; // eax
  HANDLE v65; // rax
  __int64 v66; // r13
  const WCHAR *v67; // rax
  int v68; // eax
  HANDLE v69; // rax
  int v70; // eax
  HANDLE v71; // rax
  volatile signed __int32 *v72; // rbx
  int v73; // r14d
  HANDLE v74; // rax
  unsigned int v75; // edx
  __int64 v76; // rcx
  int v77; // eax
  const unsigned __int16 *v78; // rdx
  signed int v79; // eax
  int v80; // eax
  HANDLE v81; // rax
  winrt::hstring *v82; // r12
  HKEY v83; // rcx
  const unsigned __int16 *v84; // rdx
  const WCHAR *v85; // rbx
  signed int v86; // eax
  __int64 v87; // rax
  __int64 v88; // rbx
  _QWORD *v89; // rcx
  unsigned int v90; // [rsp+20h] [rbp-1F8h]
  LPVOID lpMem; // [rsp+30h] [rbp-1E8h]
  struct winrt::impl::shared_hstring_header *lpMema; // [rsp+30h] [rbp-1E8h]
  __int64 v93; // [rsp+58h] [rbp-1C0h]
  _BYTE pExceptionObject[24]; // [rsp+A8h] [rbp-170h] BYREF
  _BYTE v95[24]; // [rsp+C0h] [rbp-158h] BYREF
  _BYTE v96[24]; // [rsp+D8h] [rbp-140h] BYREF
  __int64 v97; // [rsp+F0h] [rbp-128h]
  __int64 v98; // [rsp+110h] [rbp-108h]
  volatile signed __int32 *v99; // [rsp+168h] [rbp-B0h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]
  unsigned int v101; // [rsp+228h] [rbp+10h]
  __int64 v102; // [rsp+230h] [rbp+18h]
  signed __int64 v103; // [rsp+230h] [rbp+18h]
  __int64 v104; // [rsp+230h] [rbp+18h]
  __int64 v105; // [rsp+230h] [rbp+18h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_200;
    case 2:
      v3 = *(_QWORD *)(a1 + 504);
      *(_QWORD *)(a1 + 16) = 0;
      if ( !v3 )
        goto LABEL_8;
      *(_QWORD *)(a1 + 16) = v3;
      v4 = *(_QWORD *)(v3 + 8);
      while ( v4 >= 0 )
      {
        v5 = v4;
        v4 = _InterlockedCompareExchange64((volatile signed __int64 *)(v3 + 8), v4 + 1, v4);
        if ( v5 == v4 )
          goto LABEL_8;
      }
      _InterlockedIncrement((volatile signed __int32 *)(2 * v4 + 24));
LABEL_8:
      *(_QWORD *)(a1 + 480) = a1 - 112;
      *(_BYTE *)(a1 + 24) = 0;
      v6 = *(unsigned int *)(a1 - 112 + 96);
      if ( (_DWORD)v6 == 2 )
      {
        v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 296);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v7);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_WORD *)v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v6, a1);
      return;
    case 4:
      *(_QWORD *)(a1 + 320) = &qword_18009CFB8;
      _InterlockedAdd64(&qword_18009CFB8, 1u);
      v8 = winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics> )
      {
        *(_DWORD *)(a1 + 336) = 0;
        *(_DWORD *)(a1 + 344) = 0;
        *(_QWORD *)(a1 + 352) = 0;
        *(_QWORD *)(a1 + 360) = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a1 + 336);
        if ( v9 < 0 )
          winrt::throw_hresult((unsigned int)v9, a1 + 344);
        v11 = *(_DWORD *)(a1 + 336);
        v12 = -1;
        _InterlockedAdd64(&qword_18009CFB8, 0xFFFFFFFFFFFFFFFFuLL);
      }
      else
      {
        v12 = -1;
        _InterlockedAdd64(&qword_18009CFB8, 0xFFFFFFFFFFFFFFFFuLL);
        *(_QWORD *)(a1 + 328) = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType;
        v11 = winrt::impl::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::call<enum winrt::Windows::System::Profile::SystemOutOfBoxExperienceState (*)(winrt::Windows::System::Profile::ISystemSetupInfoStatics const &)>();
      }
      if ( v11 != 2 )
        goto LABEL_78;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix>::GetImpl'::`2'::impl) )
      {
        tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>>(a1 + 32);
        lpMem = (LPVOID)*Feature_UnifiedConsentCDSHangFix__descriptor;
        v102 = *Feature_UnifiedConsentCDSHangFix__descriptor;
        v16 = *Feature_UnifiedConsentCDSHangFix__descriptor;
        if ( (*(_DWORD *)Feature_UnifiedConsentCDSHangFix__descriptor & 0xC) == 0xC )
        {
          LODWORD(v21) = HIDWORD(*Feature_UnifiedConsentCDSHangFix__descriptor);
LABEL_48:
          v26 = *(_QWORD *)(a1 + 88);
          v99 = (volatile signed __int32 *)v26;
          *(_QWORD *)(a1 + 96) = v26;
          if ( v26 )
            _InterlockedIncrement((volatile signed __int32 *)(v26 + 280));
          EnterCriticalSection((LPCRITICAL_SECTION)(v26 + 200));
          ++*(_DWORD *)(v26 + 240);
          *(_DWORD *)(v26 + 276) = v21;
          tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>(a1 + 96);
          UnifiedConsentLogging::TraceLoggingInfo("timeoutInMs: %u", v21);
          v104 = *(_QWORD *)winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::TryLoadCloudStoreAsync(
                              *(_QWORD *)(a1 + 504),
                              a1 + 104);
          if ( *(_QWORD *)(a1 + 104) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 104);
          *(_BYTE *)(a1 + 112) = 0;
          wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v104, v27, (unsigned int)v21, a1 + 112);
          v28 = *(_BYTE *)(a1 + 112);
          v29 = *(_QWORD *)(a1 + 88);
          v99 = (volatile signed __int32 *)v29;
          *(_QWORD *)(a1 + 120) = v29;
          if ( v29 )
            _InterlockedIncrement((volatile signed __int32 *)(v29 + 280));
          EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 200));
          ++*(_DWORD *)(v29 + 240);
          *(_BYTE *)(v29 + 272) = v28;
          tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>(a1 + 120);
          v99 = *(volatile signed __int32 **)(a1 + 88);
          v30 = v99 + 2;
          v31 = (struct _RTL_CRITICAL_SECTION *)(v99 + 50);
          EnterCriticalSection((LPCRITICAL_SECTION)v99 + 5);
          *((_DWORD *)v99 + 18) |= 0x300u;
          if ( *((_QWORD *)v30 + 30) )
            tip2::details::shared_data<0,0,0>::complete_helper(v30, 2);
          if ( v31 )
            LeaveCriticalSection(v31);
          v32 = *(volatile signed __int32 **)(a1 + 88);
          v99 = v32;
          if ( v32 && !_InterlockedDecrement(v32 + 70) )
          {
            tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>::~merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>(v32);
            CoTaskMemFree((LPVOID)v32);
          }
          wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 40));
          v2 = a1 + 8;
          goto LABEL_78;
        }
        *(_DWORD *)(a1 + 368) = 0;
        v101 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(v15);
        *(_DWORD *)(a1 + 372) = 0;
        *(_DWORD *)(a1 + 376) = 0;
        v17 = (__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, __int64))g_wil_details_internalGetFeatureVariant;
        if ( g_wil_details_internalGetFeatureVariant
          || (v17 = (__int64 (__fastcall *)(__int64, _QWORD, __int64, __int64, __int64))g_wil_details_apiGetFeatureVariant) != 0 )
        {
          v18 = v17(49028071, 0, a1 + 376, a1 + 372, a1 + 368);
        }
        else
        {
          v18 = 0;
        }
        v19 = (16 * (v18 & 0x80)) | (*(_DWORD *)(a1 + 372) != 0 ? 0x400 : 0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::GetImpl'::`2'::impl) )
        {
          if ( (v18 & 0xFFFFFE7F) != 0 )
          {
            v19 ^= (v19 ^ ((v18 & 0xFFFFFE7F) << 12)) & 0x3F000;
            if ( (v18 & 0x100) != 0 )
            {
              v20 = *(_DWORD *)(a1 + 376);
LABEL_36:
              if ( !v101 )
                *(_DWORD *)(a1 + 368) = 0;
              LODWORD(v21) = HIDWORD(v102);
              while ( 1 )
              {
                v22 = v16;
                v23 = v16;
                v103 = __PAIR64__(v21, v16);
                if ( (v16 & 8) == 0 )
                {
                  LODWORD(v21) = v20;
                  v23 = v19 & 0x800 | (*(_DWORD *)(a1 + 368) != 0 ? 8 : 0) | v19 & 0x3F000 ^ v16 & 0xFFFC07F7;
                  v103 = __PAIR64__(v20, v23);
                }
                if ( (v16 & 4) == 0 )
                  LODWORD(v103) = v23 ^ ((unsigned __int16)v23 ^ (unsigned __int16)v19) & 0x400 | 4;
                v25 = lpMem;
                v24 = _InterlockedCompareExchange64(
                        Feature_UnifiedConsentCDSHangFix__descriptor,
                        v103,
                        (signed __int64)lpMem);
                v16 = v24;
                if ( v25 == (LPVOID)v24 )
                  break;
                v21 = HIDWORD(v24);
                lpMem = (LPVOID)v24;
              }
              if ( (v22 & 4) == 0 )
                wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
                  Feature_UnifiedConsentCDSHangFix__descriptor,
                  0,
                  v101,
                  8);
              goto LABEL_48;
            }
          }
          else
          {
            v19 |= 0x1000u;
          }
        }
        v20 = 11000;
        goto LABEL_36;
      }
      CloudStoreAsync = winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::TryLoadCloudStoreAsync(
                          *(_QWORD *)(v2 + 496),
                          a1 + 128);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v14 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 384);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v95, v14);
        throw (winrt::hresult_canceled *)v95;
      }
      *(_QWORD *)(a1 + 136) = 0;
      *(_QWORD *)(a1 + 144) = CloudStoreAsync;
      *(_QWORD *)(a1 + 152) = 0;
      *(_BYTE *)(a1 + 160) = 1;
      *(_WORD *)v2 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>::promise_type>(
                              a1 + 136,
                              a1) )
        return;
LABEL_72:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 136);
      v34 = *(volatile __int64 **)(a1 + 136);
      if ( v34 )
      {
        v97 = *(_QWORD *)(a1 + 136);
        while ( _InterlockedExchange64(v34, 0) == 1 )
          _Thrd_yield();
      }
      v10 = a1 + 128;
      if ( *(_QWORD *)(a1 + 128) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v10);
LABEL_78:
      winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::GetStoredDefaultId(
        v10,
        a1 + 168);
      PrimaryIdAsync = winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::GetPrimaryIdAsync(
                         *(_QWORD *)(v2 + 496),
                         a1 + 176);
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v36 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 408);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v96, v36);
        throw (winrt::hresult_canceled *)v96;
      }
      *(_QWORD *)(a1 + 184) = 0;
      *(_QWORD *)(a1 + 192) = PrimaryIdAsync;
      *(_QWORD *)(a1 + 200) = 0;
      *(_BYTE *)(a1 + 208) = 1;
      *(_WORD *)v2 = 8;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Shell::ConsentUx::PrimaryIdResult>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator *>::promise_type>(
                              a1 + 184,
                              a1) )
        return;
LABEL_98:
      v41 = (__int64 *)(a1 + 216);
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Shell::ConsentUx::PrimaryIdResult>,1>::await_resume(
        a1 + 184,
        a1 + 216);
      v42 = *(volatile __int64 **)(a1 + 184);
      if ( v42 )
      {
        v98 = *(_QWORD *)(a1 + 184);
        while ( _InterlockedExchange64(v42, 0) == 1 )
          _Thrd_yield();
      }
      v43 = *(_QWORD *)(a1 + 480);
      v105 = v43;
      if ( *(_QWORD *)(a1 + 176) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 176);
      *(_QWORD *)(a1 + 224) = 0;
      v44 = winrt::impl::consume_Windows_Internal_Shell_ConsentUx_IPrimaryIdResult<winrt::Windows::Internal::Shell::ConsentUx::IPrimaryIdResult>::Reason(a1 + 216);
      v45 = a1 + 216;
      if ( v44 )
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Internal_Shell_ConsentUx_IPrimaryIdResult<winrt::Windows::Internal::Shell::ConsentUx::IPrimaryIdResult>::Reason(v45) == 1 )
        {
          if ( *v41 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 216);
          v51 = *(volatile signed __int32 **)(a1 + 168);
          if ( v51 )
          {
            v52 = _InterlockedDecrement(v51 + 6);
            if ( v52 )
            {
              if ( v52 < 0 )
                goto LABEL_159;
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v51);
            }
            *(_QWORD *)(a1 + 168) = 0;
          }
          if ( *(_QWORD *)(a1 + 16) )
            winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
          v54 = (_WORD *)(a1 + 8);
          goto LABEL_199;
        }
      }
      else
      {
        v46 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
                v45,
                a1 + 232);
        winrt::hstring::operator=(a1 + 224, v46);
        v48 = *(volatile signed __int32 **)(a1 + 232);
        if ( v48 )
        {
          v49 = _InterlockedDecrement(v48 + 6);
          if ( v49 )
          {
            if ( v49 < 0 )
              abort();
          }
          else
          {
            v50 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v50, 0, (LPVOID)v48);
          }
        }
      }
      v55 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x39, v47);
      memcpy_s((char *)v55 + 28, 0x72u, L"Software\\Microsoft\\Windows\\CurrentVersion\\UnifiedConsent\\", 0x72u);
      *(_QWORD *)(a1 + 240) = v55;
      v93 = *(_QWORD *)(a1 + 224);
      if ( v93 )
      {
        UnifiedConsentLogging::TraceLoggingInfo("Adding isAad to registry");
        lpMema = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x39, v75);
        memcpy_s((char *)lpMema + 28, 0x72u, L"Software\\Microsoft\\Windows\\CurrentVersion\\UnifiedConsent\\", 0x72u);
        *(_QWORD *)(a1 + 264) = lpMema;
        *(_BYTE *)(a1 + 432) = 0;
        v76 = *v41;
        *(_DWORD *)(a1 + 440) = 0;
        *(_QWORD *)(a1 + 448) = 0;
        *(_QWORD *)(a1 + 456) = 0;
        v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v76 + 64LL))(v76);
        if ( v77 < 0 )
          winrt::throw_hresult((unsigned int)v77, a1 + 440);
        if ( lpMema )
          v78 = (const unsigned __int16 *)*((_QWORD *)lpMema + 2);
        else
          v78 = &Name;
        *(_DWORD *)(a1 + 464) = *(_BYTE *)(a1 + 432) != 0;
        v79 = _RegSetKeyValue((HKEY)(a1 + 464), v78, L"isAAD", 4u, (const void *)(a1 + 464), 4u);
        if ( v79 > 0 )
          v79 = (unsigned __int16)v79 | 0x80070000;
        if ( v79 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x149,
            (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\lib\\unifiedconsentcoordinator.cpp",
            (const char *)(unsigned int)v79,
            v90);
        if ( lpMema )
        {
          v80 = _InterlockedDecrement((volatile signed __int32 *)lpMema + 6);
          if ( v80 )
          {
            if ( v80 < 0 )
              goto LABEL_177;
          }
          else
          {
            v81 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v81, 0, lpMema);
          }
        }
        v82 = (winrt::hstring *)(a1 + 168);
        if ( (unsigned __int8)winrt::operator==(a1 + 168, a1 + 224) )
        {
LABEL_194:
          winrt::hstring::~hstring((winrt::hstring *)(a1 + 240));
          winrt::hstring::~hstring((winrt::hstring *)(a1 + 224));
          if ( *v41 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 216);
          winrt::hstring::~hstring(v82);
          if ( *(_QWORD *)(a1 + 16) )
            winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
          v54 = (_WORD *)(a1 + 8);
          goto LABEL_199;
        }
        v83 = *(HKEY *)(v93 + 16);
        if ( v55 )
        {
          v84 = (const unsigned __int16 *)*((_QWORD *)v55 + 2);
          v85 = &Name;
        }
        else
        {
          v85 = &Name;
          v84 = &Name;
        }
        do
          ++v12;
        while ( *((_WORD *)v83 + v12) );
        if ( v12 >= 0x7FFFFFFF )
        {
          LOWORD(v86) = 534;
        }
        else
        {
          v86 = _RegSetKeyValue(v83, v84, L"DEFAULTACCOUNT", 1u, v83, 2 * v12 + 2);
          if ( v86 <= 0 )
            goto LABEL_188;
        }
        v86 = (unsigned __int16)v86 | 0x80070000;
LABEL_188:
        if ( v86 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x14F,
            (unsigned int)"onecoreuap\\shell\\consentux\\unifiedconsent\\lib\\unifiedconsentcoordinator.cpp",
            (const char *)(unsigned int)v86,
            v90);
        if ( *(_QWORD *)v82 )
        {
          UnifiedConsentLogging::TraceLoggingInfo("Account ID doesn't match primary account ID. Delete default path.");
          v87 = winrt::hstring::hstring((winrt::hstring *)(a1 + 272), L"DEFAULTACCOUNT");
          winrt::operator+(a1 + 280, a1 + 240, v87);
          winrt::hstring::~hstring((winrt::hstring *)(a1 + 272));
          if ( *(_QWORD *)(a1 + 280) )
            v85 = *(const WCHAR **)(*(_QWORD *)(a1 + 280) + 16LL);
          RegDeleteTreeW(HKEY_CURRENT_USER, v85);
          RegDeleteKeyValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\UnifiedConsent\\",
            L"DEFAULTACCOUNT");
          winrt::hstring::~hstring((winrt::hstring *)(a1 + 280));
          v82 = (winrt::hstring *)(a1 + 168);
        }
        goto LABEL_194;
      }
      if ( !*(_QWORD *)(a1 + 168) )
      {
        UnifiedConsentLogging::TraceLoggingInfo("Unable to get the primary account ID");
        if ( !v55 )
        {
LABEL_127:
          if ( *v41 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 216);
          v58 = *(volatile signed __int32 **)(a1 + 168);
          if ( !v58 )
            goto LABEL_134;
          v59 = _InterlockedDecrement(v58 + 6);
          if ( !v59 )
          {
            v60 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v60, 0, (LPVOID)v58);
LABEL_133:
            *(_QWORD *)(a1 + 168) = 0;
LABEL_134:
            if ( *(_QWORD *)(a1 + 16) )
              winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
            v54 = (_WORD *)(a1 + 8);
            goto LABEL_199;
          }
          if ( v59 >= 0 )
            goto LABEL_133;
LABEL_159:
          abort();
        }
        v56 = _InterlockedDecrement((volatile signed __int32 *)v55 + 6);
        if ( !v56 )
        {
          v57 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v57, 0, v55);
          goto LABEL_127;
        }
        if ( v56 >= 0 )
          goto LABEL_127;
LABEL_152:
        abort();
      }
      UnifiedConsentLogging::TraceLoggingInfo("Web Account was removed. Delete default path.");
      v62 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xE, v61);
      memcpy_s((void *const)(v62 + 7), 0x1Cu, L"DEFAULTACCOUNT", 0x1Cu);
      *(_QWORD *)(a1 + 248) = v62;
      v63 = (__int64 *)(a1 + 256);
      winrt::operator+(a1 + 256, a1 + 240, a1 + 248);
      if ( v62 )
      {
        v64 = _InterlockedDecrement(v62 + 6);
        if ( v64 )
        {
          if ( v64 < 0 )
            goto LABEL_177;
        }
        else
        {
          v65 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v65, 0, (LPVOID)v62);
        }
      }
      v66 = *v63;
      if ( *v63 )
        v67 = *(const WCHAR **)(v66 + 16);
      else
        v67 = &Name;
      RegDeleteTreeW(HKEY_CURRENT_USER, v67);
      RegDeleteKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\UnifiedConsent\\",
        L"DEFAULTACCOUNT");
      if ( !v66 )
        goto LABEL_148;
      v68 = _InterlockedDecrement((volatile signed __int32 *)(v66 + 24));
      if ( v68 )
      {
        if ( v68 >= 0 )
          goto LABEL_148;
LABEL_177:
        abort();
      }
      v69 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v69, 0, (LPVOID)v66);
LABEL_148:
      if ( v55 )
      {
        v70 = _InterlockedDecrement((volatile signed __int32 *)v55 + 6);
        if ( v70 )
        {
          if ( v70 < 0 )
            goto LABEL_152;
        }
        else
        {
          v71 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v71, 0, v55);
        }
      }
      if ( *v41 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 216);
      v72 = *(volatile signed __int32 **)(a1 + 168);
      if ( v72 )
      {
        v73 = _InterlockedDecrement(v72 + 6);
        if ( v73 )
        {
          if ( v73 < 0 )
            goto LABEL_159;
        }
        else
        {
          v74 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v74, 0, (LPVOID)v72);
        }
        *(_QWORD *)(a1 + 168) = 0;
      }
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
      v43 = v105;
      v54 = (_WORD *)(a1 + 8);
LABEL_199:
      *(_QWORD *)(a1 + 288) = v43;
      *v54 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_200:
        v88 = a1 - 112;
        *(_QWORD *)(a1 + 480) = a1 - 112;
        v89 = (_QWORD *)(a1 - 112 + 88);
        if ( *v89 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v89);
        if ( *(_QWORD *)(v88 + 80) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v88 + 80);
        __ExceptionPtrDestroy((void *)(v88 + 56));
        __1__root_implements_U__map_impl_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_V__unordered_map_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_U__hash_Uhstring_winrt___std__U__equal_to_Uhstring_winrt___8_V__allocator_U__pair___CBUhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__std___8__std__Umulti_threaded_collection_base_impl_2__impl_winrt__U__IMap_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_3_U__IMapView_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__5673_U__IIterable_U__IKeyValuePair_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_winrt___5673__impl_winrt__MEAA_XZ(a1 - 112);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x270u);
      }
      return;
    case 5:
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
      goto LABEL_200;
    case 6:
      v12 = -1;
      goto LABEL_72;
    case 7:
      v33 = *(volatile __int64 **)(a1 + 136);
      if ( v33 )
      {
        v97 = *(_QWORD *)(a1 + 136);
        while ( _InterlockedExchange64(v33, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 128) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
      goto LABEL_200;
    case 8:
      v12 = -1;
      goto LABEL_98;
    case 9:
      v37 = *(volatile __int64 **)(a1 + 184);
      if ( v37 )
      {
        v98 = *(_QWORD *)(a1 + 184);
        while ( _InterlockedExchange64(v37, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 176) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 176);
      v38 = *(volatile signed __int32 **)(a1 + 168);
      if ( v38 )
      {
        v39 = _InterlockedDecrement(v38 + 6);
        if ( v39 )
        {
          if ( v39 < 0 )
            abort();
        }
        else
        {
          v40 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v40, 0, (LPVOID)v38);
        }
        *(_QWORD *)(a1 + 168) = 0;
      }
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref();
      goto LABEL_200;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18002be40  mov     [rsp+arg_0], rcx
0x18002be45  push    rbx
0x18002be46  push    rsi
0x18002be47  push    rdi
0x18002be48  push    r12
0x18002be4a  push    r13
0x18002be4c  push    r14
0x18002be4e  push    r15
0x18002be50  sub     rsp, 1E0h
0x18002be57  mov     rsi, [rsp+218h+arg_0]
0x18002be5f  lea     r15, [rsi+8]
0x18002be63  movzx   eax, word ptr [r15]
0x18002be67  mov     [rsp+218h+var_1D0], ax
0x18002be6c  mov     r13d, 1
0x18002be72  add     ax, r13w
0x18002be76  cmp     ax, 0Ah; switch 11 cases
0x18002be7a  ja      def_18002BE9A; jumptable 000000018002BE9A default case, case 1
0x18002be80  mov     [rsp+218h+var_1A0], r15
0x18002be85  movsx   rax, ax
0x18002be89  lea     rdx, cs:180000000h
0x18002be90  mov     ecx, ds:(jpt_18002BE9A - 180000000h)[rdx+rax*4]
0x18002be97  add     rcx, rdx
0x18002be9a  jmp     rcx; switch jump
0x18002be9c  xor     edi, edi; jumptable 000000018002BE9A case 4
0x18002be9e  jmp     loc_18002CD62
0x18002bea3  mov     rdx, [r15+1F0h]; jumptable 000000018002BE9A case 3
0x18002beaa  xor     edi, edi
0x18002beac  mov     [rsi+10h], rdi
0x18002beb0  test    rdx, rdx
0x18002beb3  jz      short loc_18002BED5
0x18002beb5  mov     [rsi+10h], rdx
0x18002beb9  mov     rax, [rdx+8]
0x18002bebd  test    rax, rax
0x18002bec0  js      short loc_18002BED0
0x18002bec2  lea     rcx, [rax+1]
0x18002bec6  lock cmpxchg [rdx+8], rcx
0x18002becc  jnz     short loc_18002BEBD
0x18002bece  jmp     short loc_18002BED5
0x18002bed0  lock inc dword ptr [rax+rax+18h]
0x18002bed5  lea     rax, [rsi-70h]
0x18002bed9  mov     [rsi+1E0h], rax
0x18002bee0  mov     [rsi+18h], dil
0x18002bee4  mov     ecx, [rax+60h]
0x18002bee7  nop
0x18002bee8  cmp     ecx, 2
0x18002beeb  jnz     short loc_18002BF1D
0x18002beed  lea     rcx, [rsi+128h]
0x18002bef4  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002bef9  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002befc  lea     rcx, [rsp+218h+pExceptionObject]; this
0x18002bf04  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18002bf09  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18002bf10  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x18002bf18  call    _CxxThrowException_0
0x18002bf1d  mov     r12d, 4
0x18002bf23  mov     [r15], r12w
0x18002bf27  mov     rdx, rsi
0x18002bf2a  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18002bf2f  nop
0x18002bf30  jmp     loc_18002CDB1
0x18002bf35  lea     rcx, [rsi+10h]; jumptable 000000018002BE9A case 6
0x18002bf39  mov     rax, [rcx]
0x18002bf3c  mov     [rsp+218h+lpMem], rax
0x18002bf41  xor     edi, edi
0x18002bf43  test    rax, rax
0x18002bf46  jz      short loc_18002BF4E
0x18002bf48  call    ?unconditional_release_ref@?$com_ptr@U?$map_impl@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@V?$unordered_map@Uhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@8@V?$allocator@U?$pair@$$CBUhstring@winrt@@UEnvironmentConfig@CloudRequestor@Internal@Windows@2@@std@@@8@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::map_impl<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig,std::unordered_map<winrt::hstring,winrt::Windows::Internal::CloudRequestor::EnvironmentConfig>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18002bf4d  nop
0x18002bf4e  jmp     loc_18002CD62
0x18002bf53  lea     rax, qword_18009CFB8; jumptable 000000018002BE9A case 5
0x18002bf5a  mov     [rsi+140h], rax
0x18002bf61  lock add cs:qword_18009CFB8, r13
0x18002bf69  mov     rcx, cs:??$factory_cache_entry_v@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>::winrt::factory_cache_entry<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Profile::SystemSetupInfo,winrt::Windows::System::Profile::ISystemSetupInfoStatics>
0x18002bf70  xor     edi, edi
0x18002bf72  test    rcx, rcx
0x18002bf75  jz      short loc_18002BFCC
0x18002bf77  lea     rbx, [rsi+150h]
0x18002bf7e  mov     [rbx], edi
0x18002bf80  lea     r14, [rsi+158h]
0x18002bf87  mov     [r14], edi
0x18002bf8a  mov     [rsi+160h], rdi
0x18002bf91  mov     [rsi+168h], rdi
0x18002bf98  mov     rax, [rcx]
0x18002bf9b  mov     rdx, rbx
0x18002bf9e  mov     rax, [rax+30h]
0x18002bfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfa7  test    eax, eax
0x18002bfa9  jns     short loc_18002BFB5
0x18002bfab  mov     rdx, r14
0x18002bfae  mov     ecx, eax
0x18002bfb0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002bfb5  mov     eax, [rbx]
0x18002bfb7  mov     [rsp+218h+arg_18], eax
0x18002bfbe  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002bfc2  lock add cs:qword_18009CFB8, r14
0x18002bfca  jmp     short loc_18002BFEE
0x18002bfcc  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002bfd0  lock add cs:qword_18009CFB8, r14
0x18002bfd8  lea     rdx, [rsi+148h]
0x18002bfdf  lea     rax, ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18002bfe6  mov     [rdx], rax
0x18002bfe9  call    ??$call@P6A?AW4SystemOutOfBoxExperienceState@Profile@System@Windows@winrt@@AEBUISystemSetupInfoStatics@2345@@Z@?$factory_cache_entry@USystemSetupInfo@Profile@System@Windows@winrt@@UISystemSetupInfoStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AW4SystemOutOfBoxExperienceState@Profile@System@Windows@2@AEBUISystemSetupInfoStatics@4562@@Z@Z
0x18002bfee  cmp     eax, 2
0x18002bff1  jnz     loc_18002C4CD
0x18002bff7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix>::GetImpl(void)'::`2'::impl
0x18002bffe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCDSHangFix>::__private_IsEnabled(void)
0x18002c003  test    al, al
0x18002c005  jnz     loc_18002C095
0x18002c00b  lea     rdx, [rsi+80h]
0x18002c012  mov     rcx, [r15+1F0h]
0x18002c019  call    ?TryLoadCloudStoreAsync@UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@67@XZ; winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::TryLoadCloudStoreAsync(void)
0x18002c01e  nop
0x18002c01f  mov     ecx, [rsi-10h]
0x18002c022  nop
0x18002c023  cmp     ecx, 2
0x18002c026  jnz     short loc_18002C058
0x18002c028  lea     rcx, [rsi+180h]
0x18002c02f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18002c034  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18002c037  lea     rcx, [rsp+218h+var_158]; this
0x18002c03f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18002c044  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18002c04b  lea     rcx, [rsp+218h+var_158]; pExceptionObject
0x18002c053  call    _CxxThrowException_0
0x18002c058  lea     rcx, [rsi+88h]
0x18002c05f  mov     [rcx], rdi
0x18002c062  mov     [rsi+90h], rax
0x18002c069  mov     [rsi+98h], rdi
0x18002c070  mov     [rsi+0A0h], r13b
0x18002c077  mov     eax, 6
0x18002c07c  mov     [r15], ax
0x18002c080  mov     rdx, rsi
0x18002c083  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UWebTokenRequestResult@Core@Web@Authentication@Security@34@@experimental@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UWebTokenRequestResult@Core@Web@Authentication@Security@34@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>::promise_type>)
0x18002c088  test    al, al
0x18002c08a  jz      loc_18002C47E
0x18002c090  jmp     loc_18002CDB1
0x18002c095  lea     rcx, [rsi+20h]
0x18002c099  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18002c09e  nop
0x18002c09f  mov     rax, cs:Feature_UnifiedConsentCDSHangFix__descriptor
0x18002c0a6  mov     [rsp+218h+var_1C8], rax
0x18002c0ab  mov     rax, [rax]
0x18002c0ae  mov     [rsp+218h+lpMem], rax
0x18002c0b3  mov     [rsp+218h+arg_10], rax
0x18002c0bb  mov     r13d, dword ptr [rsp+218h+arg_10]
0x18002c0c3  mov     eax, r13d
0x18002c0c6  and     eax, 0Ch
0x18002c0c9  cmp     eax, 0Ch
0x18002c0cc  jz      loc_18002C27A
0x18002c0d2  lea     r15, [rsi+170h]
0x18002c0d9  mov     [r15], edi
0x18002c0dc  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002c0e1  mov     dword ptr [rsp+218h+arg_8], eax
0x18002c0e8  lea     rbx, [rsi+174h]
0x18002c0ef  mov     [rbx], edi
0x18002c0f1  lea     rax, [rsi+178h]
0x18002c0f8  mov     [rax], edi
0x18002c0fa  mov     r10, cs:g_wil_details_internalGetFeatureVariant
0x18002c101  test    r10, r10
0x18002c104  jz      short loc_18002C125
0x18002c106  mov     [rsp+218h+var_1F8], r15
0x18002c10b  mov     r9, rbx
0x18002c10e  mov     r8, rax
0x18002c111  xor     edx, edx
0x18002c113  mov     ecx, 2EC1BE7h
0x18002c118  mov     rax, r10
0x18002c11b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c120  mov     r15d, eax
0x18002c123  jmp     short loc_18002C134
0x18002c125  mov     r10, cs:g_wil_details_apiGetFeatureVariant
0x18002c12c  test    r10, r10
0x18002c12f  jnz     short loc_18002C106
0x18002c131  mov     r15d, edi
0x18002c134  mov     eax, [rbx]
0x18002c136  mov     [rsp+218h+var_1B8], eax
0x18002c13a  neg     eax
0x18002c13c  sbb     ebx, ebx
0x18002c13e  and     ebx, 400h
0x18002c144  mov     r12d, r15d
0x18002c147  and     r12d, 80h
0x18002c14e  shl     r12d, 4
0x18002c152  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnifiedConsentCoordinator@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCoordinator@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCoordinator> `wil::Feature<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::GetImpl(void)'::`2'::impl
0x18002c159  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnifiedConsentCoordinator@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnifiedConsentCoordinator>::__private_IsEnabled(wil::ReportingKind)
0x18002c15e  or      ebx, r12d
0x18002c161  test    al, al
0x18002c163  jz      short loc_18002C194
0x18002c165  mov     eax, r15d
0x18002c168  and     eax, 0FFFFFE7Fh
0x18002c16d  jnz     short loc_18002C175
0x18002c16f  bts     ebx, 0Ch
0x18002c173  jmp     short loc_18002C194
0x18002c175  shl     eax, 0Ch
0x18002c178  xor     eax, ebx
0x18002c17a  and     eax, 3F000h
0x18002c17f  xor     ebx, eax
0x18002c181  bt      r15d, 8
0x18002c186  jnb     short loc_18002C194
0x18002c188  mov     edx, [rsi+178h]
0x18002c18e  mov     [rsp+218h+var_1B4], edx
0x18002c192  jmp     short loc_18002C199
0x18002c194  mov     edx, 2AF8h
0x18002c199  cmp     dword ptr [rsp+218h+arg_8], edi
0x18002c1a0  jnz     short loc_18002C1A8
0x18002c1a2  mov     [rsi+170h], edi
0x18002c1a8  mov     r15d, dword ptr [rsp+218h+arg_10+4]
0x18002c1b0  mov     r12d, 4
0x18002c1b6  lea     r9d, [r12+4]
0x18002c1bb  mov     r10, [rsp+218h+var_1C8]
0x18002c1c0  mov     r11d, r13d
0x18002c1c3  mov     r8d, r13d
0x18002c1c6  mov     dword ptr [rsp+218h+arg_10], r13d
0x18002c1ce  mov     dword ptr [rsp+218h+arg_10+4], r15d
0x18002c1d6  test    r9d, r13d
0x18002c1d9  jnz     short loc_18002C21C
0x18002c1db  mov     r15d, edx
0x18002c1de  mov     dword ptr [rsp+218h+arg_10+4], edx
0x18002c1e5  mov     ecx, [rsi+170h]
0x18002c1eb  mov     [rsp+218h+var_1B0], ecx
0x18002c1ef  and     r8d, 0FFFC07F7h
0x18002c1f6  mov     eax, ebx
0x18002c1f8  and     eax, 3F000h
0x18002c1fd  xor     r8d, eax
0x18002c200  neg     ecx
0x18002c202  sbb     eax, eax
0x18002c204  and     eax, r9d
0x18002c207  or      r8d, eax
0x18002c20a  mov     eax, ebx
0x18002c20c  and     eax, 800h
0x18002c211  or      r8d, eax
0x18002c214  mov     dword ptr [rsp+218h+arg_10], r8d
0x18002c21c  test    r12d, r13d
0x18002c21f  jnz     short loc_18002C239
0x18002c221  mov     ecx, ebx
0x18002c223  xor     ecx, r8d
0x18002c226  and     ecx, 400h
0x18002c22c  xor     ecx, r8d
0x18002c22f  or      ecx, r12d
0x18002c232  mov     dword ptr [rsp+218h+arg_10], ecx
0x18002c239  mov     rcx, [rsp+218h+arg_10]
0x18002c241  mov     rax, [rsp+218h+lpMem]
0x18002c246  lock cmpxchg [r10], rcx
0x18002c24b  mov     r13, rax
0x18002c24e  jz      short loc_18002C261
0x18002c250  mov     r15, rax
0x18002c253  shr     r15, 20h
0x18002c257  mov     [rsp+218h+lpMem], rax
0x18002c25c  jmp     loc_18002C1C0
0x18002c261  test    r12d, r11d
0x18002c264  jnz     short loc_18002C288
0x18002c266  mov     r8d, dword ptr [rsp+218h+arg_8]
0x18002c26e  xor     edx, edx
0x18002c270  mov     rcx, r10
0x18002c273  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18002c278  jmp     short loc_18002C288
0x18002c27a  mov     r12d, 4
0x18002c280  mov     r15d, dword ptr [rsp+218h+arg_10+4]
0x18002c288  mov     r13d, 8
0x18002c28e  mov     rbx, [rsi+58h]
0x18002c292  mov     [rsp+218h+var_B0], rbx
0x18002c29a  mov     [rsi+60h], rbx
0x18002c29e  test    rbx, rbx
0x18002c2a1  jz      short loc_18002C2AA
0x18002c2a3  lock inc dword ptr [rbx+118h]
0x18002c2aa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002c2b1  call    cs:__imp_EnterCriticalSection
0x18002c2b7  inc     dword ptr [rbx+0F0h]
0x18002c2bd  mov     [rsp+218h+var_198], rbx
0x18002c2c5  mov     [rbx+114h], r15d
0x18002c2cc  lea     rcx, [rsi+60h]
0x18002c2d0  call    ??1?$test_data_control@V?$merged_data@U_tip_CloudStoreHangMitigationTest@ConsentCoordinationTip@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>::~test_data_control<tip2::details::merged_data<ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest,ConsentCoordinationTip::_tip_CloudStoreHangMitigationTest>>(void)
0x18002c2d5  mov     edx, r15d
0x18002c2d8  lea     rcx, aTimeoutinmsU; "timeoutInMs: %u"
0x18002c2df  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x18002c2e4  lea     rbx, [rsi+68h]
0x18002c2e8  mov     rdx, rbx
0x18002c2eb  mov     rcx, [rsi+1F8h]
0x18002c2f2  call    ?TryLoadCloudStoreAsync@UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@AEAA?AUIAsyncAction@Foundation@67@XZ; winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::TryLoadCloudStoreAsync(void)
0x18002c2f7  mov     rax, [rax]
0x18002c2fa  mov     [rsp+218h+arg_10], rax
0x18002c302  mov     rax, [rbx]
0x18002c305  mov     [rsp+218h+var_190], rax
0x18002c30d  test    rax, rax
0x18002c310  jz      short loc_18002C31A
0x18002c312  mov     rcx, rbx
0x18002c315  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002c31a  lea     rbx, [rsi+70h]
0x18002c31e  mov     [rbx], dil
0x18002c321  mov     r9, rbx
0x18002c324  mov     r8d, r15d
0x18002c327  mov     rcx, [rsp+218h+arg_10]
0x18002c32f  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x18002c334  mov     r15b, [rbx]
0x18002c337  mov     byte ptr [rsp+218h+arg_8], r15b
0x18002c33f  mov     rbx, [rsi+58h]
0x18002c343  mov     [rsp+218h+var_B0], rbx
0x18002c34b  mov     [rsi+78h], rbx
0x18002c34f  test    rbx, rbx
0x18002c352  jz      short loc_18002C35B
0x18002c354  lock inc dword ptr [rbx+118h]
0x18002c35b  lea     rcx, [rbx+0C8h]; lpCriticalSection
  ... truncated ...
```
