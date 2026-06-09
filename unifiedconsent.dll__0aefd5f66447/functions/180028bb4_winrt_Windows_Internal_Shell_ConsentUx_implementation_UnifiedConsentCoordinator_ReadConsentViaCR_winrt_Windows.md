# winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::ReadConsentViaCR(winrt::Windows::Security::Credentials::WebAccount,bool &)

- ea: `0x180028bb4`
- end: `0x1800290ec`
- name: `?ReadConsentViaCR@UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@AEAA?AUhstring@7@UWebAccount@Credentials@Security@67@AEA_N@Z`
- size: `1336`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002aae0`

## callees

- `0x1800034f7`
- `0x1800035ab`
- `0x18000ebfc`
- `0x18000ed24`
- `0x18000f44c`
- `0x180013efc`
- `0x180014364`
- `0x180014a08`
- `0x180016a58`
- `0x180016d38`
- `0x180016d98`
- `0x180016e40`
- `0x1800181d0`
- `0x180018290`
- `0x1800194ec`
- `0x18001a810`
- `0x18001aa30`
- `0x180028bb4`
- `0x18002a69c`
- `0x180033368`
- `0x180038150`
- `0x18007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f9f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002907f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800290b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028f9f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002907f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800290b8`

## string_xrefs

- `0x180028e14`: `Consent Read from cloud requestor ResultCode:  0x%08lx`
- `0x180029093`: `Consent Read through cloud requestor Failed: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::ReadConsentViaCR(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2,
        void **a3,
        _BYTE *a4)
{
  struct winrt::impl::shared_hstring_header **v5; // r15
  __int64 v7; // rbx
  LPVOID v8; // rsi
  void *v9; // rcx
  _QWORD *v10; // rax
  __int64 *v11; // rax
  volatile signed __int32 *v12; // r14
  __int64 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  volatile signed __int32 *v16; // r14
  volatile signed __int32 *v17; // r14
  __int64 v18; // r14
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 *v21; // rax
  _DWORD *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  const WCHAR *v26; // r12
  const WCHAR *v27; // rdx
  unsigned int v28; // edx
  int *v29; // r14
  __int64 v30; // r15
  const void *v31; // r13
  __int64 v32; // rax
  unsigned int v33; // edx
  void *v34; // r14
  int v35; // eax
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *v37; // r14
  __int64 v38; // r15
  const void *v39; // r13
  wil *v40; // rcx
  int *v41; // r14
  int v42; // esi
  HANDLE v43; // rax
  _QWORD *v44; // rax
  int v45; // esi
  int v47; // eax
  __int64 v48; // [rsp+20h] [rbp-88h] BYREF
  __int64 v49; // [rsp+28h] [rbp-80h] BYREF
  LPVOID v50; // [rsp+30h] [rbp-78h] BYREF
  __int64 v51; // [rsp+38h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-68h] BYREF
  volatile signed __int32 *v53; // [rsp+48h] [rbp-60h]
  int *v54; // [rsp+50h] [rbp-58h] BYREF
  volatile signed __int32 *v55; // [rsp+58h] [rbp-50h]
  int v56; // [rsp+60h] [rbp-48h]
  _QWORD v57[8]; // [rsp+68h] [rbp-40h] BYREF

  try
  {
    v5 = a2;
    *a2 = 0;
    v56 = 1;
    v7 = 0;
    v49 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl'::`2'::impl) )
    {
      CloudRequestorInterface::Create(&lpMem);
      v8 = lpMem;
      v9 = *a3;
      v50 = v9;
      if ( v9 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 8LL))(v9);
      v10 = CloudRequestorInterface::ReadConsentFromUCSAsync((__int64)v8, &v51, (__int64 *)&v50);
      v11 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::get(
                         v10,
                         &v48);
      if ( &v49 != v11 )
      {
        v7 = *v11;
        *v11 = 0;
        v49 = v7;
      }
      if ( v48 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
      if ( v51 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
      v12 = v53;
      if ( v53 )
      {
        if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
    }
    else
    {
      if ( !*(_QWORD *)(a1 + 40) )
      {
        v13 = (__int64 *)CloudRequestorInterface::Create(&v54);
        v14 = *v13;
        v15 = v13[1];
        *v13 = 0;
        v13[1] = 0;
        *(_QWORD *)(a1 + 40) = v14;
        v16 = *(volatile signed __int32 **)(a1 + 48);
        *(_QWORD *)(a1 + 48) = v15;
        if ( v16 )
        {
          if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
            if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
        v17 = v55;
        if ( v55 )
        {
          if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          }
        }
      }
      v18 = *(_QWORD *)(a1 + 40);
      v19 = (__int64)*a3;
      v51 = v19;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
      v20 = CloudRequestorInterface::ReadConsentFromUCSAsync(v18, &v48, &v51);
      v21 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::get(
                         v20,
                         &v50);
      if ( &v49 != v21 )
      {
        v7 = *v21;
        *v21 = 0;
        v49 = v7;
      }
      if ( v50 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v50);
      if ( v48 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
    }
    v22 = (_DWORD *)winrt::impl::consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult<winrt::Windows::Internal::CloudNotifications::ICreateOrUpdateSubscriptionResult>::ResultCode(
                      &v49,
                      &v48);
    UnifiedConsentLogging::TraceLoggingInfo("Consent Read from cloud requestor ResultCode:  0x%08lx", *v22);
    if ( *(int *)winrt::impl::consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult<winrt::Windows::Internal::CloudNotifications::ICreateOrUpdateSubscriptionResult>::ResultCode(
                   &v49,
                   &v48) < 0 )
    {
      v44 = (_QWORD *)winrt::impl::consume_Windows_Internal_CloudNotifications_INotificationSubscriptionResponse<winrt::Windows::Internal::CloudNotifications::INotificationSubscriptionResponse>::UpdatedETag(
                        &v49,
                        &v54);
      UnifiedConsentLogging::TraceLoggingInfo("Consent Read through cloud requestor Failed: %ws", *v44);
      v41 = v54;
      if ( !v54 )
      {
LABEL_73:
        if ( v7 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v49);
        goto LABEL_87;
      }
      v45 = _InterlockedDecrement(v54 + 6);
      if ( v45 )
      {
        if ( v45 < 0 )
          abort();
        goto LABEL_73;
      }
    }
    else
    {
      v23 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(
              &v49,
              &lpMem);
      v24 = winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
              v23,
              v57);
      v25 = winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(
              v24,
              &v51);
      winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,winrt::hstring,unsigned __int64>::get(
        v25,
        &v50);
      if ( v51 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v51);
      if ( v57[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v57);
      if ( lpMem )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      v26 = &Name;
      if ( v50 )
        v27 = (const WCHAR *)*((_QWORD *)v50 + 2);
      else
        v27 = &Name;
      UnifiedConsentLogging::TraceLoggingInfo("ConsentItem details from cloudRequestor: %ws", v27);
      v29 = (int *)v50;
      if ( v50 )
      {
        if ( (*(_BYTE *)v50 & 1) != 0 )
        {
          v30 = *((unsigned int *)v50 + 1);
          if ( (_DWORD)v30 )
          {
            v31 = (const void *)*((_QWORD *)v50 + 2);
            v29 = (int *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v30, v28);
            memcpy_s(v29 + 7, 2 * v30, v31, 2 * v30);
          }
          else
          {
            v29 = 0;
          }
          v5 = a2;
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)v50 + 6);
        }
      }
      else
      {
        v29 = 0;
      }
      v54 = v29;
      ConsentCoordinationHelpers::GetConsentValuesInJsonFromCR(&v48, &v54, a4);
      if ( v48 )
      {
        v32 = winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Web::Http::HttpResponseMessage>::ToString(
                &v48,
                &lpMem);
        winrt::hstring::operator=(v5, v32);
        v34 = lpMem;
        if ( lpMem )
        {
          v35 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v35 )
          {
            if ( v35 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v34);
          }
        }
        v37 = *v5;
        if ( *v5 )
        {
          if ( (*(_BYTE *)v37 & 1) != 0 )
          {
            v38 = *((unsigned int *)v37 + 1);
            if ( (_DWORD)v38 )
            {
              v39 = (const void *)*((_QWORD *)v37 + 2);
              v37 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v38, v33);
              memcpy_s((char *)v37 + 28, 2 * v38, v39, 2 * v38);
            }
            else
            {
              v37 = 0;
            }
            v5 = a2;
          }
          else
          {
            _InterlockedIncrement((volatile signed __int32 *)v37 + 6);
          }
        }
        else
        {
          v37 = 0;
        }
        lpMem = v37;
        winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::SetConsentState(
          a1,
          &lpMem);
        if ( *v5 )
          v26 = (const WCHAR *)*((_QWORD *)*v5 + 2);
        UnifiedConsentLogging::TraceLoggingInfo("ConsentItem details stored in cloudRequestor: %ws", v26);
      }
      else
      {
        UnifiedConsentLogging::TraceLoggingInfo("ConsentItem details from cloudRequestor is empty or invalid");
      }
      if ( v48 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
      v41 = (int *)v50;
      if ( !v50 )
        goto LABEL_73;
      v42 = _InterlockedDecrement((volatile signed __int32 *)v50 + 6);
      if ( v42 )
      {
        if ( v42 < 0 )
          abort();
        goto LABEL_73;
      }
    }
    v43 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v43, 0, v41);
    goto LABEL_73;
  }
  catch ( ... )
  {
    v47 = wil::ResultFromCaughtException(v40);
    UnifiedConsentLogging::TraceLoggingInfo("ReadConsentViaCR failed: hr = 0x%08x", v47);
  }
