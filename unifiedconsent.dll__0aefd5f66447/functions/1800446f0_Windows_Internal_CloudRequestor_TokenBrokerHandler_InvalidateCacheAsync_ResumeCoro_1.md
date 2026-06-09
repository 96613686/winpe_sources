# Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync$_ResumeCoro$1

- ea: `0x1800446f0`
- end: `0x1800453d0`
- name: `Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync$_ResumeCoro$1`
- size: `3296`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045780`

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
- `0x180013f6c`
- `0x180016498`
- `0x18001c1d4`
- `0x18001cb64`
- `0x18002d81c`
- `0x18002d994`
- `0x180038b50`
- `0x18003f0c0`
- `0x18003f128`
- `0x180040150`
- `0x180040404`
- `0x180040520`
- `0x1800412f0`
- `0x180042aec`
- `0x1800446f0`
- `0x180045aa8`
- `0x180046a00`
- `0x180046fb8`
- `0x180047128`
- `0x1800486cc`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180045344`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180045344`
- `msvcp_win!_Thrd_yield` at `0x180044b0c`
- `msvcp_win!_Thrd_yield` at `0x180044cff`
- `msvcp_win!_Thrd_yield` at `0x180044e49`
- `msvcp_win!_Thrd_yield` at `0x180044fd1`
- `msvcp_win!_Thrd_yield` at `0x180044b0c`
- `msvcp_win!_Thrd_yield` at `0x180044cff`
- `msvcp_win!_Thrd_yield` at `0x180044e49`
- `msvcp_win!_Thrd_yield` at `0x180044fd1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044b75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044bb3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044ec9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044f07`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451f1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044b75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044bb3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044ec9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044f07`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451f1`

## string_xrefs

- `0x180044829`: `TokenBrokerHandler_InvalidateCacheAsync`
- `0x1800447a3`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x1800447cc`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`
- `0x180044900`: `onecoreuap\shell\clouddirect\cloudrequestor\src\tokenbrokerhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync__ResumeCoro_1(__int64 a1)
{
  __int64 v2; // r13
  _QWORD *v3; // rbx
  __int64 v4; // rdx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  __int64 v7; // rax
  struct winrt::impl::shared_hstring_header **v8; // r14
  _QWORD *v9; // rdx
  __int64 v10; // rax
  int ScopeAndClientId; // eax
  unsigned int v12; // edx
  struct winrt::impl::shared_hstring_header **v13; // rax
  struct winrt::impl::shared_hstring_header *v14; // rbx
  unsigned int v15; // r14d
  const void *v16; // r12
  struct winrt::impl::shared_hstring_header *v17; // rbx
  unsigned int v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // rax
  const struct winrt::impl::slim_source_location *v21; // rax
  volatile __int64 *v22; // rbx
  volatile signed __int32 *v23; // rbx
  int v24; // eax
  HANDLE v25; // rax
  volatile signed __int32 *v26; // rbx
  int v27; // eax
  HANDLE v28; // rax
  volatile signed __int32 *v29; // rbx
  __int64 v30; // rcx
  const struct winrt::impl::slim_source_location *v31; // rax
  __int64 *v32; // r14
  volatile __int64 *v33; // rbx
  __int64 v34; // r12
  __int64 (__fastcall *v35)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  const struct winrt::impl::slim_source_location *v38; // rax
  volatile __int64 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  int v41; // eax
  HANDLE v42; // rax
  volatile signed __int32 *v43; // rbx
  int v44; // eax
  HANDLE v45; // rax
  volatile __int64 *v46; // rbx
  __int64 v47; // rax
  volatile signed __int32 *v48; // rbx
  int v49; // eax
  HANDLE v50; // rax
  volatile signed __int32 *v51; // rbx
  int v52; // eax
  HANDLE v53; // rax
  volatile signed __int32 *v54; // rbx
  volatile signed __int32 *v55; // rbx
  int v56; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v58; // rbx
  int v59; // eax
  HANDLE v60; // rax
  int v61; // [rsp+20h] [rbp-1B8h]
  __int64 *v62; // [rsp+48h] [rbp-190h]
  __int64 v63; // [rsp+50h] [rbp-188h]
  __int64 (__fastcall *v64)(_QWORD, _QWORD, _QWORD); // [rsp+50h] [rbp-188h]
  void *Source; // [rsp+78h] [rbp-160h]
  __int64 *v66; // [rsp+90h] [rbp-148h]
  _BYTE pExceptionObject[24]; // [rsp+C8h] [rbp-110h] BYREF
  _BYTE v68[24]; // [rsp+E0h] [rbp-F8h] BYREF
  _BYTE v69[24]; // [rsp+F8h] [rbp-E0h] BYREF
  __int64 v70; // [rsp+110h] [rbp-C8h]
  volatile __int64 *v71; // [rsp+118h] [rbp-C0h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_139;
    case 2:
      *(_QWORD *)(a1 + 16) = 0;
      v66 = (__int64 *)(a1 + 752);
      if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a1 + 752, a1 + 16) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)0x80070057LL,
          v61);
      if ( !*(_QWORD *)(a1 + 760) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)0x80070057LL,
          v61);
      v3 = *(_QWORD **)(v2 + 736);
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      v4 = v3[2];
      if ( !v4 )
        goto LABEL_36;
      v5 = *(_DWORD *)(v4 + 8);
      do
      {
        if ( !v5 )
LABEL_36:
          std::_Throw_bad_weak_ptr();
        v6 = v5;
        v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
      }
      while ( v6 != v5 );
      *(_QWORD *)(a1 + 24) = v3[1];
      *(_QWORD *)(a1 + 32) = v3[2];
      *(_BYTE *)(a1 - 64) = 1;
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        a1 + 48,
        "TokenBrokerHandler_InvalidateCacheAsync");
      *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable';
      Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::StartActivity((Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync *)(a1 + 48));
      *(_QWORD *)(a1 + 384) = 0;
      *(_QWORD *)(a1 + 392) = 0;
      v7 = *(_QWORD *)(a1 + 768);
      if ( v7 )
        _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
      *(_QWORD *)(a1 + 384) = *(_QWORD *)(a1 + 760);
      *(_QWORD *)(a1 + 392) = *(_QWORD *)(a1 + 768);
      if ( !(unsigned __int8)Windows::Internal::CloudRequestor::TokenBrokerHandler::IsCoolingPeriodExpired(v3) )
        goto LABEL_134;
      *(_QWORD *)(a1 + 400) = 0;
      v8 = (struct winrt::impl::shared_hstring_header **)(a1 + 408);
      *(_QWORD *)(a1 + 408) = 0;
      v9 = (_QWORD *)(a1 + 416);
      *(_QWORD *)(a1 + 416) = 0;
      *(_QWORD *)(a1 + 424) = 0;
      v10 = *(_QWORD *)(a1 + 768);
      if ( v10 )
        _InterlockedAdd((volatile signed __int32 *)(v10 + 8), 1u);
      *v9 = *(_QWORD *)(a1 + 760);
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 768);
      ScopeAndClientId = Windows::Internal::CloudRequestor::TokenBrokerHandler::GetScopeAndClientId(
                           v3,
                           v9,
                           a1 + 400,
                           a1 + 408);
      if ( ScopeAndClientId < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecoreuap\\shell\\clouddirect\\cloudrequestor\\src\\tokenbrokerhandler.cpp",
          (const char *)(unsigned int)ScopeAndClientId,
          v61);
      v62 = (__int64 *)v3[7];
      v63 = *v62;
      v13 = (struct winrt::impl::shared_hstring_header **)(a1 + 432);
      *(_QWORD *)(a1 + 440) = a1 + 432;
      v14 = *v8;
      if ( !*v8 )
        goto LABEL_19;
      if ( (*(_DWORD *)v14 & 1) != 0 )
      {
        v15 = *((_DWORD *)v14 + 1);
        if ( v15 )
        {
          v16 = (const void *)*((_QWORD *)v14 + 2);
          v14 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v15, v12);
          memcpy_s((char *)v14 + 28, 2LL * v15, v16, 2LL * v15);
          v13 = (struct winrt::impl::shared_hstring_header **)(a1 + 432);
        }
        else
        {
LABEL_19:
          v14 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v14 + 6);
      }
      *v13 = v14;
      v17 = *(struct winrt::impl::shared_hstring_header **)(a1 + 400);
      if ( !v17 )
        goto LABEL_25;
      if ( (*(_DWORD *)v17 & 1) != 0 )
      {
        v18 = *((_DWORD *)v17 + 1);
        if ( v18 )
        {
          Source = (void *)*((_QWORD *)v17 + 2);
          v17 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)v18, v12);
          memcpy_s((char *)v17 + 28, 2LL * v18, Source, 2LL * v18);
        }
        else
        {
LABEL_25:
          v17 = 0;
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v17 + 6);
      }
      *(_QWORD *)(a1 + 448) = v17;
      v19 = *v66;
      *(_QWORD *)(a1 + 456) = *v66;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64, __int64))(v63 + 8))(
              v62,
              a1 + 464,
              a1 + 456,
              a1 + 448,
              a1 + 432);
      *(_QWORD *)(a1 + 472) = a1 + 48;
      *(_QWORD *)(a1 + 480) = 0;
      *(_QWORD *)(a1 + 488) = v20;
      *(_QWORD *)(a1 + 496) = 0;
      *(_BYTE *)(a1 + 504) = 1;
      *(_BYTE *)(a1 + 512) = 0;
      *(_DWORD *)(a1 + 513) = 0;
      *(_WORD *)(a1 + 517) = 0;
      *(_BYTE *)(a1 + 519) = 0;
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v21 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 632);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v21);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 520) = a1;
      *(_WORD *)v2 = 6;
      if ( (unsigned __int8)wil::details::coro::coroutine_withsuspend_awaiter<Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_GetTokenAsync,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,1>>::await_suspend<std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type>>() )
        return;
