# Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync$_ResumeCoro$1

- ea: `0x180049ec0`
- end: `0x18004b228`
- name: `Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync$_ResumeCoro$1`
- size: `4968`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b230`

## callees

- `0x180002810`
- `0x180002834`
- `0x180003390`
- `0x1800034f7`
- `0x1800035ab`
- `0x180005004`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fb28`
- `0x1800131f8`
- `0x180013af4`
- `0x180013f6c`
- `0x180016d38`
- `0x180018198`
- `0x18001c1d4`
- `0x18002346c`
- `0x1800236ac`
- `0x1800237d0`
- `0x18002d324`
- `0x18002d994`
- `0x180038b50`
- `0x180040150`
- `0x180040520`
- `0x1800412f0`
- `0x1800428c4`
- `0x180047128`
- `0x180047a84`
- `0x1800486cc`
- `0x180048b40`
- `0x180048d7c`
- `0x180048f18`
- `0x1800490e4`
- `0x1800492cc`
- `0x180049978`
- `0x180049a1c`
- `0x180049d4c`
- `0x180049ec0`
- `0x18004bcd4`
- `0x18004c5f8`
- `0x18006d710`
- `0x18007d010`

## import_xrefs

- `msvcp_win!_Thrd_yield` at `0x18004a40b`
- `msvcp_win!_Thrd_yield` at `0x18004a5fe`
- `msvcp_win!_Thrd_yield` at `0x18004a40b`
- `msvcp_win!_Thrd_yield` at `0x18004a5fe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a272`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a2b6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a4a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004ab27`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004ab81`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004af8a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b079`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b0d8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b147`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a272`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a2b6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a4a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004ab27`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004ab81`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004af8a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b079`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b0d8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b147`

## string_xrefs

- `0x18004a0f0`: `Base URL not found in service configuration for service: '%ls', environment: '%ls'`
- `0x18004adb2`: `application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=32 #try_helpers=1
void __fastcall Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync__ResumeCoro_1(
        __int64 a1)
{
  _QWORD *v2; // rbx
  __int64 v3; // rdx
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  unsigned int v6; // edx
  struct winrt::impl::shared_hstring_header **v7; // rcx
  struct winrt::impl::shared_hstring_header ***v8; // r13
  struct winrt::impl::shared_hstring_header *v9; // rbx
  unsigned int v10; // r14d
  const void *v11; // r15
  struct winrt::impl::shared_hstring_header *v12; // rbx
  unsigned int v13; // r14d
  const void *v14; // r12
  __int64 v15; // rcx
  __int64 v16; // rcx
  const char *v17; // r9
  const char *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // rbx
  __int64 v22; // rax
  volatile signed __int32 **v23; // r15
  _QWORD *v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  volatile signed __int32 *v27; // rbx
  int v28; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v30; // rbx
  int v31; // eax
  HANDLE v32; // rax
  __int64 v33; // r12
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  const struct winrt::impl::slim_source_location *v37; // rax
  volatile __int64 *v38; // rbx
  volatile signed __int32 *v39; // rbx
  int v40; // eax
  HANDLE v41; // rax
  volatile signed __int32 *v42; // rbx
  __int64 v43; // rcx
  const struct winrt::impl::slim_source_location *v44; // rax
  volatile __int64 *v45; // rbx
  __int64 *v46; // rcx
  __int64 v47; // rax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rcx
  int v51; // eax
  __int64 *v52; // rax
  _QWORD *v53; // r13
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // r12
  int v57; // eax
  _QWORD *v58; // rdx
  __int64 v59; // rcx
  int v60; // eax
  __int64 *v61; // r15
  __int64 *v62; // r13
  int v63; // ebx
  __int64 v64; // rcx
  int v65; // eax
  unsigned int v66; // ebx
  int v67; // ebx
  __int64 v68; // rcx
  int v69; // eax
  volatile signed __int32 **v70; // r12
  int v71; // ebx
  __int64 v72; // rcx
  int v73; // eax
  volatile signed __int32 *v74; // rdx
  __int64 v75; // rcx
  int v76; // eax
  unsigned int v77; // ebx
  volatile signed __int32 *v78; // r12
  int v79; // eax
  HANDLE v80; // rax
  volatile signed __int32 *v81; // rbx
  int v82; // eax
  HANDLE v83; // rax
  __int64 v84; // rcx
  int v85; // eax
  __int64 *v86; // rcx
  __int64 v87; // rax
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // r13
  __int64 v91; // rbx
  int v92; // eax
  __int64 *v93; // rcx
  __int64 v94; // rax
  int v95; // eax
  __int64 v96; // rcx
  int v97; // eax
  __int64 v98; // rax
  volatile signed __int32 **v99; // r13
  __int64 *v100; // r15
  __int64 *v101; // rax
  __int64 v102; // rcx
  int v103; // eax
  _QWORD *v104; // rbx
  __int64 v105; // rax
  volatile signed __int32 *v106; // rbx
  int v107; // eax
  HANDLE v108; // rax
  volatile signed __int32 *v109; // rbx
  int v110; // eax
  HANDLE v111; // rax
  volatile signed __int32 *v112; // rbx
  int v113; // r14d
  HANDLE v114; // rax
  __int64 *v115; // [rsp+50h] [rbp-368h]
  __int64 (__fastcall *v116)(__int64, __int64, __int64, __int64); // [rsp+50h] [rbp-368h]
  __int64 v117; // [rsp+60h] [rbp-358h]
  __int64 *v118; // [rsp+68h] [rbp-350h]
  __int64 v119; // [rsp+70h] [rbp-348h]
  _BYTE pExceptionObject[24]; // [rsp+160h] [rbp-258h] BYREF
  _BYTE v121[24]; // [rsp+178h] [rbp-240h] BYREF
  __int64 v122; // [rsp+190h] [rbp-228h]
  __int64 v123; // [rsp+1B0h] [rbp-208h]
  __int64 v124; // [rsp+1D0h] [rbp-1E8h]
  __int64 v125; // [rsp+1F0h] [rbp-1C8h]
  __int64 v126; // [rsp+210h] [rbp-1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 8u )
  {
LABEL_193:
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
        goto LABEL_193;
      case 2:
        *(_DWORD *)(a1 + 936) = 0;
        v2 = *(_QWORD **)(a1 + 1544);
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        v3 = v2[2];
        if ( !v3 )
          goto LABEL_50;
        v4 = *(_DWORD *)(v3 + 8);
        do
        {
          if ( !v4 )
LABEL_50:
            std::_Throw_bad_weak_ptr();
          v5 = v4;
          v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v4 + 1, v4);
        }
        while ( v5 != v4 );
        *(_QWORD *)(a1 + 16) = v2[1];
        *(_QWORD *)(a1 + 24) = v2[2];
        *(_BYTE *)(a1 - 64) = 1;
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
          a1 + 32,
          "RequestResponseHandler_BuildRequestMessageAsync");
        *(_QWORD *)(a1 + 32) = &Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::`vftable';
        Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::StartActivity((Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync *)(a1 + 32));
        v115 = (__int64 *)v2[5];
        v117 = *v115;
        v7 = (struct winrt::impl::shared_hstring_header **)(a1 + 368);
        *(_QWORD *)(a1 + 376) = a1 + 368;
        v8 = (struct winrt::impl::shared_hstring_header ***)(a1 + 1584);
        v9 = *(struct winrt::impl::shared_hstring_header **)(*(_QWORD *)(a1 + 1584) + 8LL);
        if ( !v9 )
          goto LABEL_9;
        if ( (*(_DWORD *)v9 & 1) != 0 )
        {
          v10 = *((_DWORD *)v9 + 1);
          if ( v10 )
          {
            v11 = (const void *)*((_QWORD *)v9 + 2);
            v9 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v10, v6);
            memcpy_s((char *)v9 + 28, 2LL * v10, v11, 2LL * v10);
            v7 = (struct winrt::impl::shared_hstring_header **)(a1 + 368);
          }
          else
          {
LABEL_9:
            v9 = 0;
          }
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)v9 + 6);
        }
        *v7 = v9;
        v12 = **v8;
        if ( !v12 )
          goto LABEL_15;
        if ( (*(_DWORD *)v12 & 1) != 0 )
        {
          v13 = *((_DWORD *)v12 + 1);
          if ( v13 )
          {
            v14 = (const void *)*((_QWORD *)v12 + 2);
            v12 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v13, v6);
            memcpy_s((char *)v12 + 28, 2LL * v13, v14, 2LL * v13);
            v7 = (struct winrt::impl::shared_hstring_header **)(a1 + 368);
          }
          else
          {
LABEL_15:
            v12 = 0;
          }
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)v12 + 6);
        }
        *(_QWORD *)(a1 + 384) = v12;
        (*(void (__fastcall **)(__int64 *, __int64, __int64, struct winrt::impl::shared_hstring_header **))(v117 + 24))(
          v115,
          a1 + 392,
          a1 + 384,
          v7);
        if ( !*(_BYTE *)(a1 + 400) )
        {
          tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::operator->(a1 + 1584);
          tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::operator->(v16);
          v17 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x85,
            (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\requestresponsehandler.cpp",
            v17,
            (int)"Base URL not found in service configuration for service: '%ls', environment: '%ls'",
            v18,
            v19);
        }
        *(_QWORD *)(a1 + 944) = &qword_18009CE08;
        _InterlockedIncrement64(&qword_18009CE08);
        if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory> )
        {
          _lambda_3657daff472b317e63d0148d109dd539_::operator()(
            v15,
            a1 + 408,
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory>);
          _InterlockedAdd64(&qword_18009CE08, 0xFFFFFFFFFFFFFFFFuLL);
        }
        else
        {
          _InterlockedAdd64(&qword_18009CE08, 0xFFFFFFFFFFFFFFFFuLL);
          *(_QWORD *)(a1 + 952) = _lambda_3657daff472b317e63d0148d109dd539_::_lambda_invoker_cdecl_;
          winrt::impl::factory_cache_entry<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Web::Http::HttpRequestMessage (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
            v15,
            a1 + 408);
        }
        if ( !*(_BYTE *)(a1 + 400) )
          std::_Throw_bad_optional_access();
        v20 = *(_QWORD *)(a1 + 1568);
        v21 = v20 + 32;
        v22 = winrt::operator+(a1 + 456, a1 + 392, v20 + 24);
        v23 = (volatile signed __int32 **)(a1 + 464);
        *(_QWORD *)(a1 + 424) = *(_QWORD *)winrt::operator+(a1 + 464, v22, v21);
        v24 = (_QWORD *)winrt::Windows::Foundation::Uri::Uri(
                          (winrt::Windows::Foundation::Uri *)(a1 + 416),
                          (const struct winrt::param::hstring *)(a1 + 424));
        v25 = *(_QWORD *)(a1 + 408);
        *(_DWORD *)(a1 + 960) = 0;
        *(_QWORD *)(a1 + 968) = 0;
        *(_QWORD *)(a1 + 976) = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 104LL))(v25, *v24);
        if ( v26 < 0 )
          winrt::throw_hresult((unsigned int)v26, a1 + 960);
        if ( *(_QWORD *)(a1 + 416) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 416);
        v27 = *v23;
        if ( *v23 )
        {
          v28 = _InterlockedDecrement(v27 + 6);
          if ( v28 )
          {
            if ( v28 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v27);
          }
          *v23 = 0;
        }
        v30 = *(volatile signed __int32 **)(a1 + 456);
        if ( v30 )
        {
          v31 = _InterlockedDecrement(v30 + 6);
          if ( v31 )
          {
            if ( v31 < 0 )
              abort();
          }
          else
          {
            v32 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v32, 0, (LPVOID)v30);
          }
        }
        v33 = *(_QWORD *)(*(_QWORD *)(a1 + 1544) + 56LL);
        v116 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v33 + 8LL);
        *(_QWORD *)(a1 + 472) = 0;
        *(_QWORD *)(a1 + 480) = 0;
        v34 = *(_QWORD *)(a1 + 1592);
        if ( v34 )
          _InterlockedIncrement((volatile signed __int32 *)(v34 + 8));
        *(_QWORD *)(a1 + 472) = *v8;
        *(_QWORD *)(a1 + 480) = *(_QWORD *)(a1 + 1592);
        v35 = *(_QWORD *)(a1 + 1600);
        *(_QWORD *)(a1 + 488) = v35;
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
        v36 = v116(v33, a1 + 496, a1 + 488, a1 + 472);
        *(_QWORD *)(a1 + 504) = a1 + 32;
        *(_QWORD *)(a1 + 512) = 0;
        *(_QWORD *)(a1 + 520) = v36;
        *(_QWORD *)(a1 + 528) = 0;
        *(_BYTE *)(a1 + 536) = 1;
        *(_BYTE *)(a1 + 544) = 0;
        *(_DWORD *)(a1 + 545) = 0;
        *(_WORD *)(a1 + 549) = 0;
        *(_BYTE *)(a1 + 551) = 0;
        if ( *(_DWORD *)(a1 - 16) == 2 )
        {
          v37 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 984);
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v37);
          throw (winrt::hresult_canceled *)pExceptionObject;
        }
        *(_QWORD *)(a1 + 552) = a1;
        *(_WORD *)(a1 + 8) = 6;
        if ( !(unsigned __int8)wil::details::coro::coroutine_withsuspend_awaiter<Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,1>>::await_suspend<std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type>>() )
        {
LABEL_70:
          if ( *(_BYTE *)(a1 + 544) )
            wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::resume(*(_QWORD *)(a1 + 504));
          *(_DWORD *)(a1 + 1008) = 0;
          *(_QWORD *)(a1 + 1016) = 0;
          *(_QWORD *)(a1 + 1024) = 0;
          v43 = *(unsigned int *)(a1 + 532);
          if ( (int)v43 < 0 )
            winrt::throw_hresult(v43, a1 + 1008);
          if ( *(_DWORD *)(a1 + 528) == 2 )
          {
            v44 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 1032);
            winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v121, v44);
            throw (winrt::hresult_canceled *)v121;
          }
          winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,winrt::hstring>::GetResults(
            *(_QWORD *)(a1 + 520),
            a1 + 560);
          v45 = *(volatile __int64 **)(a1 + 512);
          if ( v45 )
          {
            while ( _InterlockedExchange64(v45, 0) == 1 )
              _Thrd_yield();
          }
          if ( *(_QWORD *)(a1 + 496) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 496);
          *(_QWORD *)(a1 + 576) = *(_QWORD *)(a1 + 560);
          *(_QWORD *)(a1 + 608) = *(_QWORD *)(*(_QWORD *)(a1 + 1544) + 72LL);
          *(_QWORD *)(a1 + 1056) = a1 + 608;
          *(_QWORD *)(a1 + 1064) = a1 + 576;
          *(_QWORD *)(a1 + 1072) = &qword_18009D038;
          _InterlockedAdd64(&qword_18009D038, 1u);
          v46 = (__int64 *)winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue,winrt::Windows::Web::Http::Headers::IHttpCredentialsHeaderValueFactory>;
          if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue,winrt::Windows::Web::Http::Headers::IHttpCredentialsHeaderValueFactory> )
          {
            *(_QWORD *)(a1 + 1104) = 0;
            *(_DWORD *)(a1 + 1112) = 0;
            *(_QWORD *)(a1 + 1120) = 0;
            *(_QWORD *)(a1 + 1128) = 0;
            v47 = *v46;
            v122 = *(_QWORD *)(a1 + 576);
            v123 = *(_QWORD *)(a1 + 608);
            v48 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v47 + 56))(
                    v46,
                    v123,
                    v122,
                    a1 + 1104);
            if ( v48 < 0 )
              winrt::throw_hresult((unsigned int)v48, a1 + 1112);
            *(_QWORD *)(a1 + 568) = *(_QWORD *)(a1 + 1104);
            _InterlockedAdd64(&qword_18009D038, 0xFFFFFFFFFFFFFFFFuLL);
            v49 = 127;
          }
          else
          {
            _InterlockedAdd64(&qword_18009D038, 0xFFFFFFFFFFFFFFFFuLL);
            winrt::impl::factory_cache_entry<winrt::Windows::Web::Http::Headers::HttpCredentialsHeaderValue,winrt::Windows::Web::Http::Headers::IHttpCredentialsHeaderValueFactory>::call<_lambda_95230da2a24f541a16015f63e1e15fc4_ &>(
              0,
              a1 + 568,
              a1 + 1056);
            v49 = 31;
          }
          *(_DWORD *)(a1 + 936) = v49;
          v50 = *(_QWORD *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
                             a1 + 408,
                             a1 + 640);
          *(_DWORD *)(a1 + 1080) = 0;
          *(_QWORD *)(a1 + 1088) = 0;
          *(_QWORD *)(a1 + 1096) = 0;
          v51 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 80LL))(v50);
          if ( v51 < 0 )
            winrt::throw_hresult((unsigned int)v51, a1 + 1080);
          if ( *(_QWORD *)(a1 + 640) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 640);
          v52 = (__int64 *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
                             a1 + 408,
                             a1 + 648);
          v53 = (_QWORD *)(a1 + 1136);
          *(_QWORD *)(a1 + 1136) = 0;
          v54 = *v52;
          *(_DWORD *)(a1 + 1144) = 0;
          *(_QWORD *)(a1 + 1152) = 0;
          *(_QWORD *)(a1 + 1160) = 0;
          v55 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 88LL))(v54, a1 + 1136);
          if ( v55 < 0 )
            winrt::throw_hresult((unsigned int)v55, a1 + 1144);
          *(_QWORD *)(a1 + 656) = *v53;
          *(_DWORD *)(a1 + 936) |= 0x80u;
          *(_DWORD *)(a1 + 672) = 1;
          *(_DWORD *)(a1 + 676) = 8;
          *(_QWORD *)(a1 + 688) = L"no_store";
          *(_QWORD *)(a1 + 664) = a1 + 672;
          v56 = *v53;
          *(_BYTE *)(a1 + 1168) = 0;
          *(_DWORD *)(a1 + 1176) = 0;
          *(_QWORD *)(a1 + 1184) = 0;
          *(_QWORD *)(a1 + 1192) = 0;
          v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 120LL))(v56);
          if ( v57 < 0 )
            winrt::throw_hresult((unsigned int)v57, a1 + 1176);
          if ( v56 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 656);
          if ( *(_QWORD *)(a1 + 648) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 648);
          v58 = *(_QWORD **)(a1 + 1568);
          v59 = *(_QWORD *)(a1 + 408);
          *(_DWORD *)(a1 + 1200) = 0;
          *(_QWORD *)(a1 + 1208) = 0;
          *(_QWORD *)(a1 + 1216) = 0;
          v60 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v59 + 80LL))(v59, *v58);
          if ( v60 < 0 )
            winrt::throw_hresult((unsigned int)v60, a1 + 1200);
          winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::hstring>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>::begin(
            *(_QWORD *)(a1 + 1568) + 8LL,
            a1 + 696);
          *(_QWORD *)(a1 + 704) = 0;
          while ( 1 )
          {
            v61 = (__int64 *)(a1 + 696);
            if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a1 + 696, a1 + 704) )
              break;
            v62 = (__int64 *)(a1 + 712);
            *(_QWORD *)(a1 + 712) = 0;
            v63 = *(_DWORD *)(a1 + 936) | 0x200;
            *(_DWORD *)(a1 + 936) = v63;
            v64 = *v61;
            *(_DWORD *)(a1 + 1256) = 0;
            *(_QWORD *)(a1 + 1264) = 0;
            *(_QWORD *)(a1 + 1272) = 0;
            v65 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 48LL))(v64, a1 + 712);
            if ( v65 < 0 )
              winrt::throw_hresult((unsigned int)v65, a1 + 1256);
            v66 = v63 & 0xFFFFFCFF | 0x100;
            *(_DWORD *)(a1 + 936) = v66;
            v118 = (__int64 *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
                                a1 + 408,
                                a1 + 720);
            *(_QWORD *)(a1 + 728) = 0;
            v67 = v66 | 0x400;
            *(_DWORD *)(a1 + 936) = v67;
            v68 = *v62;
            *(_DWORD *)(a1 + 1280) = 0;
            *(_QWORD *)(a1 + 1288) = 0;
            *(_QWORD *)(a1 + 1296) = 0;
            v69 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 56LL))(v68, a1 + 728);
            if ( v69 < 0 )
              winrt::throw_hresult((unsigned int)v69, a1 + 1280);
            v119 = *(_QWORD *)(a1 + 728);
            v70 = (volatile signed __int32 **)(a1 + 736);
            *(_QWORD *)(a1 + 736) = 0;
            v71 = v67 | 0x800;
            *(_DWORD *)(a1 + 936) = v71;
            v72 = *v62;
            *(_DWORD *)(a1 + 1304) = 0;
            *(_QWORD *)(a1 + 1312) = 0;
            *(_QWORD *)(a1 + 1320) = 0;
            v73 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 48LL))(v72, a1 + 736);
            if ( v73 < 0 )
              winrt::throw_hresult((unsigned int)v73, a1 + 1304);
            v74 = *v70;
            v75 = *v118;
            *(_DWORD *)(a1 + 1328) = 0;
            *(_QWORD *)(a1 + 1336) = 0;
            *(_QWORD *)(a1 + 1344) = 0;
            v76 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, __int64))(*(_QWORD *)v75 + 264LL))(
                    v75,
                    v74,
                    v119);
            if ( v76 < 0 )
              winrt::throw_hresult((unsigned int)v76, a1 + 1328);
            v77 = v71 & 0xFFFFF7FF;
            *(_DWORD *)(a1 + 936) = v77;
            v78 = *v70;
            if ( v78 )
            {
              v79 = _InterlockedDecrement(v78 + 6);
              if ( v79 )
              {
                if ( v79 < 0 )
                  abort();
              }
              else
              {
                v80 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v80, 0, (LPVOID)v78);
              }
              *(_QWORD *)(a1 + 736) = 0;
            }
            *(_DWORD *)(a1 + 936) = v77 & 0xFFFFFBFF;
            v81 = *(volatile signed __int32 **)(a1 + 728);
            if ( v81 )
            {
              v82 = _InterlockedDecrement(v81 + 6);
              if ( v82 )
              {
                if ( v82 < 0 )
                  abort();
              }
              else
              {
                v83 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v83, 0, (LPVOID)v81);
              }
              *(_QWORD *)(a1 + 728) = 0;
            }
            if ( *(_QWORD *)(a1 + 720) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 720);
            if ( *v62 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 712);
            *(_BYTE *)(a1 + 1248) = 0;
            v84 = *v61;
            *(_DWORD *)(a1 + 1224) = 0;
            *(_QWORD *)(a1 + 1232) = 0;
            *(_QWORD *)(a1 + 1240) = 0;
            v85 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 64LL))(v84, a1 + 1248);
            if ( v85 < 0 )
              winrt::throw_hresult((unsigned int)v85, a1 + 1224);
            if ( !*(_BYTE *)(a1 + 1248) )
            {
              if ( *v61 )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 696);
              *v61 = 0;
            }
          }
          if ( *(_QWORD *)(a1 + 704) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 704);
          if ( *v61 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 696);
          if ( *(_QWORD *)(*(_QWORD *)(a1 + 1568) + 16LL) )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudDirectNotification>::GetImpl'::`2'::impl) )
            {
              *(_DWORD *)(a1 + 760) = 1;
              *(_DWORD *)(a1 + 764) = 16;
              *(_QWORD *)(a1 + 776) = L"application/json";
              *(_QWORD *)(a1 + 752) = a1 + 760;
              *(_DWORD *)(a1 + 784) = 0;
              *(_QWORD *)(a1 + 792) = *(_QWORD *)(*(_QWORD *)(a1 + 1568) + 16LL);
              *(_QWORD *)(a1 + 1352) = a1 + 792;
              *(_QWORD *)(a1 + 1360) = a1 + 784;
              *(_QWORD *)(a1 + 1368) = a1 + 752;
              *(_QWORD *)(a1 + 1376) = &qword_18009CDC8;
              _InterlockedIncrement64(&qword_18009CDC8);
              v93 = (__int64 *)winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpStringContent,winrt::Windows::Web::Http::IHttpStringContentFactory>;
              if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpStringContent,winrt::Windows::Web::Http::IHttpStringContentFactory> )
              {
                *(_QWORD *)(a1 + 1408) = 0;
                *(_DWORD *)(a1 + 1416) = 0;
                *(_QWORD *)(a1 + 1424) = 0;
                *(_QWORD *)(a1 + 1432) = 0;
                v94 = *v93;
                v125 = *(_QWORD *)(a1 + 752);
                v126 = *(_QWORD *)(a1 + 792);
                v95 = (*(__int64 (__fastcall **)(__int64 *))(v94 + 64))(v93);
                if ( v95 < 0 )
                  winrt::throw_hresult((unsigned int)v95, a1 + 1416);
                *(_QWORD *)(a1 + 744) = *(_QWORD *)(a1 + 1408);
                _InterlockedAdd64(&qword_18009CDC8, 0xFFFFFFFFFFFFFFFFuLL);
              }
              else
              {
                _InterlockedAdd64(&qword_18009CDC8, 0xFFFFFFFFFFFFFFFFuLL);
                winrt::impl::factory_cache_entry<winrt::Windows::Web::Http::HttpStringContent,winrt::Windows::Web::Http::IHttpStringContentFactory>::call<_lambda_83e446bf24d90680735344101bad2757_ &>(
                  0,
                  a1 + 744);
              }
              v96 = *(_QWORD *)(a1 + 408);
              *(_DWORD *)(a1 + 1384) = 0;
              *(_QWORD *)(a1 + 1392) = 0;
              *(_QWORD *)(a1 + 1400) = 0;
              v90 = a1 + 744;
              v91 = *(_QWORD *)(a1 + 744);
              v97 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v96 + 56LL))(v96, v91);
              if ( v97 < 0 )
                winrt::throw_hresult((unsigned int)v97, a1 + 1384);
            }
            else
            {
              *(_QWORD *)(a1 + 832) = *(_QWORD *)(*(_QWORD *)(a1 + 1568) + 16LL);
              *(_QWORD *)(a1 + 1440) = a1 + 832;
              *(_QWORD *)(a1 + 1448) = &qword_18009CDC8;
              _InterlockedIncrement64(&qword_18009CDC8);
              v86 = (__int64 *)winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpStringContent,winrt::Windows::Web::Http::IHttpStringContentFactory>;
              if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpStringContent,winrt::Windows::Web::Http::IHttpStringContentFactory> )
              {
                *(_QWORD *)(a1 + 1480) = 0;
                *(_DWORD *)(a1 + 1488) = 0;
                *(_QWORD *)(a1 + 1496) = 0;
                *(_QWORD *)(a1 + 1504) = 0;
                v87 = *v86;
                v124 = *(_QWORD *)(a1 + 832);
                v88 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(v87 + 48))(v86, v124, a1 + 1480);
                if ( v88 < 0 )
                  winrt::throw_hresult((unsigned int)v88, a1 + 1488);
                *(_QWORD *)(a1 + 824) = *(_QWORD *)(a1 + 1480);
                _InterlockedAdd64(&qword_18009CDC8, 0xFFFFFFFFFFFFFFFFuLL);
              }
              else
              {
                _InterlockedAdd64(&qword_18009CDC8, 0xFFFFFFFFFFFFFFFFuLL);
                winrt::impl::factory_cache_entry<winrt::Windows::Web::Http::HttpStringContent,winrt::Windows::Web::Http::IHttpStringContentFactory>::call<_lambda_8007628372758ef72c656ab67b312149_ &>(
                  0,
                  a1 + 824);
              }
              v89 = *(_QWORD *)(a1 + 408);
              *(_DWORD *)(a1 + 1456) = 0;
              *(_QWORD *)(a1 + 1464) = 0;
              *(_QWORD *)(a1 + 1472) = 0;
              v90 = a1 + 824;
              v91 = *(_QWORD *)(a1 + 824);
              v92 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v89 + 56LL))(v89, v91);
              if ( v92 < 0 )
                winrt::throw_hresult((unsigned int)v92, a1 + 1456);
            }
            if ( v91 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v90);
          }
          *(_QWORD *)(a1 + 864) = 0;
          *(_QWORD *)(a1 + 872) = 0;
          v98 = *(_QWORD *)(a1 + 1560);
          if ( v98 )
            _InterlockedIncrement((volatile signed __int32 *)(v98 + 8));
          *(_QWORD *)(a1 + 864) = *(_QWORD *)(a1 + 1552);
          *(_QWORD *)(a1 + 872) = *(_QWORD *)(a1 + 1560);
          v99 = (volatile signed __int32 **)(a1 + 880);
          Windows::Internal::CloudRequestor::CorrelationVectorUtils::Increment(a1 + 880);
          v100 = (__int64 *)(a1 + 408);
          v101 = (__int64 *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
                              a1 + 408,
                              a1 + 888);
          if ( aMsCv[5] )
            abort();
          *(_DWORD *)(a1 + 904) = 1;
          *(_DWORD *)(a1 + 908) = 5;
          *(_QWORD *)(a1 + 920) = L"MS-CV";
          *(_QWORD *)(a1 + 896) = a1 + 904;
          v102 = *v101;
          *(_DWORD *)(a1 + 1512) = 0;
          *(_QWORD *)(a1 + 1520) = 0;
          *(_QWORD *)(a1 + 1528) = 0;
          v103 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v102 + 264LL))(v102);
          if ( v103 < 0 )
            winrt::throw_hresult((unsigned int)v103, a1 + 1512);
          if ( *(_QWORD *)(a1 + 888) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 888);
          wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
            (_QWORD *)(a1 + 32),
            0);
          v104 = (_QWORD *)(a1 - 8);
          if ( (__int64 *)(a1 - 8) != v100 )
          {
            if ( *v104 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 8);
            v105 = *v100;
            *v100 = 0;
            *v104 = v105;
          }
          v106 = *v99;
          if ( *v99 )
          {
            v107 = _InterlockedDecrement(v106 + 6);
            if ( v107 )
            {
              if ( v107 < 0 )
                abort();
            }
            else
            {
              v108 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v108, 0, (LPVOID)v106);
            }
            *v99 = 0;
          }
          if ( *(_QWORD *)(a1 + 568) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 568);
          v109 = *(volatile signed __int32 **)(a1 + 560);
          if ( v109 )
          {
            v110 = _InterlockedDecrement(v109 + 6);
            if ( v110 )
            {
              if ( v110 < 0 )
                abort();
            }
            else
            {
              v111 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v111, 0, (LPVOID)v109);
            }
            *(_QWORD *)(a1 + 560) = 0;
          }
          if ( *v100 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 408);
          if ( *(_BYTE *)(a1 + 400) )
          {
            v112 = *(volatile signed __int32 **)(a1 + 392);
            if ( v112 )
            {
              v113 = _InterlockedDecrement(v112 + 6);
              if ( v113 )
              {
                if ( v113 < 0 )
                  abort();
              }
              else
              {
                v114 = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(v114, 0, (LPVOID)v112);
              }
              *(_QWORD *)(a1 + 392) = 0;
            }
          }
          *(_QWORD *)(a1 + 32) = &Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::`vftable';
          wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 32);
          wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 32);
          std::shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>::~shared_ptr<Windows::Internal::CloudNotifications::CommonNotificationsInterface>(a1 + 16);
          *(_QWORD *)(a1 + 928) = a1 - 112;
          *(_WORD *)(a1 + 8) = 0;
          if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,void>::final_suspend_awaiter::await_suspend() )
          {
LABEL_191:
            std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type::~promise_type(a1 - 112);
            Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync_::_18_::_parameters_::__parameters_(a1 + 1544);
            if ( *(_WORD *)(a1 + 10) )
              operator delete((void *)(a1 - 112), 0x6D0u);
          }
        }
        break;
      case 6:
        goto LABEL_70;
      case 7:
        v38 = *(volatile __int64 **)(a1 + 512);
        if ( v38 )
        {
          while ( _InterlockedExchange64(v38, 0) == 1 )
            _Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 496) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 496);
        if ( *(_QWORD *)(a1 + 408) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 408);
        if ( *(_BYTE *)(a1 + 400) )
        {
          v39 = *(volatile signed __int32 **)(a1 + 392);
          if ( v39 )
          {
            v40 = _InterlockedDecrement(v39 + 6);
            if ( v40 )
            {
              if ( v40 < 0 )
                abort();
            }
            else
            {
              v41 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v41, 0, (LPVOID)v39);
            }
            *(_QWORD *)(a1 + 392) = 0;
          }
        }
        *(_QWORD *)(a1 + 32) = &Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::`vftable';
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 32);
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 32);
        if ( *(_QWORD *)(a1 + 24) )
        {
          v42 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
            if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
          }
        }
        goto LABEL_191;
    }
  }
}

