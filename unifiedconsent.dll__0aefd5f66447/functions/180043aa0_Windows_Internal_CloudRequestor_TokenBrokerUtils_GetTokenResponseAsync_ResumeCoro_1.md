# Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync$_ResumeCoro$1

- ea: `0x180043aa0`
- end: `0x180044350`
- name: `Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync$_ResumeCoro$1`
- size: `2224`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044360`

## callees

- `0x180002834`
- `0x180003390`
- `0x180005004`
- `0x18000e4a4`
- `0x18000ed24`
- `0x18000fb28`
- `0x1800131f8`
- `0x180013f6c`
- `0x180014364`
- `0x180016498`
- `0x180016a58`
- `0x180018144`
- `0x18001c1d4`
- `0x18001cb64`
- `0x18002d994`
- `0x180038b50`
- `0x18003f190`
- `0x18003f1c8`
- `0x18003f5d0`
- `0x180040474`
- `0x180042414`
- `0x180043aa0`
- `0x1800445b8`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800442e6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800442e6`
- `msvcp_win!_Thrd_yield` at `0x180043f4c`
- `msvcp_win!_Thrd_yield` at `0x1800440ad`
- `msvcp_win!_Thrd_yield` at `0x180043f4c`
- `msvcp_win!_Thrd_yield` at `0x1800440ad`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043f2a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043f2a`

## string_xrefs

- `0x180043b2d`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x180043b56`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x180043b7e`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x180044121`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x1800441a3`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync__ResumeCoro_1(__int64 a1)
{
  __int64 v2; // r15
  __int64 (__fastcall ****v3)(_QWORD, __int64 *, __int64); // r12
  __int64 v4; // r8
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  _QWORD *v11; // rsi
  __int64 v12; // r9
  __int64 (__fastcall ***v13)(_QWORD, __int64 *, __int64); // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rsi
  const struct winrt::impl::slim_source_location *v19; // rax
  volatile __int64 *v20; // rsi
  volatile signed __int32 *v21; // rsi
  __int64 v22; // rcx
  const struct winrt::impl::slim_source_location *v23; // rax
  __int64 *v24; // rsi
  volatile __int64 *v25; // r14
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // eax
  unsigned int CloudDirectTokenHandlerError; // eax
  unsigned int v30; // eax
  __int64 *v31; // rax
  __int64 v32; // rcx
  int v33; // eax
  _QWORD *v34; // r14
  __int64 v35; // rax
  volatile signed __int32 *v36; // rsi
  int v37; // [rsp+20h] [rbp-198h]
  _BYTE pExceptionObject[24]; // [rsp+B0h] [rbp-108h] BYREF
  _BYTE v39[24]; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-D8h]
  __int64 v41; // [rsp+100h] [rbp-B8h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_89;
    case 2:
      *(_QWORD *)(a1 + 16) = 0;
      v3 = (__int64 (__fastcall ****)(_QWORD, __int64 *, __int64))(a1 + 560);
      if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a1 + 560, a1 + 16) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D1,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)0x80070057LL,
          v37);
      if ( !*(_QWORD *)(a1 + 568) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D2,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)0x80070057LL,
          v37);
      if ( !*(_QWORD *)(a1 + 576) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D3,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)0x80070057LL,
          v37);
      v4 = *(_QWORD *)(v2 + 544);
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      v5 = *(_QWORD *)(v4 + 16);
      if ( !v5 )
        goto LABEL_37;
      v6 = *(_DWORD *)(v5 + 8);
      do
      {
        if ( !v6 )
LABEL_37:
          std::_Throw_bad_weak_ptr();
        v7 = v6;
        v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      }
      while ( v7 != v6 );
      *(_QWORD *)(a1 + 24) = *(_QWORD *)(v4 + 8);
      *(_QWORD *)(a1 + 32) = *(_QWORD *)(v4 + 16);
      *(_QWORD *)(a1 + 272) = a1 - 112;
      *(_BYTE *)(a1 - 112 + 48) = 1;
      winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
        a1 + 560,
        a1 + 40);
      *(_QWORD *)(a1 + 56) = *(_QWORD *)(a1 + 576);
      *(_QWORD *)(a1 + 88) = *(_QWORD *)(a1 + 568);
      *(_QWORD *)(a1 + 288) = a1 + 40;
      *(_QWORD *)(a1 + 296) = a1 + 88;
      *(_QWORD *)(a1 + 304) = a1 + 56;
      *(_QWORD *)(a1 + 312) = &qword_18009D008;
      _InterlockedAdd64(&qword_18009D008, 1u);
      v8 = (__int64 *)winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequest,winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequest,winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory> )
      {
        *(_QWORD *)(a1 + 320) = 0;
        *(_DWORD *)(a1 + 328) = 0;
        *(_QWORD *)(a1 + 336) = 0;
        *(_QWORD *)(a1 + 344) = 0;
        v9 = *v8;
        v40 = *(_QWORD *)(a1 + 56);
        v41 = *(_QWORD *)(a1 + 88);
        v37 = a1 + 320;
        v10 = (*(__int64 (__fastcall **)(__int64 *))(v9 + 48))(v8);
        if ( v10 < 0 )
          winrt::throw_hresult((unsigned int)v10, a1 + 328);
        v11 = (_QWORD *)(a1 + 48);
        *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 320);
        _InterlockedDecrement64(&qword_18009D008);
      }
      else
      {
        _InterlockedDecrement64(&qword_18009D008);
        v11 = (_QWORD *)(a1 + 48);
        winrt::impl::factory_cache_entry<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequest,winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>::call<_lambda_ff84475bd4cb9e55983b607a673f469d_ &>(
          0,
          a1 + 48);
      }
      v12 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
              v11,
              a1 + 120);
      if ( a20[3]
        || (*(_DWORD *)(a1 + 136) = 1,
            *(_DWORD *)(a1 + 140) = 3,
            *(_QWORD *)(a1 + 152) = L"2.0",
            *(_QWORD *)(a1 + 128) = a1 + 136,
            aApiVersion[11]) )
      {
        abort();
      }
      *(_DWORD *)(a1 + 168) = 1;
      *(_DWORD *)(a1 + 172) = 11;
      *(_QWORD *)(a1 + 184) = L"api-version";
      *(_QWORD *)(a1 + 160) = a1 + 168;
      winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::hstring>,winrt::hstring,winrt::hstring>::Insert(v12);
      if ( *(_QWORD *)(a1 + 120) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 120);
      v13 = *v3;
      if ( *v3 )
      {
        *(_QWORD *)(a1 + 352) = 0;
        *(_DWORD *)(a1 + 360) = 0;
        *(_QWORD *)(a1 + 368) = 0;
        *(_QWORD *)(a1 + 376) = 0;
        v15 = (**v13)(v13, winrt::impl::guid_v<winrt::Windows::Security::Credentials::IWebAccount>, a1 + 352);
        if ( v15 < 0 )
          winrt::throw_hresult((unsigned int)v15, a1 + 360);
        v14 = *(_QWORD *)(a1 + 352);
      }
      else
      {
        v14 = 0;
      }
      *(_QWORD *)(a1 + 192) = v14;
      *(_QWORD *)(a1 + 384) = v11;
      *(_QWORD *)(a1 + 392) = a1 + 192;
      *(_QWORD *)(a1 + 424) = &qword_18009CDA8;
      _InterlockedAdd64(&qword_18009CDA8, 1u);
      v16 = winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Authentication::Web::Core::WebAuthenticationCoreManager,winrt::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Authentication::Web::Core::WebAuthenticationCoreManager,winrt::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> )
      {
        *(_QWORD *)(a1 + 432) = 0;
        *(_DWORD *)(a1 + 440) = 0;
        *(_QWORD *)(a1 + 448) = 0;
        *(_QWORD *)(a1 + 456) = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v16 + 56LL))(
                v16,
                *v11,
                *(_QWORD *)(a1 + 192),
                a1 + 432);
        if ( v17 < 0 )
          winrt::throw_hresult((unsigned int)v17, a1 + 440);
        v18 = a1 + 200;
        *(_QWORD *)(a1 + 200) = *(_QWORD *)(a1 + 432);
        _InterlockedDecrement64(&qword_18009CDA8);
      }
      else
      {
        _InterlockedDecrement64(&qword_18009CDA8);
        v18 = a1 + 200;
        winrt::impl::factory_cache_entry<winrt::Windows::Security::Authentication::Web::Core::WebAuthenticationCoreManager,winrt::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::call<_lambda_0a8107739f92a0afef5b8db6e3b7e099_ &>(
          0,
          a1 + 200,
          a1 + 384);
      }
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 400);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v19);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 208) = 0;
      *(_QWORD *)(a1 + 216) = v18;
      *(_QWORD *)(a1 + 224) = 0;
      *(_BYTE *)(a1 + 232) = 1;
      *(_WORD *)v2 = 6;
      if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type>(
                               a1 + 208,
                               a1) )
      {
LABEL_54:
        *(_DWORD *)(a1 + 464) = 0;
        *(_QWORD *)(a1 + 472) = 0;
        *(_QWORD *)(a1 + 480) = 0;
        v22 = *(unsigned int *)(a1 + 228);
        if ( (int)v22 < 0 )
          winrt::throw_hresult(v22, a1 + 464);
        if ( *(_DWORD *)(a1 + 224) == 2 )
        {
          v23 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 496);
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v39, v23);
          throw (winrt::hresult_canceled *)v39;
        }
        v24 = (__int64 *)(a1 + 240);
        winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::GetResults(
          *(_QWORD *)(a1 + 216),
          a1 + 240);
        v25 = *(volatile __int64 **)(a1 + 208);
        if ( v25 )
        {
          while ( _InterlockedExchange64(v25, 0) == 1 )
            _Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 200) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 200);
        if ( *(_QWORD *)(a1 + 192) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 192);
        v26 = winrt::impl::consume_Windows_Internal_Shell_ConsentUx_IPrimaryIdResult<winrt::Windows::Internal::Shell::ConsentUx::IPrimaryIdResult>::Reason(a1 + 240);
        v27 = a1 + 240;
        if ( v26 )
        {
          v28 = winrt::impl::consume_Windows_Internal_Shell_ConsentUx_IPrimaryIdResult<winrt::Windows::Internal::Shell::ConsentUx::IPrimaryIdResult>::Reason(v27);
          CloudDirectTokenHandlerError = GetCloudDirectTokenHandlerError(v28);
          v30 = wil::verify_hresult<long>(CloudDirectTokenHandlerError);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E9,
            (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
            (const char *)v30,
            v37);
        }
        v31 = (__int64 *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
                           v27,
                           a1 + 248);
        *(_DWORD *)(a1 + 488) = 0;
        v32 = *v31;
        *(_DWORD *)(a1 + 520) = 0;
        *(_QWORD *)(a1 + 528) = 0;
        *(_QWORD *)(a1 + 536) = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 56LL))(v32, a1 + 488);
        if ( v33 < 0 )
          winrt::throw_hresult((unsigned int)v33, a1 + 520);
        if ( !*(_DWORD *)(a1 + 488) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1ED,
            (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
            (const char *)0x800703F0LL,
            v37);
        if ( *(_QWORD *)(a1 + 248) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 248);
        v34 = (_QWORD *)(a1 - 8);
        if ( (__int64 *)(a1 - 8) != v24 )
        {
          if ( *v34 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 8);
          v35 = *v24;
          *v24 = 0;
          *v34 = v35;
        }
        if ( *v24 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 240);
        if ( *(_QWORD *)(a1 + 48) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 48);
        if ( *(_QWORD *)(a1 + 40) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 40);
        v36 = *(volatile signed __int32 **)(a1 + 32);
        if ( v36 )
        {
          if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
            if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
          }
        }
        *(_QWORD *)(a1 + 256) = *(_QWORD *)(a1 + 272);
        *(_WORD *)v2 = 0;
        if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,void>::final_suspend_awaiter::await_suspend() )
        {
LABEL_89:
          if ( *(_QWORD *)(a1 - 8) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 8);
          if ( *(_QWORD *)(a1 - 24) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
          if ( *(_QWORD *)(a1 - 32) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 32);
          __ExceptionPtrDestroy((void *)(a1 - 56));
          __1__root_implements_U__map_impl_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_V__unordered_map_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_U__hash_Uhstring_winrt___std__U__equal_to_Uhstring_winrt___8_V__allocator_U__pair___CBUhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__std___8__std__Umulti_threaded_collection_base_impl_2__impl_winrt__U__IMap_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_3_U__IMapView_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__5673_U__IIterable_U__IKeyValuePair_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_winrt___5673__impl_winrt__MEAA_XZ(a1 - 112);
          Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync_::_6_::_parameters_::__parameters_(v2 + 544);
          if ( *(_WORD *)(a1 + 10) )
            operator delete((void *)(a1 - 112), 0x2C0u);
        }
      }
      return;
    case 6:
      goto LABEL_54;
    case 7:
      v20 = *(volatile __int64 **)(a1 + 208);
      if ( v20 )
      {
        while ( _InterlockedExchange64(v20, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 200) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 200);
      if ( *(_QWORD *)(a1 + 192) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 192);
      if ( *(_QWORD *)(a1 + 48) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 48);
      if ( *(_QWORD *)(a1 + 40) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 40);
      v21 = *(volatile signed __int32 **)(a1 + 32);
      if ( v21 )
      {
        if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
      goto LABEL_89;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180043aa0  mov     [rsp+arg_0], rcx
0x180043aa5  push    rbx
0x180043aa6  push    rsi
0x180043aa7  push    rdi
0x180043aa8  push    r12
0x180043aaa  push    r13
0x180043aac  push    r14
0x180043aae  push    r15
0x180043ab0  sub     rsp, 180h
0x180043ab7  mov     rbx, [rsp+1B8h+arg_0]
0x180043abf  lea     r15, [rbx+8]
0x180043ac3  movzx   eax, word ptr [r15]
0x180043ac7  mov     [rsp+1B8h+var_188], ax
0x180043acc  mov     r13d, 1
0x180043ad2  add     ax, r13w
0x180043ad6  cmp     ax, 8; switch 9 cases
0x180043ada  ja      def_180043AFA; jumptable 0000000180043AFA default case, cases 1,5,6
0x180043ae0  mov     [rsp+1B8h+var_170], r15
0x180043ae5  movsx   rax, ax
0x180043ae9  lea     rdx, cs:180000000h
0x180043af0  mov     ecx, ds:(jpt_180043AFA - 180000000h)[rdx+rax*4]
0x180043af7  add     rcx, rdx
0x180043afa  jmp     rcx; switch jump
0x180043afc  xor     edi, edi; jumptable 0000000180043AFA case 4
0x180043afe  jmp     loc_1800442B8
0x180043b03  xor     edi, edi; jumptable 0000000180043AFA case 3
0x180043b05  lea     rdx, [rbx+10h]
0x180043b09  mov     [rdx], rdi
0x180043b0c  lea     r12, [rdx+220h]
0x180043b13  mov     rcx, r12
0x180043b16  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180043b1b  mov     rcx, [rsp+1B8h]; this
0x180043b23  test    al, al
0x180043b25  jz      short loc_180043B3F
0x180043b27  mov     r9d, 80070057h; char *
0x180043b2d  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180043b34  mov     edx, 1D1h; void *
0x180043b39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043b3f  mov     rcx, [rsp+1B8h]; this
0x180043b47  cmp     [rbx+238h], rdi
0x180043b4e  jnz     short loc_180043B67
0x180043b50  mov     r9d, 80070057h; char *
0x180043b56  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180043b5d  mov     edx, 1D2h; void *
0x180043b62  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043b67  mov     rcx, [rsp+1B8h]; this
0x180043b6f  cmp     [rbx+240h], rdi
0x180043b76  jnz     short loc_180043B8F
0x180043b78  mov     r9d, 80070057h; char *
0x180043b7e  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180043b85  mov     edx, 1D3h; void *
0x180043b8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043b8f  mov     r8, [r15+220h]
0x180043b96  mov     [rbx+18h], rdi
0x180043b9a  mov     [rbx+20h], rdi
0x180043b9e  mov     rdx, [r8+10h]
0x180043ba2  test    rdx, rdx
0x180043ba5  jz      loc_180043F31
0x180043bab  mov     eax, [rdx+8]
0x180043bae  jmp     short loc_180043BBA
0x180043bb0  lea     ecx, [rax+1]
0x180043bb3  lock cmpxchg [rdx+8], ecx
0x180043bb8  jz      short loc_180043BC3
0x180043bba  test    eax, eax
0x180043bbc  jnz     short loc_180043BB0
0x180043bbe  jmp     loc_180043F31
0x180043bc3  mov     rax, [r8+8]
0x180043bc7  mov     [rbx+18h], rax
0x180043bcb  mov     rax, [r8+10h]
0x180043bcf  mov     [rbx+20h], rax
0x180043bd3  lea     rax, [rbx-70h]
0x180043bd7  mov     [rbx+110h], rax
0x180043bde  mov     [rax+30h], r13b
0x180043be2  lea     rsi, [rbx+28h]
0x180043be6  mov     rdx, rsi
0x180043be9  mov     rcx, r12
0x180043bec  call    ?ClientId@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(void)
0x180043bf1  nop
0x180043bf2  lea     r9, [rbx+38h]
0x180043bf6  mov     rax, [rbx+240h]
0x180043bfd  mov     [r9], rax
0x180043c00  lea     rdx, [rbx+58h]
0x180043c04  mov     rax, [rbx+238h]
0x180043c0b  mov     [rdx], rax
0x180043c0e  lea     r8, [rbx+120h]
0x180043c15  mov     [r8], rsi
0x180043c18  mov     [rbx+128h], rdx
0x180043c1f  mov     [rbx+130h], r9
0x180043c26  lea     rax, qword_18009D008
0x180043c2d  mov     [rbx+138h], rax
0x180043c34  lock add cs:qword_18009D008, r13
0x180043c3c  mov     rcx, cs:??$factory_cache_entry_v@UWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@UIWebTokenRequestFactory@234567@@impl@winrt@@3U?$factory_cache_entry@UWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@UIWebTokenRequestFactory@234567@@12@A; factory_cache_entry<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequest,winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>::winrt::factory_cache_entry<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequest,winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequest,winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>
0x180043c43  test    rcx, rcx
0x180043c46  jz      loc_180043CCC
0x180043c4c  lea     r13, [rbx+140h]
0x180043c53  mov     [r13+0], rdi
0x180043c57  lea     r14, [rbx+148h]
0x180043c5e  mov     [r14], edi
0x180043c61  mov     [rbx+150h], rdi
0x180043c68  mov     [rbx+158h], rdi
0x180043c6f  mov     rax, [rcx]
0x180043c72  mov     r9, [r9]
0x180043c75  mov     [rsp+1B8h+var_D8], r9
0x180043c7d  mov     r8, [rdx]
0x180043c80  mov     [rsp+1B8h+var_B8], r8
0x180043c88  mov     rdx, [rsi]
0x180043c8b  mov     [rsp+1B8h+var_180], rdx
0x180043c90  mov     qword ptr [rsp+1B8h+var_198], r13
0x180043c95  mov     rax, [rax+30h]
0x180043c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c9e  test    eax, eax
0x180043ca0  jns     short loc_180043CAC
0x180043ca2  mov     rdx, r14
0x180043ca5  mov     ecx, eax
0x180043ca7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180043cac  lea     rsi, [rbx+30h]
0x180043cb0  mov     rax, [r13+0]
0x180043cb4  mov     [rsp+1B8h+var_148], rax
0x180043cb9  mov     [rsi], rax
0x180043cbc  lock dec cs:qword_18009D008
0x180043cc4  mov     r13d, 1
0x180043cca  jmp     short loc_180043CE1
0x180043ccc  lock dec cs:qword_18009D008
0x180043cd4  lea     rsi, [rbx+30h]
0x180043cd8  mov     rdx, rsi
0x180043cdb  call    ??$call@AEAV_lambda_ff84475bd4cb9e55983b607a673f469d_@@@?$factory_cache_entry@UWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@UIWebTokenRequestFactory@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_ff84475bd4cb9e55983b607a673f469d_@@@Z
0x180043ce0  nop
0x180043ce1  lea     r14, [rbx+78h]
0x180043ce5  mov     rdx, r14
0x180043ce8  mov     rcx, rsi
0x180043ceb  call    ?Properties@?$consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(void)
0x180043cf0  mov     r9, rax
0x180043cf3  cmp     word ptr cs:a20+6, di; ""
0x180043cfa  jnz     loc_180043F2A
0x180043d00  lea     rcx, [rbx+88h]
0x180043d07  mov     [rcx], r13d
0x180043d0a  mov     dword ptr [rbx+8Ch], 3
0x180043d14  lea     rax, a20; "2.0"
0x180043d1b  mov     [rbx+98h], rax
0x180043d22  lea     r8, [rbx+80h]
0x180043d29  mov     [r8], rcx
0x180043d2c  cmp     word ptr cs:aApiVersion+16h, di; ""
0x180043d33  jnz     loc_180043F2A
0x180043d39  lea     rax, [rbx+0A8h]
0x180043d40  mov     [rax], r13d
0x180043d43  mov     dword ptr [rbx+0ACh], 0Bh
0x180043d4d  lea     rcx, aApiVersion; "api-version"
0x180043d54  mov     [rbx+0B8h], rcx
0x180043d5b  lea     rdx, [rbx+0A0h]
0x180043d62  mov     [rdx], rax
0x180043d65  mov     rcx, r9
0x180043d68  call    ?Insert@?$consume_Windows_Foundation_Collections_IMap@U?$IMap@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@Uhstring@5@U65@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::hstring>,winrt::hstring,winrt::hstring>::Insert(winrt::param::hstring const &,winrt::param::hstring const &)
0x180043d6d  nop
0x180043d6e  mov     rax, [r14]
0x180043d71  mov     [rsp+1B8h+var_140], rax
0x180043d76  test    rax, rax
0x180043d79  jz      short loc_180043D83
0x180043d7b  mov     rcx, r14
0x180043d7e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180043d83  mov     rcx, [r12]
0x180043d87  test    rcx, rcx
0x180043d8a  jnz     short loc_180043D91
0x180043d8c  mov     rcx, rdi
0x180043d8f  jmp     short loc_180043DE2
0x180043d91  lea     r14, [rbx+160h]
0x180043d98  mov     [r14], rdi
0x180043d9b  lea     r12, [rbx+168h]
0x180043da2  mov     [r12], edi
0x180043da6  mov     [rbx+170h], rdi
0x180043dad  mov     [rbx+178h], rdi
0x180043db4  mov     rax, [rcx]
0x180043db7  mov     r8, r14
0x180043dba  lea     rdx, ??$guid_v@UIWebAccount@Credentials@Security@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Security::Credentials::IWebAccount>
0x180043dc1  mov     rax, [rax]
0x180043dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dc9  test    eax, eax
0x180043dcb  jns     short loc_180043DD7
0x180043dcd  mov     rdx, r12
0x180043dd0  mov     ecx, eax
0x180043dd2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180043dd7  mov     rcx, [r14]
0x180043dda  mov     [rsp+1B8h+var_138], rcx
0x180043de2  mov     rdx, rbx
0x180043de5  mov     eax, 0C0h
0x180043dea  lea     r8, [rax+rbx]
0x180043dee  mov     [r8], rcx
0x180043df1  lea     rax, [rbx+180h]
0x180043df8  mov     [rax], rsi
0x180043dfb  mov     [rbx+188h], r8
0x180043e02  lea     rcx, qword_18009CDA8
0x180043e09  mov     [rbx+1A8h], rcx
0x180043e10  lock add cs:qword_18009CDA8, r13
0x180043e18  mov     rcx, cs:??$factory_cache_entry_v@UWebAuthenticationCoreManager@Core@Web@Authentication@Security@Windows@winrt@@UIWebAuthenticationCoreManagerStatics@234567@@impl@winrt@@3U?$factory_cache_entry@UWebAuthenticationCoreManager@Core@Web@Authentication@Security@Windows@winrt@@UIWebAuthenticationCoreManagerStatics@234567@@12@A; factory_cache_entry<winrt::Windows::Security::Authentication::Web::Core::WebAuthenticationCoreManager,winrt::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>::winrt::factory_cache_entry<winrt::Windows::Security::Authentication::Web::Core::WebAuthenticationCoreManager,winrt::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Security::Authentication::Web::Core::WebAuthenticationCoreManager,winrt::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>
0x180043e1f  test    rcx, rcx
0x180043e22  jz      short loc_180043E99
0x180043e24  lea     r14, [rbx+1B0h]
0x180043e2b  mov     [r14], rdi
0x180043e2e  lea     r12, [rbx+1B8h]
0x180043e35  mov     [r12], edi
0x180043e39  mov     [rbx+1C0h], rdi
0x180043e40  mov     [rbx+1C8h], rdi
0x180043e47  mov     rax, [rcx]
0x180043e4a  mov     r8, [r8]
0x180043e4d  mov     [rsp+1B8h+arg_10], r8
0x180043e55  mov     rdx, [rsi]
0x180043e58  mov     [rsp+1B8h+arg_18], rdx
0x180043e60  mov     r9, r14
0x180043e63  mov     rax, [rax+38h]
0x180043e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e6c  test    eax, eax
0x180043e6e  jns     short loc_180043E7A
0x180043e70  mov     rdx, r12
0x180043e73  mov     ecx, eax
0x180043e75  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180043e7a  lea     rsi, [rbx+0C8h]
0x180043e81  mov     rax, [r14]
0x180043e84  mov     [rsp+1B8h+var_130], rax
0x180043e8c  mov     [rsi], rax
0x180043e8f  lock dec cs:qword_18009CDA8
0x180043e97  jmp     short loc_180043EB4
0x180043e99  lock dec cs:qword_18009CDA8
0x180043ea1  lea     rsi, [rbx+0C8h]
0x180043ea8  mov     r8, rax
0x180043eab  mov     rdx, rsi
0x180043eae  call    ??$call@AEAV_lambda_0a8107739f92a0afef5b8db6e3b7e099_@@@?$factory_cache_entry@UWebAuthenticationCoreManager@Core@Web@Authentication@Security@Windows@winrt@@UIWebAuthenticationCoreManagerStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_0a8107739f92a0afef5b8db6e3b7e099_@@@Z
0x180043eb3  nop
0x180043eb4  mov     eax, [rbx-10h]
0x180043eb7  nop
0x180043eb8  cmp     eax, 2
0x180043ebb  jnz     short loc_180043EED
0x180043ebd  lea     rcx, [rbx+190h]
0x180043ec4  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180043ec9  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180043ecc  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x180043ed4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180043ed9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180043ee0  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x180043ee8  call    _CxxThrowException_0
0x180043eed  lea     rcx, [rbx+0D0h]
0x180043ef4  mov     [rcx], rdi
0x180043ef7  mov     [rbx+0D8h], rsi
0x180043efe  mov     [rbx+0E0h], rdi
0x180043f05  mov     [rbx+0E8h], r13b
0x180043f0c  mov     eax, 6
0x180043f11  mov     [r15], ax
0x180043f15  mov     rdx, rbx
0x180043f18  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@Uhstring@4@Uhstring@4@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@Uhstring@4@Uhstring@4@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type>)
0x180043f1d  test    al, al
0x180043f1f  jz      loc_180044015
0x180043f25  jmp     loc_180044318
0x180043f2a  call    cs:__imp_abort
0x180043f31  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x180043f37  mov     rsi, [rbx+0D0h]; jumptable 0000000180043AFA case 8
0x180043f3e  xor     edi, edi
0x180043f40  test    rsi, rsi
0x180043f43  jz      short loc_180043F5D
0x180043f45  mov     [rsp+1B8h+var_168], rsi
0x180043f4a  jmp     short loc_180043F52
0x180043f4c  call    cs:__imp__Thrd_yield
0x180043f52  mov     rax, rdi
0x180043f55  xchg    rax, [rsi]
0x180043f58  cmp     rax, r13
0x180043f5b  jz      short loc_180043F4C
0x180043f5d  lea     rcx, [rbx+0C8h]
0x180043f64  mov     rax, [rcx]
0x180043f67  mov     [rsp+1B8h+var_178], rax
0x180043f6c  test    rax, rax
0x180043f6f  jz      short loc_180043F77
0x180043f71  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180043f76  nop
0x180043f77  lea     rcx, [rbx+0C0h]
0x180043f7e  mov     rax, [rcx]
0x180043f81  mov     [rsp+1B8h+arg_10], rax
0x180043f89  test    rax, rax
0x180043f8c  jz      short loc_180043F94
0x180043f8e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180043f93  nop
0x180043f94  lea     rcx, [rbx+30h]
0x180043f98  mov     rax, [rcx]
0x180043f9b  mov     [rsp+1B8h+arg_18], rax
0x180043fa3  test    rax, rax
0x180043fa6  jz      short loc_180043FAE
0x180043fa8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180043fad  nop
0x180043fae  lea     rcx, [rbx+28h]
0x180043fb2  mov     rax, [rcx]
0x180043fb5  mov     [rsp+1B8h+var_180], rax
0x180043fba  test    rax, rax
0x180043fbd  jz      short loc_180043FC5
0x180043fbf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180043fc4  nop
0x180043fc5  mov     rsi, [rbx+20h]
0x180043fc9  test    rsi, rsi
0x180043fcc  jz      short loc_18004400E
0x180043fce  mov     [rsp+1B8h+var_110], rsi
0x180043fd6  or      eax, 0FFFFFFFFh
0x180043fd9  lock xadd [rsi+8], eax
0x180043fde  cmp     eax, 1
0x180043fe1  jnz     short loc_18004400E
0x180043fe3  mov     rax, [rsi]
  ... truncated ...
```