LABEL_57:
      if ( *(_BYTE *)(a1 + 512) )
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::resume();
      *(_DWORD *)(a1 + 656) = 0;
      *(_QWORD *)(a1 + 664) = 0;
      *(_QWORD *)(a1 + 672) = 0;
      v30 = *(unsigned int *)(a1 + 500);
      if ( (int)v30 < 0 )
        winrt::throw_hresult(v30, a1 + 656);
      if ( *(_DWORD *)(a1 + 496) == 2 )
      {
        v31 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 680);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v68, v31);
        throw (winrt::hresult_canceled *)v68;
      }
      v32 = (__int64 *)(a1 + 528);
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::GetResults(
        *(_QWORD *)(a1 + 488),
        a1 + 528);
      v33 = *(volatile __int64 **)(a1 + 480);
      if ( v33 )
      {
        while ( _InterlockedExchange64(v33, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 464) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
      v34 = *(_QWORD *)(*(_QWORD *)(v2 + 736) + 56LL);
      v35 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v34 + 16LL);
      v64 = v35;
      v36 = *v32;
      *(_QWORD *)(a1 + 536) = *v32;
      if ( v36 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
        v35 = v64;
      }
      v37 = v35(v34, a1 + 544, a1 + 536);
      *(_QWORD *)(a1 + 552) = a1 + 48;
      *(_QWORD *)(a1 + 560) = 0;
      *(_QWORD *)(a1 + 568) = v37;
      *(_QWORD *)(a1 + 576) = 0;
      *(_BYTE *)(a1 + 584) = 1;
      *(_BYTE *)(a1 + 592) = 0;
      *(_DWORD *)(a1 + 593) = 0;
      *(_WORD *)(a1 + 597) = 0;
      *(_BYTE *)(a1 + 599) = 0;
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v38 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 704);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v69, v38);
        throw (winrt::hresult_canceled *)v69;
      }
      *(_QWORD *)(a1 + 600) = a1;
      *(_WORD *)v2 = 8;
      if ( (unsigned __int8)wil::details::coro::coroutine_withsuspend_awaiter<Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>>::await_suspend<std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type>>(a1 + 552) )
        return;