LABEL_87:
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return a2;
}

```

## disassembly

```asm
0x180028bb4  mov     rax, rsp
0x180028bb7  mov     [rax+20h], r9
0x180028bbb  mov     [rax+18h], r8
0x180028bbf  mov     [rax+10h], rdx
0x180028bc3  mov     [rax+8], rcx
0x180028bc7  push    rbx
0x180028bc8  push    rsi
0x180028bc9  push    rdi
0x180028bca  push    r12
0x180028bcc  push    r13
0x180028bce  push    r14
0x180028bd0  push    r15
0x180028bd2  sub     rsp, 70h
0x180028bd6  mov     r12, r8
0x180028bd9  mov     r15, rdx
0x180028bdc  mov     r13, rcx
0x180028bdf  xor     edi, edi
0x180028be1  mov     [rax-48h], edi
0x180028be4  mov     [rdx], rdi
0x180028be7  mov     dword ptr [rax-48h], 1
0x180028bee  mov     ebx, edi
0x180028bf0  mov     [rax-80h], rbx
0x180028bf4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification> `wil::Feature<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::GetImpl(void)'::`2'::impl
0x180028bfb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDirectSubscribeNotification@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDirectSubscribeNotification>::__private_IsEnabled(void)
0x180028c00  test    al, al
0x180028c02  jz      loc_180028CDE
0x180028c08  lea     rcx, [rsp+0A8h+lpMem]
0x180028c0d  call    ?Create@CloudRequestorInterface@@SA?AV?$shared_ptr@VCloudRequestorInterface@@@std@@XZ; CloudRequestorInterface::Create(void)
0x180028c12  nop
0x180028c13  mov     rsi, [rsp+0A8h+lpMem]
0x180028c18  mov     rcx, [r12]
0x180028c1c  mov     [rsp+0A8h+var_78], rcx
0x180028c21  test    rcx, rcx
0x180028c24  jz      short loc_180028C32
0x180028c26  mov     rax, [rcx]
0x180028c29  mov     rax, [rax+8]
0x180028c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c32  lea     r8, [rsp+0A8h+var_78]
0x180028c37  lea     rdx, [rsp+0A8h+var_70]
0x180028c3c  mov     rcx, rsi
0x180028c3f  call    ?ReadConsentFromUCSAsync@CloudRequestorInterface@@QEAA?AU?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UWebAccount@Credentials@Security@45@@Z; CloudRequestorInterface::ReadConsentFromUCSAsync(winrt::Windows::Security::Credentials::WebAccount)
0x180028c44  nop
0x180028c45  lea     rdx, [rsp+0A8h+var_88]
0x180028c4a  mov     rcx, rax
0x180028c4d  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UResponseDetails@CloudRequestor@Internal@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::get(void)
0x180028c52  lea     rcx, [rsp+0A8h+var_80]
0x180028c57  cmp     rcx, rax
0x180028c5a  jz      short loc_180028C67
0x180028c5c  mov     rbx, [rax]
0x180028c5f  mov     [rax], rdi
0x180028c62  mov     [rsp+0A8h+var_80], rbx
0x180028c67  cmp     [rsp+0A8h+var_88], rdi
0x180028c6c  jz      short loc_180028C79
0x180028c6e  lea     rcx, [rsp+0A8h+var_88]
0x180028c73  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028c78  nop
0x180028c79  cmp     [rsp+0A8h+var_70], rdi
0x180028c7e  jz      short loc_180028C8B
0x180028c80  lea     rcx, [rsp+0A8h+var_70]
0x180028c85  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028c8a  nop
0x180028c8b  mov     r14, [rsp+0A8h+var_60]
0x180028c90  or      esi, 0FFFFFFFFh
0x180028c93  test    r14, r14
0x180028c96  jz      loc_180028E03
0x180028c9c  mov     eax, esi
0x180028c9e  lock xadd [r14+8], eax
0x180028ca4  add     eax, esi
0x180028ca6  jnz     loc_180028E03
0x180028cac  mov     rax, [r14]
0x180028caf  mov     rcx, r14
0x180028cb2  mov     rax, [rax]
0x180028cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cba  mov     eax, esi
0x180028cbc  lock xadd [r14+0Ch], eax
0x180028cc2  add     eax, esi
0x180028cc4  jnz     loc_180028E03
0x180028cca  mov     rax, [r14]
0x180028ccd  mov     rcx, r14
0x180028cd0  mov     rax, [rax+8]
0x180028cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cd9  jmp     loc_180028E03
0x180028cde  cmp     [r13+28h], rdi
0x180028ce2  jnz     loc_180028D8A
0x180028ce8  lea     rcx, [rsp+0A8h+var_58]
0x180028ced  call    ?Create@CloudRequestorInterface@@SA?AV?$shared_ptr@VCloudRequestorInterface@@@std@@XZ; CloudRequestorInterface::Create(void)
0x180028cf2  mov     rcx, [rax]
0x180028cf5  mov     rdx, [rax+8]
0x180028cf9  mov     [rax], rdi
0x180028cfc  mov     [rax+8], rdi
0x180028d00  mov     [r13+28h], rcx
0x180028d04  mov     r14, [r13+30h]
0x180028d08  mov     [r13+30h], rdx
0x180028d0c  or      esi, 0FFFFFFFFh
0x180028d0f  test    r14, r14
0x180028d12  jz      short loc_180028D49
0x180028d14  mov     eax, esi
0x180028d16  lock xadd [r14+8], eax
0x180028d1c  add     eax, esi
0x180028d1e  jnz     short loc_180028D49
0x180028d20  mov     rax, [r14]
0x180028d23  mov     rcx, r14
0x180028d26  mov     rax, [rax]
0x180028d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d2e  mov     eax, esi
0x180028d30  lock xadd [r14+0Ch], eax
0x180028d36  add     eax, esi
0x180028d38  jnz     short loc_180028D49
0x180028d3a  mov     rax, [r14]
0x180028d3d  mov     rcx, r14
0x180028d40  mov     rax, [rax+8]
0x180028d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d49  mov     r14, [rsp+0A8h+var_50]
0x180028d4e  test    r14, r14
0x180028d51  jz      short loc_180028D8D
0x180028d53  mov     eax, esi
0x180028d55  lock xadd [r14+8], eax
0x180028d5b  add     eax, esi
0x180028d5d  jnz     short loc_180028D8D
0x180028d5f  mov     rax, [r14]
0x180028d62  mov     rcx, r14
0x180028d65  mov     rax, [rax]
0x180028d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d6d  mov     eax, esi
0x180028d6f  lock xadd [r14+0Ch], eax
0x180028d75  add     eax, esi
0x180028d77  jnz     short loc_180028D8D
0x180028d79  mov     rax, [r14]
0x180028d7c  mov     rcx, r14
0x180028d7f  mov     rax, [rax+8]
0x180028d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d88  jmp     short loc_180028D8D
0x180028d8a  or      esi, 0FFFFFFFFh
0x180028d8d  mov     r14, [r13+28h]
0x180028d91  mov     rcx, [r12]
0x180028d95  mov     [rsp+0A8h+var_70], rcx
0x180028d9a  test    rcx, rcx
0x180028d9d  jz      short loc_180028DAB
0x180028d9f  mov     rax, [rcx]
0x180028da2  mov     rax, [rax+8]
0x180028da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028dab  lea     r8, [rsp+0A8h+var_70]
0x180028db0  lea     rdx, [rsp+0A8h+var_88]
0x180028db5  mov     rcx, r14
0x180028db8  call    ?ReadConsentFromUCSAsync@CloudRequestorInterface@@QEAA?AU?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UWebAccount@Credentials@Security@45@@Z; CloudRequestorInterface::ReadConsentFromUCSAsync(winrt::Windows::Security::Credentials::WebAccount)
0x180028dbd  nop
0x180028dbe  lea     rdx, [rsp+0A8h+var_78]
0x180028dc3  mov     rcx, rax
0x180028dc6  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UResponseDetails@CloudRequestor@Internal@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,winrt::Windows::Internal::CloudRequestor::ResponseDetails>::get(void)
0x180028dcb  lea     rcx, [rsp+0A8h+var_80]
0x180028dd0  cmp     rcx, rax
0x180028dd3  jz      short loc_180028DE0
0x180028dd5  mov     rbx, [rax]
0x180028dd8  mov     [rax], rdi
0x180028ddb  mov     [rsp+0A8h+var_80], rbx
0x180028de0  cmp     [rsp+0A8h+var_78], rdi
0x180028de5  jz      short loc_180028DF2
0x180028de7  lea     rcx, [rsp+0A8h+var_78]
0x180028dec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028df1  nop
0x180028df2  cmp     [rsp+0A8h+var_88], rdi
0x180028df7  jz      short loc_180028E03
0x180028df9  lea     rcx, [rsp+0A8h+var_88]
0x180028dfe  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028e03  lea     rdx, [rsp+0A8h+var_88]
0x180028e08  lea     rcx, [rsp+0A8h+var_80]
0x180028e0d  call    ?ResultCode@?$consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult@UICreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult<winrt::Windows::Internal::CloudNotifications::ICreateOrUpdateSubscriptionResult>::ResultCode(void)
0x180028e12  mov     edx, [rax]
0x180028e14  lea     rcx, aConsentReadFro; "Consent Read from cloud requestor Resul"...
0x180028e1b  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180028e20  lea     rdx, [rsp+0A8h+var_88]
0x180028e25  lea     rcx, [rsp+0A8h+var_80]
0x180028e2a  call    ?ResultCode@?$consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult@UICreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudNotifications_ICreateOrUpdateSubscriptionResult<winrt::Windows::Internal::CloudNotifications::ICreateOrUpdateSubscriptionResult>::ResultCode(void)
0x180028e2f  lea     rcx, [rsp+0A8h+var_80]
0x180028e34  cmp     [rax], edi
0x180028e36  jl      loc_180029086
0x180028e3c  lea     rdx, [rsp+0A8h+lpMem]
0x180028e41  call    ?BaseUrl@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::BaseUrl(void)
0x180028e46  nop
0x180028e47  lea     rdx, [rsp+0A8h+var_40]
0x180028e4c  mov     rcx, rax
0x180028e4f  call    ?ClientId@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(void)
0x180028e54  nop
0x180028e55  lea     rdx, [rsp+0A8h+var_70]
0x180028e5a  mov     rcx, rax
0x180028e5d  call    ?Properties@?$consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Authentication_Web_Core_IWebTokenRequest<winrt::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::Properties(void)
0x180028e62  nop
0x180028e63  lea     rdx, [rsp+0A8h+var_78]
0x180028e68  mov     rcx, rax
0x180028e6b  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@Uhstring@winrt@@_K@Foundation@Windows@winrt@@Uhstring@4@_K@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::hstring,unsigned __int64>,winrt::hstring,unsigned __int64>::get(void)
0x180028e70  nop
0x180028e71  cmp     [rsp+0A8h+var_70], rdi
0x180028e76  jz      short loc_180028E83
0x180028e78  lea     rcx, [rsp+0A8h+var_70]
0x180028e7d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028e82  nop
0x180028e83  cmp     [rsp+0A8h+var_40], rdi
0x180028e88  jz      short loc_180028E95
0x180028e8a  lea     rcx, [rsp+0A8h+var_40]
0x180028e8f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028e94  nop
0x180028e95  cmp     [rsp+0A8h+lpMem], rdi
0x180028e9a  jz      short loc_180028EA6
0x180028e9c  lea     rcx, [rsp+0A8h+lpMem]
0x180028ea1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028ea6  mov     rax, [rsp+0A8h+var_78]
0x180028eab  lea     r12, Name
0x180028eb2  test    rax, rax
0x180028eb5  jz      short loc_180028EBD
0x180028eb7  mov     rdx, [rax+10h]
0x180028ebb  jmp     short loc_180028EC0
0x180028ebd  mov     rdx, r12
0x180028ec0  lea     rcx, aConsentitemDet; "ConsentItem details from cloudRequestor"...
0x180028ec7  call    ?TraceLoggingInfo@UnifiedConsentLogging@@SAXPEBDZZ; UnifiedConsentLogging::TraceLoggingInfo(char const *,...)
0x180028ecc  mov     r14, [rsp+0A8h+var_78]
0x180028ed1  test    r14, r14
0x180028ed4  jnz     short loc_180028EDB
0x180028ed6  mov     r14, rdi
0x180028ed9  jmp     short loc_180028F22
0x180028edb  test    byte ptr [r14], 1
0x180028edf  jnz     short loc_180028EE8
0x180028ee1  lock inc dword ptr [r14+18h]
0x180028ee6  jmp     short loc_180028F22
0x180028ee8  mov     r15d, [r14+4]
0x180028eec  test    r15d, r15d
0x180028eef  jnz     short loc_180028EF6
0x180028ef1  mov     r14, rdi
0x180028ef4  jmp     short loc_180028F1A
0x180028ef6  mov     r13, [r14+10h]
0x180028efa  mov     ecx, r15d; this
0x180028efd  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180028f02  mov     r14, rax
0x180028f05  mov     rdx, r15
0x180028f08  add     rdx, rdx; DestinationSize
0x180028f0b  lea     rcx, [rax+1Ch]; Destination
0x180028f0f  mov     r9, rdx; SourceSize
0x180028f12  mov     r8, r13; Source
0x180028f15  call    memcpy_s
0x180028f1a  mov     r15, [rsp+0A8h+arg_8]
0x180028f22  mov     [rsp+0A8h+var_58], r14
0x180028f27  mov     r8, [rsp+0A8h+arg_18]
0x180028f2f  lea     rdx, [rsp+0A8h+var_58]
0x180028f34  lea     rcx, [rsp+0A8h+var_88]
0x180028f39  call    ?GetConsentValuesInJsonFromCR@ConsentCoordinationHelpers@@YA?AUJsonObject@Json@Data@Windows@winrt@@Uhstring@6@AEA_N@Z; ConsentCoordinationHelpers::GetConsentValuesInJsonFromCR(winrt::hstring,bool &)
0x180028f3e  nop
0x180028f3f  cmp     [rsp+0A8h+var_88], rdi
0x180028f44  jz      loc_180029021
0x180028f4a  lea     rdx, [rsp+0A8h+lpMem]
0x180028f4f  lea     rcx, [rsp+0A8h+var_88]
0x180028f54  call    ?ToString@?$consume_Windows_Foundation_IStringable@UHttpResponseMessage@Http@Web@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Web::Http::HttpResponseMessage>::ToString(void)
0x180028f59  mov     rdx, rax
0x180028f5c  mov     rcx, r15
0x180028f5f  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x180028f64  mov     r14, [rsp+0A8h+lpMem]
0x180028f69  test    r14, r14
0x180028f6c  jz      short loc_180028F8E
0x180028f6e  mov     eax, esi
0x180028f70  lock xadd [r14+18h], eax
0x180028f76  sub     eax, 1
0x180028f79  jnz     short loc_180028F9B
0x180028f7b  nop
0x180028f7c  call    WINRT_IMPL_GetProcessHeap
0x180028f81  mov     rcx, rax; hHeap
0x180028f84  mov     r8, r14; lpMem
0x180028f87  xor     edx, edx; dwFlags
0x180028f89  call    WINRT_IMPL_HeapFree
0x180028f8e  mov     r14, [r15]
0x180028f91  test    r14, r14
0x180028f94  jnz     short loc_180028FA6
0x180028f96  mov     r14, rdi
0x180028f99  jmp     short loc_180028FED
0x180028f9b  test    eax, eax
0x180028f9d  jns     short loc_180028F8E
0x180028f9f  call    cs:__imp_abort
0x180028fa6  test    byte ptr [r14], 1
0x180028faa  jnz     short loc_180028FB3
0x180028fac  lock inc dword ptr [r14+18h]
0x180028fb1  jmp     short loc_180028FED
0x180028fb3  mov     r15d, [r14+4]
0x180028fb7  test    r15d, r15d
0x180028fba  jnz     short loc_180028FC1
0x180028fbc  mov     r14, rdi
0x180028fbf  jmp     short loc_180028FE5
0x180028fc1  mov     r13, [r14+10h]
0x180028fc5  mov     ecx, r15d; this
0x180028fc8  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180028fcd  mov     r14, rax
0x180028fd0  mov     rdx, r15
0x180028fd3  add     rdx, rdx; DestinationSize
0x180028fd6  lea     rcx, [rax+1Ch]; Destination
0x180028fda  mov     r9, rdx; SourceSize
0x180028fdd  mov     r8, r13; Source
0x180028fe0  call    memcpy_s
0x180028fe5  mov     r15, [rsp+0A8h+arg_8]
0x180028fed  mov     [rsp+0A8h+lpMem], r14
0x180028ff2  lea     rdx, [rsp+0A8h+lpMem]
0x180028ff7  mov     rcx, [rsp+0A8h+arg_0]
0x180028fff  call    ?SetConsentState@UnifiedConsentCoordinator@implementation@ConsentUx@Shell@Internal@Windows@winrt@@QEAAXUhstring@7@@Z; winrt::Windows::Internal::Shell::ConsentUx::implementation::UnifiedConsentCoordinator::SetConsentState(winrt::hstring)
0x180029004  mov     rax, [r15]
0x180029007  test    rax, rax
  ... truncated ...
```
