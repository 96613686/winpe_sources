# Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync$_ResumeCoro$1

- ea: `0x180043000`
- end: `0x1800438c4`
- name: `Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync$_ResumeCoro$1`
- size: `2244`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800438d0`

## callees

- `0x180002810`
- `0x180002834`
- `0x180003390`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000e4a4`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x18000fb28`
- `0x1800131f8`
- `0x180013efc`
- `0x180013f6c`
- `0x180014364`
- `0x180016498`
- `0x18001c1d4`
- `0x18002d8ec`
- `0x180038b50`
- `0x18003f0c0`
- `0x180040150`
- `0x180040404`
- `0x180040520`
- `0x180040ab0`
- `0x1800412f0`
- `0x180042aec`
- `0x180043000`
- `0x180046e48`
- `0x180047128`
- `0x1800486cc`
- `0x18007d010`

## import_xrefs

- `msvcp_win!_Thrd_yield` at `0x1800433a0`
- `msvcp_win!_Thrd_yield` at `0x180043594`
- `msvcp_win!_Thrd_yield` at `0x1800433a0`
- `msvcp_win!_Thrd_yield` at `0x180043594`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043406`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043444`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043701`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043758`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043796`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043406`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043444`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043701`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043758`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180043796`

## string_xrefs

- `0x180043121`: `TokenBrokerHandler_GetTokenAsync`
- `0x1800430ba`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x1800431ae`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync__ResumeCoro_1(__int64 a1)
{
  _WORD *v2; // r14
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  struct winrt::impl::shared_hstring_header **v7; // r15
  _QWORD *v8; // rdx
  __int64 v9; // rax
  int ScopeAndClientId; // eax
  unsigned int v11; // edx
  struct winrt::impl::shared_hstring_header *v12; // rbx
  unsigned int v13; // r15d
  const void *v14; // r12
  struct winrt::impl::shared_hstring_header *v15; // rbx
  unsigned int v16; // r15d
  __int64 v17; // rcx
  __int64 v18; // rax
  const struct winrt::impl::slim_source_location *v19; // rax
  volatile __int64 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  int v22; // eax
  HANDLE v23; // rax
  volatile signed __int32 *v24; // rbx
  int v25; // eax
  HANDLE v26; // rax
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rcx
  const struct winrt::impl::slim_source_location *v29; // rax
  volatile __int64 *v30; // rbx
  __int64 *v31; // rax
  __int64 *v32; // rbx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  int v36; // eax
  volatile signed __int32 **v37; // r13
  volatile signed __int32 *v38; // rbx
  int v39; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v41; // rbx
  int v42; // eax
  HANDLE v43; // rax
  volatile signed __int32 *v44; // rbx
  int v45; // eax
  HANDLE v46; // rax
  volatile signed __int32 *v47; // rbx
  int v48; // [rsp+20h] [rbp-198h]
  void *Source; // [rsp+30h] [rbp-188h]
  __int64 v50; // [rsp+40h] [rbp-178h]
  _WORD *v51; // [rsp+58h] [rbp-160h]
  __int64 *v52; // [rsp+68h] [rbp-150h]
  __int64 *v53; // [rsp+70h] [rbp-148h]
  _BYTE pExceptionObject[24]; // [rsp+D0h] [rbp-E8h] BYREF
  _BYTE v55[160]; // [rsp+E8h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  v51 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_95;
    case 2:
      *(_DWORD *)(a1 + 576) = 0;
      *(_QWORD *)(a1 + 16) = 0;
      v52 = (__int64 *)(a1 + 736);
      if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a1 + 736, a1 + 16) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)0x80070057LL,
          v48);
      v3 = (_QWORD *)*((_QWORD *)v2 + 90);
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      v4 = v3[2];
      if ( !v4 )
        goto LABEL_31;
      v5 = *(_DWORD *)(v4 + 8);
      do
      {
        if ( !v5 )
LABEL_31:
          std::_Throw_bad_weak_ptr();
        v6 = v5;
        v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
      }
      while ( v6 != v5 );
      *(_QWORD *)(a1 + 24) = v3[1];
      *(_QWORD *)(a1 + 32) = v3[2];
      *(_QWORD *)(a1 + 560) = a1 - 112;
      *(_BYTE *)(a1 - 112 + 48) = 1;
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        a1 + 48,
        "TokenBrokerHandler_GetTokenAsync");
      *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::`vftable';
      Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::StartActivity((Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync *)(a1 + 48));
      *(_QWORD *)(a1 + 384) = 0;
      v7 = (struct winrt::impl::shared_hstring_header **)(a1 + 392);
      *(_QWORD *)(a1 + 392) = 0;
      v8 = (_QWORD *)(a1 + 400);
      *(_QWORD *)(a1 + 400) = 0;
      *(_QWORD *)(a1 + 408) = 0;
      v9 = *(_QWORD *)(a1 + 752);
      if ( v9 )
        _InterlockedAdd((volatile signed __int32 *)(v9 + 8), 1u);
      *v8 = *(_QWORD *)(a1 + 744);
      *(_QWORD *)(a1 + 408) = *(_QWORD *)(a1 + 752);
      ScopeAndClientId = Windows::Internal::CloudRequestor::TokenBrokerHandler::GetScopeAndClientId(
                           v3,
                           v8,
                           a1 + 384,
                           a1 + 392);
      if ( ScopeAndClientId < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)(unsigned int)ScopeAndClientId,
          v48);
      v53 = (__int64 *)v3[7];
      v50 = *v53;
      *(_QWORD *)(a1 + 424) = a1 + 416;
      v12 = *v7;
      if ( !*v7 )
        goto LABEL_14;
      if ( (*(_DWORD *)v12 & 1) != 0 )
      {
        v13 = *((_DWORD *)v12 + 1);
        if ( v13 )
        {
          v14 = (const void *)*((_QWORD *)v12 + 2);
          v12 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v13, v11);
          memcpy_s((char *)v12 + 28, 2LL * v13, v14, 2LL * v13);
        }
        else
        {
LABEL_14:
          v12 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v12 + 6);
      }
      *(_QWORD *)(a1 + 416) = v12;
      v15 = *(struct winrt::impl::shared_hstring_header **)(a1 + 384);
      if ( !v15 )
        goto LABEL_20;
      if ( (*(_DWORD *)v15 & 1) != 0 )
      {
        v16 = *((_DWORD *)v15 + 1);
        if ( v16 )
        {
          Source = (void *)*((_QWORD *)v15 + 2);
          v15 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v16, v11);
          memcpy_s((char *)v15 + 28, 2LL * v16, Source, 2LL * v16);
        }
        else
        {
LABEL_20:
          v15 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v15 + 6);
      }
      *(_QWORD *)(a1 + 432) = v15;
      v17 = *v52;
      *(_QWORD *)(a1 + 440) = *v52;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64))(v50 + 8))(
              v53,
              a1 + 448,
              a1 + 440,
              a1 + 432,
              a1 + 416);
      *(_QWORD *)(a1 + 456) = a1 + 48;
      *(_QWORD *)(a1 + 464) = 0;
      *(_QWORD *)(a1 + 472) = v18;
      *(_QWORD *)(a1 + 480) = 0;
      *(_BYTE *)(a1 + 488) = 1;
      *(_BYTE *)(a1 + 496) = 0;
      *(_DWORD *)(a1 + 497) = 0;
      *(_WORD *)(a1 + 501) = 0;
      *(_BYTE *)(a1 + 503) = 0;
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v19 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 584);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v19);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 504) = a1;
      *v2 = 6;
      if ( !(unsigned __int8)wil::details::coro::coroutine_withsuspend_awaiter<Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,1>>::await_suspend<std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type>>() )
      {
LABEL_53:
        if ( *(_BYTE *)(a1 + 496) )
          wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::resume(*(_QWORD *)(a1 + 456));
        *(_DWORD *)(a1 + 608) = 0;
        *(_QWORD *)(a1 + 616) = 0;
        *(_QWORD *)(a1 + 624) = 0;
        v28 = *(unsigned int *)(a1 + 484);
        if ( (int)v28 < 0 )
          winrt::throw_hresult(v28, a1 + 608);
        if ( *(_DWORD *)(a1 + 480) == 2 )
        {
          v29 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 632);
          winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v55, v29);
          throw (winrt::hresult_canceled *)v55;
        }
        winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::GetResults(
          *(_QWORD *)(a1 + 472),
          a1 + 512);
        v30 = *(volatile __int64 **)(a1 + 464);
        if ( v30 )
        {
          while ( _InterlockedExchange64(v30, 0) == 1 )
            _Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 448) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 448);
        v31 = (__int64 *)winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
                           a1 + 512,
                           a1 + 520);
        v32 = (__int64 *)(a1 + 528);
        *(_QWORD *)(a1 + 528) = 0;
        *(_DWORD *)(a1 + 576) = 15;
        v33 = *v31;
        *(_DWORD *)(a1 + 656) = 0;
        *(_QWORD *)(a1 + 664) = 0;
        *(_QWORD *)(a1 + 672) = 0;
        v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v33 + 48LL))(v33, 0, a1 + 528);
        if ( v34 < 0 )
          winrt::throw_hresult((unsigned int)v34, a1 + 656);
        *(_QWORD *)(a1 + 680) = 0;
        v35 = *v32;
        *(_DWORD *)(a1 + 688) = 0;
        *(_QWORD *)(a1 + 696) = 0;
        *(_QWORD *)(a1 + 704) = 0;
        v36 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 48LL))(v35, a1 + 680);
        if ( v36 < 0 )
          winrt::throw_hresult((unsigned int)v36, a1 + 688);
        v37 = (volatile signed __int32 **)(a1 + 536);
        *(_QWORD *)(a1 + 536) = *(_QWORD *)(a1 + 680);
        if ( *v32 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 528);
        if ( *(_QWORD *)(a1 + 520) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 520);
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          (_QWORD *)(a1 + 48),
          0);
        winrt::hstring::operator=(*(_QWORD *)(a1 + 560) + 104LL, a1 + 536);
        v38 = *v37;
        if ( *v37 )
        {
          v39 = _InterlockedDecrement(v38 + 6);
          if ( v39 )
          {
            if ( v39 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v38);
          }
        }
        if ( *(_QWORD *)(a1 + 512) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 512);
        v41 = *(volatile signed __int32 **)(a1 + 392);
        if ( v41 )
        {
          v42 = _InterlockedDecrement(v41 + 6);
          if ( v42 )
          {
            if ( v42 < 0 )
              abort();
          }
          else
          {
            v43 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v43, 0, (LPVOID)v41);
          }
        }
        v44 = *(volatile signed __int32 **)(a1 + 384);
        if ( v44 )
        {
          v45 = _InterlockedDecrement(v44 + 6);
          if ( v45 )
          {
            if ( v45 < 0 )
              abort();
          }
          else
          {
            v46 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v46, 0, (LPVOID)v44);
          }
        }
        *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::`vftable';
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 48);
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 48);
        if ( *(_QWORD *)(a1 + 32) )
        {
          v47 = *(volatile signed __int32 **)(a1 + 32);
          if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        v2 = v51;
        *(_QWORD *)(a1 + 544) = a1 - 112;
        *v51 = 0;
        if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::final_suspend_awaiter::await_suspend() )
        {
LABEL_95:
          std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::~promise_type(a1 - 112);
          Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync_::_11_::_parameters_::__parameters_(v2 + 360);
          if ( *(_WORD *)(a1 + 10) )
            operator delete((void *)(a1 - 112), 0x370u);
        }
      }
      return;
    case 6:
      goto LABEL_53;
    case 7:
      v20 = *(volatile __int64 **)(a1 + 464);
      if ( v20 )
      {
        while ( _InterlockedExchange64(v20, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 448) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 448);
      v21 = *(volatile signed __int32 **)(a1 + 392);
      if ( v21 )
      {
        v22 = _InterlockedDecrement(v21 + 6);
        if ( v22 )
        {
          if ( v22 < 0 )
            abort();
        }
        else
        {
          v23 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v23, 0, (LPVOID)v21);
        }
      }
      v24 = *(volatile signed __int32 **)(a1 + 384);
      if ( v24 )
      {
        v25 = _InterlockedDecrement(v24 + 6);
        if ( v25 )
        {
          if ( v25 < 0 )
            abort();
        }
        else
        {
          v26 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v26, 0, (LPVOID)v24);
        }
      }
      *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::`vftable';
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 48);
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 48);
      if ( *(_QWORD *)(a1 + 32) )
      {
        v27 = *(volatile signed __int32 **)(a1 + 32);
        if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v2 = v51;
      goto LABEL_95;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180043000  mov     r11, rsp
0x180043003  mov     [r11+10h], rbx
0x180043007  mov     [r11+18h], rsi
0x18004300b  mov     [r11+8], rcx
0x18004300f  push    rdi
0x180043010  push    r12
0x180043012  push    r13
0x180043014  push    r14
0x180043016  push    r15
0x180043018  sub     rsp, 190h
0x18004301f  mov     rax, cs:__security_cookie
0x180043026  xor     rax, rsp
0x180043029  mov     [rsp+1B8h+var_30], rax
0x180043031  mov     rsi, rcx
0x180043034  mov     [rsp+1B8h+var_158], rcx
0x180043039  lea     r14, [rsi+8]
0x18004303d  mov     [rsp+1B8h+var_160], r14
0x180043042  movzx   eax, word ptr [r14]
0x180043046  mov     [rsp+1B8h+var_180], ax
0x18004304b  mov     r12d, 1
0x180043051  add     ax, r12w
0x180043055  cmp     ax, 8; switch 9 cases
0x180043059  ja      def_18004307C; jumptable 000000018004307C default case, cases 1,5,6
0x18004305f  mov     [rsp+1B8h+var_138], r14
0x180043067  movsx   rax, ax
0x18004306b  lea     rdx, cs:180000000h
0x180043072  mov     ecx, ds:(jpt_18004307C - 180000000h)[rdx+rax*4]
0x180043079  add     rcx, rdx
0x18004307c  jmp     rcx; switch jump
0x18004307e  xor     edi, edi; jumptable 000000018004307C case 4
0x180043080  jmp     loc_180043845
0x180043085  xor     edi, edi; jumptable 000000018004307C case 3
0x180043087  mov     [rsi+240h], edi
0x18004308d  lea     rdx, [rsi+10h]
0x180043091  mov     [rdx], rdi
0x180043094  lea     rax, [rdx+2D0h]
0x18004309b  mov     [rsp+1B8h+var_150], rax
0x1800430a0  mov     rcx, rax
0x1800430a3  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800430a8  mov     rcx, [rsp+1B8h]; this
0x1800430b0  test    al, al
0x1800430b2  jz      short loc_1800430CA
0x1800430b4  mov     r9d, 80070057h; char *
0x1800430ba  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x1800430c1  lea     edx, [rdi+56h]; void *
0x1800430c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800430ca  mov     rbx, [r14+2D0h]
0x1800430d1  mov     [rsi+18h], rdi
0x1800430d5  mov     [rsi+20h], rdi
0x1800430d9  mov     rdx, [rbx+10h]
0x1800430dd  test    rdx, rdx
0x1800430e0  jz      loc_180043382
0x1800430e6  mov     eax, [rdx+8]
0x1800430e9  jmp     short loc_1800430F5
0x1800430eb  lea     ecx, [rax+1]
0x1800430ee  lock cmpxchg [rdx+8], ecx
0x1800430f3  jz      short loc_1800430FE
0x1800430f5  test    eax, eax
0x1800430f7  jnz     short loc_1800430EB
0x1800430f9  jmp     loc_180043382
0x1800430fe  mov     rax, [rbx+8]
0x180043102  mov     [rsi+18h], rax
0x180043106  mov     rax, [rbx+10h]
0x18004310a  mov     [rsi+20h], rax
0x18004310e  lea     rax, [rsi-70h]
0x180043112  mov     [rsi+230h], rax
0x180043119  mov     [rax+30h], r12b
0x18004311d  lea     r15, [rsi+30h]
0x180043121  lea     rdx, aTokenbrokerhan; "TokenBrokerHandler_GetTokenAsync"
0x180043128  mov     rcx, r15
0x18004312b  call    ??0?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180043130  lea     rax, ??_7TokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::`vftable'
0x180043137  mov     [r15], rax
0x18004313a  mov     rcx, r15; this
0x18004313d  call    ?StartActivity@TokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ; Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::StartActivity(void)
0x180043142  nop
0x180043143  lea     rcx, [rsi+180h]
0x18004314a  mov     [rcx], rdi
0x18004314d  lea     r15, [rsi+188h]
0x180043154  mov     [r15], rdi
0x180043157  lea     rdx, [rsi+190h]
0x18004315e  mov     [rdx], rdi
0x180043161  mov     [rsi+198h], rdi
0x180043168  mov     rax, [rsi+2F0h]
0x18004316f  test    rax, rax
0x180043172  jz      short loc_180043179
0x180043174  lock add [rax+8], r12d
0x180043179  mov     rax, [rsi+2E8h]
0x180043180  mov     [rdx], rax
0x180043183  mov     rax, [rsi+2F0h]
0x18004318a  mov     [rsi+198h], rax
0x180043191  mov     r9, r15
0x180043194  mov     r8, rcx
0x180043197  mov     rcx, rbx
0x18004319a  call    ?GetScopeAndClientId@TokenBrokerHandler@CloudRequestor@Internal@Windows@@AEAAJV?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@AEAUhstring@winrt@@1@Z; Windows::Internal::CloudRequestor::TokenBrokerHandler::GetScopeAndClientId(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::hstring &,winrt::hstring &)
0x18004319f  mov     rcx, [rsp+1B8h]; this
0x1800431a7  test    eax, eax
0x1800431a9  jns     short loc_1800431BF
0x1800431ab  mov     r9d, eax; char *
0x1800431ae  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x1800431b5  mov     edx, 63h ; 'c'; void *
0x1800431ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800431bf  mov     rax, [rbx+38h]
0x1800431c3  mov     [rsp+1B8h+var_148], rax
0x1800431c8  mov     rax, [rax]
0x1800431cb  mov     [rsp+1B8h+var_178], rax
0x1800431d0  lea     r13, [rsi+1A0h]
0x1800431d7  mov     [rsi+1A8h], r13
0x1800431de  mov     rbx, [r15]
0x1800431e1  mov     [rsp+1B8h+var_170], rbx
0x1800431e6  test    rbx, rbx
0x1800431e9  jnz     short loc_1800431F0
0x1800431eb  mov     rbx, rdi
0x1800431ee  jmp     short loc_180043228
0x1800431f0  test    [rbx], r12d
0x1800431f3  jnz     short loc_1800431FB
0x1800431f5  lock inc dword ptr [rbx+18h]
0x1800431f9  jmp     short loc_180043228
0x1800431fb  mov     r15d, [rbx+4]
0x1800431ff  test    r15d, r15d
0x180043202  jz      short loc_1800431EB
0x180043204  mov     r12, [rbx+10h]
0x180043208  mov     ecx, r15d; this
0x18004320b  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180043210  mov     rbx, rax
0x180043213  mov     edx, r15d
0x180043216  add     rdx, rdx; DestinationSize
0x180043219  lea     rcx, [rax+1Ch]; Destination
0x18004321d  mov     r9, rdx; SourceSize
0x180043220  mov     r8, r12; Source
0x180043223  call    memcpy_s
0x180043228  mov     [r13+0], rbx
0x18004322c  lea     r12, [rsi+1B0h]
0x180043233  mov     rbx, [rsi+180h]
0x18004323a  mov     [rsp+1B8h+var_168], rbx
0x18004323f  test    rbx, rbx
0x180043242  jnz     short loc_180043249
0x180043244  mov     rbx, rdi
0x180043247  jmp     short loc_18004328B
0x180043249  test    dword ptr [rbx], 1
0x18004324f  jnz     short loc_180043257
0x180043251  lock inc dword ptr [rbx+18h]
0x180043255  jmp     short loc_18004328B
0x180043257  mov     r15d, [rbx+4]
0x18004325b  test    r15d, r15d
0x18004325e  jz      short loc_180043244
0x180043260  mov     rax, [rbx+10h]
0x180043264  mov     [rsp+1B8h+Source], rax
0x180043269  mov     ecx, r15d; this
0x18004326c  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180043271  mov     rbx, rax
0x180043274  mov     edx, r15d
0x180043277  add     rdx, rdx; DestinationSize
0x18004327a  lea     rcx, [rax+1Ch]; Destination
0x18004327e  mov     r9, rdx; SourceSize
0x180043281  mov     r8, [rsp+1B8h+Source]; Source
0x180043286  call    memcpy_s
0x18004328b  mov     [r12], rbx
0x18004328f  lea     rbx, [rsi+1B8h]
0x180043296  mov     rcx, [rsp+1B8h+var_150]
0x18004329b  mov     rcx, [rcx]
0x18004329e  mov     [rbx], rcx
0x1800432a1  test    rcx, rcx
0x1800432a4  jz      short loc_1800432B2
0x1800432a6  mov     rax, [rcx]
0x1800432a9  mov     rax, [rax+8]
0x1800432ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432b2  lea     rdx, [rsi+1C0h]
0x1800432b9  mov     qword ptr [rsp+1B8h+var_198], r13
0x1800432be  mov     r9, r12
0x1800432c1  mov     r8, rbx
0x1800432c4  mov     rcx, [rsp+1B8h+var_148]
0x1800432c9  mov     rax, [rsp+1B8h+var_178]
0x1800432ce  mov     rax, [rax+8]
0x1800432d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432d7  nop
0x1800432d8  lea     rcx, [rsi+1C8h]
0x1800432df  lea     rdx, [rsi+30h]
0x1800432e3  mov     [rcx], rdx
0x1800432e6  mov     [rsi+1D0h], rdi
0x1800432ed  mov     [rsi+1D8h], rax
0x1800432f4  mov     [rsi+1E0h], rdi
0x1800432fb  mov     r12d, 1
0x180043301  mov     [rsi+1E8h], r12b
0x180043308  mov     [rsi+1F0h], dil
0x18004330f  xor     eax, eax
0x180043311  mov     [rsi+1F1h], eax
0x180043317  mov     [rsi+1F5h], ax
0x18004331e  mov     [rsi+1F7h], al
0x180043324  mov     eax, [rsi-10h]
0x180043327  nop
0x180043328  cmp     eax, 2
0x18004332b  jnz     short loc_18004335D
0x18004332d  lea     rcx, [rsi+248h]
0x180043334  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180043339  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18004333c  lea     rcx, [rsp+1B8h+pExceptionObject]; this
0x180043344  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180043349  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180043350  lea     rcx, [rsp+1B8h+pExceptionObject]; pExceptionObject
0x180043358  call    _CxxThrowException_0
0x18004335d  lea     rdx, [rsi+1F8h]
0x180043364  mov     [rdx], rsi
0x180043367  mov     eax, 6
0x18004336c  mov     [r14], ax
0x180043370  call    ??$await_suspend@U?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@@experimental@std@@@?$coroutine_withsuspend_awaiter@VTokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@U?$await_adapter@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@coro@details@wil@@QEAA?A_P$$QEAU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@@experimental@std@@@Z
0x180043375  test    al, al
0x180043377  jz      loc_1800434CB
0x18004337d  jmp     loc_180043871
0x180043382  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x180043388  mov     rbx, [rsi+1D0h]; jumptable 000000018004307C case 8
0x18004338f  mov     [rsp+1B8h+var_118], rbx
0x180043397  xor     edi, edi
0x180043399  test    rbx, rbx
0x18004339c  jz      short loc_1800433B1
0x18004339e  jmp     short loc_1800433A6
0x1800433a0  call    cs:__imp__Thrd_yield
0x1800433a6  mov     rax, rdi
0x1800433a9  xchg    rax, [rbx]
0x1800433ac  cmp     rax, r12
0x1800433af  jz      short loc_1800433A0
0x1800433b1  lea     rcx, [rsi+1C0h]
0x1800433b8  mov     rax, [rcx]
0x1800433bb  mov     [rsp+1B8h+var_140], rax
0x1800433c0  test    rax, rax
0x1800433c3  jz      short loc_1800433CB
0x1800433c5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800433ca  nop
0x1800433cb  mov     rbx, [rsi+188h]
0x1800433d2  mov     [rsp+1B8h+var_170], rbx
0x1800433d7  or      r14d, 0FFFFFFFFh
0x1800433db  test    rbx, rbx
0x1800433de  jz      short loc_18004340D
0x1800433e0  mov     eax, r14d
0x1800433e3  lock xadd [rbx+18h], eax
0x1800433e8  sub     eax, 1
0x1800433eb  jnz     short loc_180043402
0x1800433ed  nop
0x1800433ee  call    WINRT_IMPL_GetProcessHeap
0x1800433f3  mov     rcx, rax; hHeap
0x1800433f6  mov     r8, rbx; lpMem
0x1800433f9  xor     edx, edx; dwFlags
0x1800433fb  call    WINRT_IMPL_HeapFree
0x180043400  jmp     short loc_18004340D
0x180043402  test    eax, eax
0x180043404  jns     short loc_18004340D
0x180043406  call    cs:__imp_abort
0x18004340d  mov     rbx, [rsi+180h]
0x180043414  mov     [rsp+1B8h+var_168], rbx
0x180043419  test    rbx, rbx
0x18004341c  jz      short loc_18004344B
0x18004341e  mov     eax, r14d
0x180043421  lock xadd [rbx+18h], eax
0x180043426  sub     eax, 1
0x180043429  jnz     short loc_180043440
0x18004342b  nop
0x18004342c  call    WINRT_IMPL_GetProcessHeap
0x180043431  mov     rcx, rax; hHeap
0x180043434  mov     r8, rbx; lpMem
0x180043437  xor     edx, edx; dwFlags
0x180043439  call    WINRT_IMPL_HeapFree
0x18004343e  jmp     short loc_18004344B
0x180043440  test    eax, eax
0x180043442  jns     short loc_18004344B
0x180043444  call    cs:__imp_abort
0x18004344b  lea     rbx, [rsi+30h]
0x18004344f  lea     rax, ??_7TokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync::`vftable'
0x180043456  mov     [rbx], rax
0x180043459  mov     rcx, rbx
0x18004345c  call    ?Destroy@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180043461  mov     rcx, rbx
0x180043464  call    ??1?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180043469  nop
0x18004346a  mov     rax, [rsi+20h]
0x18004346e  mov     [rsp+1B8h+var_128], rax
0x180043476  test    rax, rax
0x180043479  jz      short loc_1800434BF
0x18004347b  mov     rbx, [rsi+20h]
0x18004347f  mov     [rsp+1B8h+var_128], rbx
0x180043487  mov     eax, r14d
0x18004348a  lock xadd [rbx+8], eax
0x18004348f  add     eax, r14d
0x180043492  jnz     short loc_1800434BF
0x180043494  mov     rax, [rbx]
0x180043497  mov     rcx, rbx
0x18004349a  mov     rax, [rax]
0x18004349d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434a2  mov     eax, r14d
0x1800434a5  lock xadd [rbx+0Ch], eax
0x1800434aa  add     eax, r14d
0x1800434ad  jnz     short loc_1800434BF
0x1800434af  mov     rax, [rbx]
0x1800434b2  mov     rcx, rbx
0x1800434b5  mov     rax, [rax+8]
0x1800434b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800434be  nop
0x1800434bf  mov     r14, [rsp+1B8h+var_160]
0x1800434c4  jmp     loc_180043845
0x1800434c9  xor     edi, edi; jumptable 000000018004307C case 7
0x1800434cb  mov     al, [rsi+1F0h]
  ... truncated ...
```