LABEL_97:
      if ( *(_BYTE *)(a1 + 592) )
      {
        v70 = *(_QWORD *)(a1 + 552);
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::resume();
      }
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(a1 + 560);
      v46 = *(volatile __int64 **)(a1 + 560);
      v71 = v46;
      if ( v46 )
      {
        while ( _InterlockedExchange64(v46, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 544) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 544);
      *(_QWORD *)(a1 + 608) = 0;
      *(_QWORD *)(a1 + 616) = 0;
      v47 = *(_QWORD *)(a1 + 768);
      if ( v47 )
        _InterlockedAdd((volatile signed __int32 *)(v47 + 8), 1u);
      *(_QWORD *)(a1 + 608) = *(_QWORD *)(a1 + 760);
      *(_QWORD *)(a1 + 616) = *(_QWORD *)(a1 + 768);
      if ( (int)Windows::Internal::CloudRequestor::TokenBrokerHandler::SetTokenRefreshTime(*(_QWORD *)(v2 + 736)) >= 0 )
      {
        if ( *(_QWORD *)(a1 + 528) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 528);
        v55 = *(volatile signed __int32 **)(a1 + 408);
        if ( v55 )
        {
          v56 = _InterlockedDecrement(v55 + 6);
          if ( v56 )
          {
            if ( v56 < 0 )
              goto LABEL_128;
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v55);
          }
        }
        v58 = *(volatile signed __int32 **)(a1 + 400);
        if ( v58 )
        {
          v59 = _InterlockedDecrement(v58 + 6);
          if ( v59 )
          {
            if ( v59 < 0 )
              goto LABEL_133;
          }
          else
          {
            v60 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v60, 0, (LPVOID)v58);
          }
        }