```

## disassembly

```asm
0x180049ec0  mov     r11, rsp
0x180049ec3  mov     [r11+10h], rbx
0x180049ec7  mov     [r11+18h], rsi
0x180049ecb  mov     [r11+8], rcx
0x180049ecf  push    rdi
0x180049ed0  push    r12
0x180049ed2  push    r13
0x180049ed4  push    r14
0x180049ed6  push    r15
0x180049ed8  sub     rsp, 390h
0x180049edf  mov     rax, cs:__security_cookie
0x180049ee6  xor     rax, rsp
0x180049ee9  mov     [rsp+3B8h+var_30], rax
0x180049ef1  mov     rdi, rcx
0x180049ef4  mov     [rsp+3B8h+var_330], rcx
0x180049efc  movzx   eax, word ptr [rdi+8]
0x180049f00  mov     [rsp+3B8h+var_338], ax
0x180049f08  mov     r12d, 1
0x180049f0e  add     ax, r12w
0x180049f12  lea     ecx, [r12+7]
0x180049f17  cmp     ax, cx
0x180049f1a  ja      loc_18004B1D3; jumptable 0000000180049F35 cases 1,5,6
0x180049f20  movsx   rax, ax
0x180049f24  lea     rdx, cs:180000000h
0x180049f2b  mov     ecx, ds:(jpt_180049F35 - 180000000h)[rdx+rax*4]; switch 9 cases
0x180049f32  add     rcx, rdx
0x180049f35  jmp     rcx; switch jump
0x180049f37  xor     esi, esi; jumptable 0000000180049F35 case 4
0x180049f39  jmp     loc_18004B1A8
0x180049f3e  xor     esi, esi; jumptable 0000000180049F35 case 3
0x180049f40  mov     [rdi+3A8h], esi
0x180049f46  mov     rbx, [rdi+608h]
0x180049f4d  mov     [rdi+10h], rsi
0x180049f51  mov     [rdi+18h], rsi
0x180049f55  mov     rdx, [rbx+10h]
0x180049f59  test    rdx, rdx
0x180049f5c  jz      loc_18004A3ED
0x180049f62  mov     eax, [rdx+8]
0x180049f65  jmp     short loc_180049F71
0x180049f67  lea     ecx, [rax+1]
0x180049f6a  lock cmpxchg [rdx+8], ecx
0x180049f6f  jz      short loc_180049F7A
0x180049f71  test    eax, eax
0x180049f73  jnz     short loc_180049F67
0x180049f75  jmp     loc_18004A3ED
0x180049f7a  mov     rax, [rbx+8]
0x180049f7e  mov     [rdi+10h], rax
0x180049f82  mov     rax, [rbx+10h]
0x180049f86  mov     [rdi+18h], rax
0x180049f8a  mov     [rdi-40h], r12b
0x180049f8e  lea     r14, [rdi+20h]
0x180049f92  lea     rdx, aRequestrespons; "RequestResponseHandler_BuildRequestMess"...
0x180049f99  mov     rcx, r14
0x180049f9c  call    ??0?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180049fa1  lea     rax, ??_7RequestResponseHandler_BuildRequestMessageAsync@InternalLogger@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::`vftable'
0x180049fa8  mov     [r14], rax
0x180049fab  mov     rcx, r14; this
0x180049fae  call    ?StartActivity@RequestResponseHandler_BuildRequestMessageAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ; Windows::Internal::CloudRequestor::InternalLogger::RequestResponseHandler_BuildRequestMessageAsync::StartActivity(void)
0x180049fb3  nop
0x180049fb4  mov     rax, [rbx+28h]
0x180049fb8  mov     [rsp+3B8h+var_368], rax
0x180049fbd  mov     rax, [rax]
0x180049fc0  mov     [rsp+3B8h+var_358], rax
0x180049fc5  lea     rcx, [rdi+170h]
0x180049fcc  mov     [rdi+178h], rcx
0x180049fd3  lea     r13, [rdi+630h]
0x180049fda  mov     rax, [r13+0]
0x180049fde  mov     rbx, [rax+8]
0x180049fe2  test    rbx, rbx
0x180049fe5  jnz     short loc_180049FEC
0x180049fe7  mov     rbx, rsi
0x180049fea  jmp     short loc_18004A02B
0x180049fec  test    [rbx], r12d
0x180049fef  jnz     short loc_180049FF7
0x180049ff1  lock inc dword ptr [rbx+18h]
0x180049ff5  jmp     short loc_18004A02B
0x180049ff7  mov     r14d, [rbx+4]
0x180049ffb  test    r14d, r14d
0x180049ffe  jz      short loc_180049FE7
0x18004a000  mov     r15, [rbx+10h]
0x18004a004  mov     ecx, r14d; this
0x18004a007  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004a00c  mov     rbx, rax
0x18004a00f  mov     edx, r14d
0x18004a012  add     rdx, rdx; DestinationSize
0x18004a015  lea     rcx, [rax+1Ch]; Destination
0x18004a019  mov     r9, rdx; SourceSize
0x18004a01c  mov     r8, r15; Source
0x18004a01f  call    memcpy_s
0x18004a024  lea     rcx, [rdi+170h]
0x18004a02b  mov     [rcx], rbx
0x18004a02e  lea     r15, [rdi+180h]
0x18004a035  mov     rax, [r13+0]
0x18004a039  mov     rbx, [rax]
0x18004a03c  test    rbx, rbx
0x18004a03f  jnz     short loc_18004A046
0x18004a041  mov     rbx, rsi
0x18004a044  jmp     short loc_18004A085
0x18004a046  test    [rbx], r12d
0x18004a049  jnz     short loc_18004A051
0x18004a04b  lock inc dword ptr [rbx+18h]
0x18004a04f  jmp     short loc_18004A085
0x18004a051  mov     r14d, [rbx+4]
0x18004a055  test    r14d, r14d
0x18004a058  jz      short loc_18004A041
0x18004a05a  mov     r12, [rbx+10h]
0x18004a05e  mov     ecx, r14d; this
0x18004a061  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004a066  mov     rbx, rax
0x18004a069  mov     edx, r14d
0x18004a06c  add     rdx, rdx; DestinationSize
0x18004a06f  lea     rcx, [rax+1Ch]; Destination
0x18004a073  mov     r9, rdx; SourceSize
0x18004a076  mov     r8, r12; Source
0x18004a079  call    memcpy_s
0x18004a07e  lea     rcx, [rdi+170h]
0x18004a085  mov     [r15], rbx
0x18004a088  lea     r12, [rdi+188h]
0x18004a08f  mov     r9, rcx
0x18004a092  mov     r8, r15
0x18004a095  mov     rdx, r12
0x18004a098  mov     rcx, [rsp+3B8h+var_368]
0x18004a09d  mov     rax, [rsp+3B8h+var_358]
0x18004a0a2  mov     rax, [rax+18h]
0x18004a0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0ab  nop
0x18004a0ac  mov     al, [rdi+190h]
0x18004a0b2  mov     [rsp+3B8h+var_320], al
0x18004a0b9  test    al, al
0x18004a0bb  jnz     short loc_18004A10D
0x18004a0bd  mov     rcx, r13
0x18004a0c0  call    ??C?$test_data_control@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEBAPEAV?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@1@XZ; tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::operator->(void)
0x18004a0c5  mov     r8, [rax+8]
0x18004a0c9  call    ??C?$test_data_control@V?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@tip2@@@tip2@@QEBAPEAV?$merged_data@U_tip_CNCreateWnpChannelTip@CloudNotificationsTip@@U12@@details@1@XZ; tip2::test_data_control<tip2::details::merged_data<CloudNotificationsTip::_tip_CNCreateWnpChannelTip,CloudNotificationsTip::_tip_CNCreateWnpChannelTip>>::operator->(void)
0x18004a0ce  mov     rdx, [rax]
0x18004a0d1  mov     ecx, 80070057h
0x18004a0d6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004a0db  mov     r9d, eax; char *
0x18004a0de  mov     rcx, [rsp+3B8h]; this
0x18004a0e6  mov     [rsp+3B8h+var_388], r8
0x18004a0eb  mov     [rsp+3B8h+var_390], rdx; char *
0x18004a0f0  lea     rax, aBaseUrlNotFoun; "Base URL not found in service configura"...
0x18004a0f7  mov     qword ptr [rsp+3B8h+var_398], rax; int
0x18004a0fc  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x18004a103  mov     edx, 85h; void *
0x18004a108  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a10d  lea     rax, qword_18009CE08
0x18004a114  mov     [rdi+3B0h], rax
0x18004a11b  lock inc cs:qword_18009CE08
0x18004a123  cmp     cs:??$factory_cache_entry_v@UHttpRequestMessage@Http@Web@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UHttpRequestMessage@Http@Web@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rsi; factory_cache_entry<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory>
0x18004a12a  jz      short loc_18004A14E
0x18004a12c  lea     rdx, [rdi+198h]
0x18004a133  lea     r8, ??$factory_cache_entry_v@UHttpRequestMessage@Http@Web@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UHttpRequestMessage@Http@Web@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Web::Http::HttpRequestMessage,winrt::Windows::Foundation::IActivationFactory>
0x18004a13a  call    ??R_lambda_3657daff472b317e63d0148d109dd539_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_3657daff472b317e63d0148d109dd539_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18004a13f  nop
0x18004a140  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004a144  lock add cs:qword_18009CE08, r14
0x18004a14c  jmp     short loc_18004A178
0x18004a14e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004a152  lock add cs:qword_18009CE08, r14
0x18004a15a  lea     r8, [rdi+3B8h]
0x18004a161  lea     rax, ?_lambda_invoker_cdecl_@_lambda_3657daff472b317e63d0148d109dd539_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_3657daff472b317e63d0148d109dd539_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x18004a168  mov     [r8], rax
0x18004a16b  lea     rdx, [rdi+198h]
0x18004a172  call    ??$call@P6A?AUHttpRequestMessage@Http@Web@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UHttpRequestMessage@Http@Web@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUHttpRequestMessage@Http@Web@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18004a177  nop
0x18004a178  mov     al, [rdi+190h]
0x18004a17e  mov     [rsp+3B8h+var_320], al
0x18004a185  test    al, al
0x18004a187  jnz     short loc_18004A18E
0x18004a189  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x18004a18e  mov     r8, [rdi+620h]
0x18004a195  lea     rbx, [r8+20h]
0x18004a199  lea     rcx, [rdi+1C8h]
0x18004a1a0  add     r8, 18h
0x18004a1a4  mov     rdx, r12
0x18004a1a7  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x18004a1ac  nop
0x18004a1ad  lea     r15, [rdi+1D0h]
0x18004a1b4  mov     r8, rbx
0x18004a1b7  mov     rdx, rax
0x18004a1ba  mov     rcx, r15
0x18004a1bd  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x18004a1c2  nop
0x18004a1c3  lea     rdx, [rdi+1A8h]; struct winrt::param::hstring *
0x18004a1ca  mov     rax, [rax]
0x18004a1cd  mov     [rdx], rax
0x18004a1d0  lea     rbx, [rdi+1A0h]
0x18004a1d7  mov     rcx, rbx; this
0x18004a1da  call    ??0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@3@@Z; winrt::Windows::Foundation::Uri::Uri(winrt::param::hstring const &)
0x18004a1df  nop
0x18004a1e0  mov     rcx, [rdi+198h]
0x18004a1e7  mov     [rsp+3B8h+var_370], rcx
0x18004a1ec  lea     r12, [rdi+3C0h]
0x18004a1f3  mov     [r12], esi
0x18004a1f7  mov     [rdi+3C8h], rsi
0x18004a1fe  mov     [rdi+3D0h], rsi
0x18004a205  mov     r8, [rcx]
0x18004a208  mov     rdx, [rax]
0x18004a20b  mov     rax, [r8+68h]
0x18004a20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a214  test    eax, eax
0x18004a216  jns     short loc_18004A223
0x18004a218  mov     rdx, r12
0x18004a21b  mov     ecx, eax
0x18004a21d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a223  mov     rax, [rbx]
0x18004a226  mov     [rsp+3B8h+var_278], rax
0x18004a22e  test    rax, rax
0x18004a231  jz      short loc_18004A23C
0x18004a233  mov     rcx, rbx
0x18004a236  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004a23b  nop
0x18004a23c  mov     rbx, [r15]
0x18004a23f  mov     [rsp+3B8h+var_260], rbx
0x18004a247  test    rbx, rbx
0x18004a24a  jz      short loc_18004A27C
0x18004a24c  mov     eax, r14d
0x18004a24f  lock xadd [rbx+18h], eax
0x18004a254  sub     eax, 1
0x18004a257  jnz     short loc_18004A26E
0x18004a259  nop
0x18004a25a  call    WINRT_IMPL_GetProcessHeap
0x18004a25f  mov     rcx, rax; hHeap
0x18004a262  mov     r8, rbx; lpMem
0x18004a265  xor     edx, edx; dwFlags
0x18004a267  call    WINRT_IMPL_HeapFree
0x18004a26c  jmp     short loc_18004A279
0x18004a26e  test    eax, eax
0x18004a270  jns     short loc_18004A279
0x18004a272  call    cs:__imp_abort
0x18004a279  mov     [r15], rsi
0x18004a27c  mov     rbx, [rdi+1C8h]
0x18004a283  mov     [rsp+3B8h+var_2B8], rbx
0x18004a28b  test    rbx, rbx
0x18004a28e  jz      short loc_18004A2BD
0x18004a290  mov     eax, r14d
0x18004a293  lock xadd [rbx+18h], eax
0x18004a298  sub     eax, 1
0x18004a29b  jnz     short loc_18004A2B2
0x18004a29d  nop
0x18004a29e  call    WINRT_IMPL_GetProcessHeap
0x18004a2a3  mov     rcx, rax; hHeap
0x18004a2a6  mov     r8, rbx; lpMem
0x18004a2a9  xor     edx, edx; dwFlags
0x18004a2ab  call    WINRT_IMPL_HeapFree
0x18004a2b0  jmp     short loc_18004A2BD
0x18004a2b2  test    eax, eax
0x18004a2b4  jns     short loc_18004A2BD
0x18004a2b6  call    cs:__imp_abort
0x18004a2bd  mov     r12, [rdi+608h]
0x18004a2c4  mov     r12, [r12+38h]
0x18004a2c9  mov     rax, [r12]
0x18004a2cd  mov     rax, [rax+8]
0x18004a2d1  mov     [rsp+3B8h+var_368], rax
0x18004a2d6  lea     rbx, [rdi+1D8h]
0x18004a2dd  mov     [rbx], rsi
0x18004a2e0  mov     [rdi+1E0h], rsi
0x18004a2e7  mov     rax, [r13+8]
0x18004a2eb  test    rax, rax
0x18004a2ee  jz      short loc_18004A2F4
0x18004a2f0  lock inc dword ptr [rax+8]
0x18004a2f4  mov     rax, [r13+0]
0x18004a2f8  mov     [rbx], rax
0x18004a2fb  mov     rax, [r13+8]
0x18004a2ff  mov     [rdi+1E0h], rax
0x18004a306  lea     r15, [rdi+1E8h]
0x18004a30d  mov     rcx, [rdi+640h]
0x18004a314  mov     [r15], rcx
0x18004a317  test    rcx, rcx
0x18004a31a  jz      short loc_18004A328
0x18004a31c  mov     rdx, [rcx]
0x18004a31f  mov     rax, [rdx+8]
0x18004a323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a328  lea     rdx, [rdi+1F0h]
0x18004a32f  mov     r9, rbx
0x18004a332  mov     r8, r15
0x18004a335  mov     rcx, r12
0x18004a338  mov     rax, [rsp+3B8h+var_368]
0x18004a33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a342  nop
0x18004a343  lea     rcx, [rdi+1F8h]
0x18004a34a  lea     rdx, [rdi+20h]
0x18004a34e  mov     [rcx], rdx
0x18004a351  mov     [rdi+200h], rsi
0x18004a358  mov     [rdi+208h], rax
0x18004a35f  mov     [rdi+210h], rsi
0x18004a366  mov     r12d, 1
0x18004a36c  mov     [rdi+218h], r12b
0x18004a373  mov     [rdi+220h], sil
0x18004a37a  xor     eax, eax
0x18004a37c  mov     [rdi+221h], eax
0x18004a382  mov     [rdi+225h], ax
0x18004a389  mov     [rdi+227h], al
0x18004a38f  mov     eax, [rdi-10h]
0x18004a392  nop
0x18004a393  cmp     eax, 2
0x18004a396  jnz     short loc_18004A3C8
0x18004a398  lea     rcx, [rdi+3D8h]
0x18004a39f  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
  ... truncated ...
```