LABEL_134:
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          a1 + 48,
          0);
        *(_DWORD *)(a1 - 8) = 0;
        *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable';
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 48);
        wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 48);
        if ( *(_QWORD *)(a1 + 32) )
        {
          v54 = *(volatile signed __int32 **)(a1 + 32);
          if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
            if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_137;
          }
        }
        goto LABEL_138;
      }
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        a1 + 48,
        2147746566LL);
      *(_DWORD *)(a1 - 8) = -2147220730;
      if ( *(_QWORD *)(a1 + 528) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 528);
      v48 = *(volatile signed __int32 **)(a1 + 408);
      if ( v48 )
      {
        v49 = _InterlockedDecrement(v48 + 6);
        if ( !v49 )
        {
          v50 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v50, 0, (LPVOID)v48);
          goto LABEL_114;
        }
        if ( v49 < 0 )
LABEL_128:
          abort();
      }
LABEL_114:
      v51 = *(volatile signed __int32 **)(a1 + 400);
      if ( v51 )
      {
        v52 = _InterlockedDecrement(v51 + 6);
        if ( !v52 )
        {
          v53 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v53, 0, (LPVOID)v51);
          goto LABEL_118;
        }
        if ( v52 >= 0 )
          goto LABEL_118;
LABEL_133:
        abort();
      }
LABEL_118:
      *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable';
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 48);
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 48);
      if ( *(_QWORD *)(a1 + 32) )
      {
        v54 = *(volatile signed __int32 **)(a1 + 32);
        if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
LABEL_137:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
LABEL_138:
      *(_QWORD *)(a1 + 624) = a1 - 112;
      *(_WORD *)v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_139:
        if ( *(_QWORD *)(a1 - 24) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 24);
        if ( *(_QWORD *)(a1 - 32) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 - 32);
        __ExceptionPtrDestroy((void *)(a1 - 56));
        __1__root_implements_U__map_impl_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_V__unordered_map_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2_U__hash_Uhstring_winrt___std__U__equal_to_Uhstring_winrt___8_V__allocator_U__pair___CBUhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__std___8__std__Umulti_threaded_collection_base_impl_2__impl_winrt__U__IMap_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_3_U__IMapView_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__5673_U__IIterable_U__IKeyValuePair_Uhstring_winrt__U__IMap_Uhstring_winrt__UEnvironmentConfig_CloudRequestor_Internal_Windows_2__Collections_Foundation_Windows_2__Collections_Foundation_Windows_winrt___5673__impl_winrt__MEAA_XZ(a1 - 112);
        Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync_::_11_::_parameters_::__parameters_(v2 + 736);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 112), 0x380u);
      }
      return;
    case 6:
      goto LABEL_57;
    case 7:
      v22 = *(volatile __int64 **)(a1 + 480);
      if ( v22 )
      {
        while ( _InterlockedExchange64(v22, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 464) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
      v23 = *(volatile signed __int32 **)(a1 + 408);
      if ( v23 )
      {
        v24 = _InterlockedDecrement(v23 + 6);
        if ( v24 )
        {
          if ( v24 < 0 )
            abort();
        }
        else
        {
          v25 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v25, 0, (LPVOID)v23);
        }
      }
      v26 = *(volatile signed __int32 **)(a1 + 400);
      if ( v26 )
      {
        v27 = _InterlockedDecrement(v26 + 6);
        if ( v27 )
        {
          if ( v27 < 0 )
            abort();
        }
        else
        {
          v28 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v28, 0, (LPVOID)v26);
        }
      }
      *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable';
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 48);
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 48);
      if ( *(_QWORD *)(a1 + 32) )
      {
        v29 = *(volatile signed __int32 **)(a1 + 32);
        if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            goto LABEL_56;
        }
      }
      goto LABEL_139;
    case 8:
      goto LABEL_97;
    case 9:
      v39 = *(volatile __int64 **)(a1 + 560);
      v71 = v39;
      if ( v39 )
      {
        while ( _InterlockedExchange64(v39, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 544) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 544);
      if ( *(_QWORD *)(a1 + 528) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 528);
      v40 = *(volatile signed __int32 **)(a1 + 408);
      if ( v40 )
      {
        v41 = _InterlockedDecrement(v40 + 6);
        if ( v41 )
        {
          if ( v41 < 0 )
            abort();
        }
        else
        {
          v42 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v42, 0, (LPVOID)v40);
        }
      }
      v43 = *(volatile signed __int32 **)(a1 + 400);
      if ( v43 )
      {
        v44 = _InterlockedDecrement(v43 + 6);
        if ( v44 )
        {
          if ( v44 < 0 )
            abort();
        }
        else
        {
          v45 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v45, 0, (LPVOID)v43);
        }
      }
      *(_QWORD *)(a1 + 48) = &Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable';
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(a1 + 48);
      wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(a1 + 48);
      if ( *(_QWORD *)(a1 + 32) )
      {
        v29 = *(volatile signed __int32 **)(a1 + 32);
        if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
LABEL_56:
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      goto LABEL_139;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x1800446f0  mov     r11, rsp
0x1800446f3  mov     [r11+10h], rbx
0x1800446f7  mov     [r11+18h], rsi
0x1800446fb  mov     [r11+8], rcx
0x1800446ff  push    rdi
0x180044700  push    r12
0x180044702  push    r13
0x180044704  push    r14
0x180044706  push    r15
0x180044708  sub     rsp, 1B0h
0x18004470f  mov     rax, cs:__security_cookie
0x180044716  xor     rax, rsp
0x180044719  mov     [rsp+1D8h+var_38], rax
0x180044721  mov     rsi, rcx
0x180044724  mov     [rsp+1D8h+var_198], rcx
0x180044729  lea     r13, [rsi+8]
0x18004472d  movzx   eax, word ptr [r13+0]
0x180044732  mov     [rsp+1D8h+var_170], ax
0x180044737  mov     r12d, 1
0x18004473d  add     ax, r12w
0x180044741  cmp     ax, 0Ah; switch 11 cases
0x180044745  ja      def_180044768; jumptable 0000000180044768 default case, cases 1,5,6
0x18004474b  mov     [rsp+1D8h+var_150], r13
0x180044753  movsx   rax, ax
0x180044757  lea     rdx, cs:180000000h
0x18004475e  mov     ecx, ds:(jpt_180044768 - 180000000h)[rdx+rax*4]
0x180044765  add     rcx, rdx
0x180044768  jmp     rcx; switch jump
0x18004476a  xor     edi, edi; jumptable 0000000180044768 case 4
0x18004476c  jmp     loc_180045324
0x180044771  xor     edi, edi; jumptable 0000000180044768 case 3
0x180044773  lea     rdx, [rsi+10h]
0x180044777  mov     [rdx], rdi
0x18004477a  lea     rax, [rdx+2E0h]
0x180044781  mov     [rsp+1D8h+var_148], rax
0x180044789  mov     rcx, rax
0x18004478c  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180044791  mov     rcx, [rsp+1D8h]; this
0x180044799  test    al, al
0x18004479b  jz      short loc_1800447B5
0x18004479d  mov     r9d, 80070057h; char *
0x1800447a3  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x1800447aa  mov     edx, 0CCh; void *
0x1800447af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800447b5  mov     rcx, [rsp+1D8h]; this
0x1800447bd  cmp     [rsi+2F8h], rdi
0x1800447c4  jnz     short loc_1800447DD
0x1800447c6  mov     r9d, 80070057h; char *
0x1800447cc  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x1800447d3  mov     edx, 0CDh; void *
0x1800447d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800447dd  mov     rbx, [r13+2E0h]
0x1800447e4  mov     [rsi+18h], rdi
0x1800447e8  mov     [rsi+20h], rdi
0x1800447ec  mov     rdx, [rbx+10h]
0x1800447f0  test    rdx, rdx
0x1800447f3  jz      loc_180044AEE
0x1800447f9  mov     eax, [rdx+8]
0x1800447fc  jmp     short loc_180044808
0x1800447fe  lea     ecx, [rax+1]
0x180044801  lock cmpxchg [rdx+8], ecx
0x180044806  jz      short loc_180044811
0x180044808  test    eax, eax
0x18004480a  jnz     short loc_1800447FE
0x18004480c  jmp     loc_180044AEE
0x180044811  mov     rax, [rbx+8]
0x180044815  mov     [rsi+18h], rax
0x180044819  mov     rax, [rbx+10h]
0x18004481d  mov     [rsi+20h], rax
0x180044821  mov     [rsi-40h], r12b
0x180044825  lea     r14, [rsi+30h]
0x180044829  lea     rdx, aTokenbrokerhan_0; "TokenBrokerHandler_InvalidateCacheAsync"
0x180044830  mov     rcx, r14
0x180044833  call    ??0?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180044838  lea     r15, ??_7TokenBrokerHandler_InvalidateCacheAsync@InternalLogger@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable'
0x18004483f  mov     [r14], r15
0x180044842  mov     rcx, r14; this
0x180044845  call    ?StartActivity@TokenBrokerHandler_InvalidateCacheAsync@InternalLogger@CloudRequestor@Internal@Windows@@QEAAXXZ; Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::StartActivity(void)
0x18004484a  nop
0x18004484b  lea     rdx, [rsi+180h]
0x180044852  mov     [rdx], rdi
0x180044855  mov     [rsi+188h], rdi
0x18004485c  mov     rax, [rsi+300h]
0x180044863  test    rax, rax
0x180044866  jz      short loc_18004486D
0x180044868  lock add [rax+8], r12d
0x18004486d  mov     rax, [rsi+2F8h]
0x180044874  mov     [rdx], rax
0x180044877  mov     rax, [rsi+300h]
0x18004487e  mov     [rsi+188h], rax
0x180044885  mov     rcx, rbx
0x180044888  call    ?IsCoolingPeriodExpired@TokenBrokerHandler@CloudRequestor@Internal@Windows@@AEAA_NV?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@Z; Windows::Internal::CloudRequestor::TokenBrokerHandler::IsCoolingPeriodExpired(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)
0x18004488d  test    al, al
0x18004488f  jz      loc_180044AE5
0x180044895  lea     rcx, [rsi+190h]
0x18004489c  mov     [rcx], rdi
0x18004489f  lea     r14, [rsi+198h]
0x1800448a6  mov     [r14], rdi
0x1800448a9  lea     rdx, [rsi+1A0h]
0x1800448b0  mov     [rdx], rdi
0x1800448b3  mov     [rsi+1A8h], rdi
0x1800448ba  mov     rax, [rsi+300h]
0x1800448c1  test    rax, rax
0x1800448c4  jz      short loc_1800448CB
0x1800448c6  lock add [rax+8], r12d
0x1800448cb  mov     rax, [rsi+2F8h]
0x1800448d2  mov     [rdx], rax
0x1800448d5  mov     rax, [rsi+300h]
0x1800448dc  mov     [rsi+1A8h], rax
0x1800448e3  mov     r9, r14
0x1800448e6  mov     r8, rcx
0x1800448e9  mov     rcx, rbx
0x1800448ec  call    ?GetScopeAndClientId@TokenBrokerHandler@CloudRequestor@Internal@Windows@@AEAAJV?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@AEAUhstring@winrt@@1@Z; Windows::Internal::CloudRequestor::TokenBrokerHandler::GetScopeAndClientId(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::hstring &,winrt::hstring &)
0x1800448f1  mov     rcx, [rsp+1D8h]; this
0x1800448f9  test    eax, eax
0x1800448fb  jns     short loc_180044911
0x1800448fd  mov     r9d, eax; char *
0x180044900  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\clouddirect\\cloudre"...
0x180044907  mov     edx, 0DEh; void *
0x18004490c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044911  mov     rax, [rbx+38h]
0x180044915  mov     [rsp+1D8h+var_190], rax
0x18004491a  mov     rax, [rax]
0x18004491d  mov     [rsp+1D8h+var_188], rax
0x180044922  lea     rax, [rsi+1B0h]
0x180044929  mov     [rsi+1B8h], rax
0x180044930  mov     rbx, [r14]
0x180044933  mov     [rsp+1D8h+var_1A8], rbx
0x180044938  test    rbx, rbx
0x18004493b  jnz     short loc_180044942
0x18004493d  mov     rbx, rdi
0x180044940  jmp     short loc_180044981
0x180044942  test    [rbx], r12d
0x180044945  jnz     short loc_18004494D
0x180044947  lock inc dword ptr [rbx+18h]
0x18004494b  jmp     short loc_180044981
0x18004494d  mov     r14d, [rbx+4]
0x180044951  test    r14d, r14d
0x180044954  jz      short loc_18004493D
0x180044956  mov     r12, [rbx+10h]
0x18004495a  mov     ecx, r14d; this
0x18004495d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180044962  mov     rbx, rax
0x180044965  mov     edx, r14d
0x180044968  add     rdx, rdx; DestinationSize
0x18004496b  lea     rcx, [rax+1Ch]; Destination
0x18004496f  mov     r9, rdx; SourceSize
0x180044972  mov     r8, r12; Source
0x180044975  call    memcpy_s
0x18004497a  lea     rax, [rsi+1B0h]
0x180044981  mov     [rax], rbx
0x180044984  lea     r12, [rsi+1C0h]
0x18004498b  mov     rbx, [rsi+190h]
0x180044992  mov     [rsp+1D8h+var_1A0], rbx
0x180044997  test    rbx, rbx
0x18004499a  jnz     short loc_1800449A1
0x18004499c  mov     rbx, rdi
0x18004499f  jmp     short loc_1800449E3
0x1800449a1  test    dword ptr [rbx], 1
0x1800449a7  jnz     short loc_1800449AF
0x1800449a9  lock inc dword ptr [rbx+18h]
0x1800449ad  jmp     short loc_1800449E3
0x1800449af  mov     r14d, [rbx+4]
0x1800449b3  test    r14d, r14d
0x1800449b6  jz      short loc_18004499C
0x1800449b8  mov     rax, [rbx+10h]
0x1800449bc  mov     [rsp+1D8h+Source], rax
0x1800449c1  mov     ecx, r14d; this
0x1800449c4  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800449c9  mov     rbx, rax
0x1800449cc  mov     edx, r14d
0x1800449cf  add     rdx, rdx; DestinationSize
0x1800449d2  lea     rcx, [rax+1Ch]; Destination
0x1800449d6  mov     r9, rdx; SourceSize
0x1800449d9  mov     r8, [rsp+1D8h+Source]; Source
0x1800449de  call    memcpy_s
0x1800449e3  mov     [r12], rbx
0x1800449e7  lea     rbx, [rsi+1C8h]
0x1800449ee  mov     rcx, [rsp+1D8h+var_148]
0x1800449f6  mov     rcx, [rcx]
0x1800449f9  mov     [rbx], rcx
0x1800449fc  test    rcx, rcx
0x1800449ff  jz      short loc_180044A0D
0x180044a01  mov     rax, [rcx]
0x180044a04  mov     rax, [rax+8]
0x180044a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a0d  lea     rdx, [rsi+1D0h]
0x180044a14  lea     r8, [rsi+1B0h]
0x180044a1b  mov     qword ptr [rsp+1D8h+var_1B8], r8
0x180044a20  mov     r9, r12
0x180044a23  mov     r8, rbx
0x180044a26  mov     rcx, [rsp+1D8h+var_190]
0x180044a2b  mov     rax, [rsp+1D8h+var_188]
0x180044a30  mov     rax, [rax+8]
0x180044a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a39  nop
0x180044a3a  lea     rcx, [rsi+1D8h]
0x180044a41  lea     rdx, [rsi+30h]
0x180044a45  mov     [rcx], rdx
0x180044a48  mov     [rsi+1E0h], rdi
0x180044a4f  mov     [rsi+1E8h], rax
0x180044a56  mov     [rsi+1F0h], rdi
0x180044a5d  mov     r12d, 1
0x180044a63  mov     [rsi+1F8h], r12b
0x180044a6a  mov     [rsi+200h], dil
0x180044a71  xor     eax, eax
0x180044a73  mov     [rsi+201h], eax
0x180044a79  mov     [rsi+205h], ax
0x180044a80  mov     [rsi+207h], al
0x180044a86  mov     eax, [rsi-10h]
0x180044a89  nop
0x180044a8a  cmp     eax, 2
0x180044a8d  jnz     short loc_180044ABF
0x180044a8f  lea     rcx, [rsi+278h]
0x180044a96  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180044a9b  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180044a9e  lea     rcx, [rsp+1D8h+pExceptionObject]; this
0x180044aa6  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180044aab  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180044ab2  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x180044aba  call    _CxxThrowException_0
0x180044abf  lea     rdx, [rsi+208h]
0x180044ac6  mov     [rdx], rsi
0x180044ac9  mov     eax, 6
0x180044ace  mov     [r13+0], ax
0x180044ad3  call    ??$await_suspend@U?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@@experimental@std@@@?$coroutine_withsuspend_awaiter@VTokenBrokerHandler_GetTokenAsync@InternalLogger@CloudRequestor@Internal@Windows@@U?$await_adapter@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@coro@details@wil@@QEAA?A_P$$QEAU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@@experimental@std@@@Z
0x180044ad8  test    al, al
0x180044ada  jz      loc_180044C36
0x180044ae0  jmp     loc_180045376
0x180044ae5  or      r14d, 0FFFFFFFFh
0x180044ae9  jmp     loc_1800451F8
0x180044aee  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x180044af4  mov     rbx, [rsi+1E0h]; jumptable 0000000180044768 case 8
0x180044afb  mov     [rsp+1D8h+var_138], rbx
0x180044b03  xor     edi, edi
0x180044b05  test    rbx, rbx
0x180044b08  jz      short loc_180044B1D
0x180044b0a  jmp     short loc_180044B12
0x180044b0c  call    cs:__imp__Thrd_yield
0x180044b12  mov     rax, rdi
0x180044b15  xchg    rax, [rbx]
0x180044b18  cmp     rax, r12
0x180044b1b  jz      short loc_180044B0C
0x180044b1d  lea     rcx, [rsi+1D0h]
0x180044b24  mov     rax, [rcx]
0x180044b27  mov     [rsp+1D8h+var_158], rax
0x180044b2f  test    rax, rax
0x180044b32  jz      short loc_180044B3A
0x180044b34  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180044b39  nop
0x180044b3a  mov     rbx, [rsi+198h]
0x180044b41  mov     [rsp+1D8h+var_1A8], rbx
0x180044b46  or      r14d, 0FFFFFFFFh
0x180044b4a  test    rbx, rbx
0x180044b4d  jz      short loc_180044B7C
0x180044b4f  mov     eax, r14d
0x180044b52  lock xadd [rbx+18h], eax
0x180044b57  sub     eax, 1
0x180044b5a  jnz     short loc_180044B71
0x180044b5c  nop
0x180044b5d  call    WINRT_IMPL_GetProcessHeap
0x180044b62  mov     rcx, rax; hHeap
0x180044b65  mov     r8, rbx; lpMem
0x180044b68  xor     edx, edx; dwFlags
0x180044b6a  call    WINRT_IMPL_HeapFree
0x180044b6f  jmp     short loc_180044B7C
0x180044b71  test    eax, eax
0x180044b73  jns     short loc_180044B7C
0x180044b75  call    cs:__imp_abort
0x180044b7c  mov     rbx, [rsi+190h]
0x180044b83  mov     [rsp+1D8h+var_1A0], rbx
0x180044b88  test    rbx, rbx
0x180044b8b  jz      short loc_180044BBA
0x180044b8d  mov     eax, r14d
0x180044b90  lock xadd [rbx+18h], eax
0x180044b95  sub     eax, 1
0x180044b98  jnz     short loc_180044BAF
0x180044b9a  nop
0x180044b9b  call    WINRT_IMPL_GetProcessHeap
0x180044ba0  mov     rcx, rax; hHeap
0x180044ba3  mov     r8, rbx; lpMem
0x180044ba6  xor     edx, edx; dwFlags
0x180044ba8  call    WINRT_IMPL_HeapFree
0x180044bad  jmp     short loc_180044BBA
0x180044baf  test    eax, eax
0x180044bb1  jns     short loc_180044BBA
0x180044bb3  call    cs:__imp_abort
0x180044bba  lea     rbx, [rsi+30h]
0x180044bbe  lea     r15, ??_7TokenBrokerHandler_InvalidateCacheAsync@InternalLogger@CloudRequestor@Internal@Windows@@6B@; const Windows::Internal::CloudRequestor::InternalLogger::TokenBrokerHandler_InvalidateCacheAsync::`vftable'
0x180044bc5  mov     [rbx], r15
0x180044bc8  mov     rcx, rbx
0x180044bcb  call    ?Destroy@?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180044bd0  mov     rcx, rbx
0x180044bd3  call    ??1?$ActivityBase@VInternalLogger@CloudRequestor@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::CloudRequestor::InternalLogger,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180044bd8  nop
0x180044bd9  mov     rax, [rsi+20h]
0x180044bdd  mov     [rsp+1D8h+var_178], rax
0x180044be2  test    rax, rax
0x180044be5  jz      short loc_180044C28
0x180044be7  mov     rbx, [rsi+20h]
  ... truncated ...
```
