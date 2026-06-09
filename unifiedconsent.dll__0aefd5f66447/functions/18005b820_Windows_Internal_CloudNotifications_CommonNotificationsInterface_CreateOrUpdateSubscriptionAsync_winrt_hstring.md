# Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateOrUpdateSubscriptionAsync(winrt::hstring)

- ea: `0x18005b820`
- end: `0x18005b9a7`
- name: `?CreateOrUpdateSubscriptionAsync@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@UEAA?AU?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@4winrt@@Uhstring@7@@Z`
- size: `391`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002810`
- `0x180002840`
- `0x180003384`
- `0x1800034f7`
- `0x1800035ab`
- `0x180059840`
- `0x18005b820`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005b8f8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005b8f8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005b9a0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18005b9a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateOrUpdateSubscriptionAsync(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdi
  volatile signed __int32 *v8; // rax
  __int64 v9; // rbx
  volatile signed __int32 *v10; // rbx
  int v11; // eax
  HANDLE ProcessHeap; // rax

  v6 = operator new(0x5F0u);
  v7 = (__int64)(v6 + 14);
  v6[187] = a1;
  v8 = *a3;
  *a3 = 0;
  *(_QWORD *)(v7 + 1392) = v8;
  *(_QWORD *)v7 = Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateOrUpdateSubscriptionAsync__ResumeCoro_1;
  *(_DWORD *)(v7 + 8) = 65538;
  v9 = v7 - 112;
  memset_0((void *)(v7 - 112), 0, 0x70u);
  *(_QWORD *)(v9 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>>::`vftable';
  *(_QWORD *)(v9 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(v9 + 8) = 1;
  *(_QWORD *)(v9 + 32) = 0;
  *(_QWORD *)(v9 + 40) = 0;
  *(_BYTE *)(v9 + 48) = 0;
  *(_QWORD *)v9 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,void>::`vftable';
  *(_QWORD *)(v9 + 56) = 0;
  *(_QWORD *)(v9 + 64) = 0;
  __ExceptionPtrCreate((void *)(v7 - 112 + 56));
  *(_QWORD *)(v9 + 72) = 0;
  *(_QWORD *)(v9 + 80) = 0;
  *(_QWORD *)(v9 + 88) = 0;
  *(_DWORD *)(v9 + 96) = 0;
  *(_BYTE *)(v9 + 100) = 0;
  *(_QWORD *)v9 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type::`vftable';
  *(_QWORD *)(v9 + 104) = 0;
  *a2 = v7 - 112 + 16;
  if ( v7 != 96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 16) + 8LL))(v9 + 16);
  *(_BYTE *)(v7 + 1376) = 0;
  Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateOrUpdateSubscriptionAsync__ResumeCoro_1(v7);
  v10 = *a3;
  if ( *a3 )
  {
    v11 = _InterlockedDecrement(v10 + 6);
    if ( v11 )
    {
      if ( v11 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v10);
    }
    *a3 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18005b820  mov     rax, rsp
0x18005b823  mov     [rax+8], rbx
0x18005b827  mov     [rax+20h], rbp
0x18005b82b  mov     [rax+18h], r8
0x18005b82f  mov     [rax+10h], rdx
0x18005b833  push    rsi
0x18005b834  push    rdi
0x18005b835  push    r12
0x18005b837  push    r14
0x18005b839  push    r15
0x18005b83b  sub     rsp, 40h
0x18005b83f  mov     rax, cs:__security_cookie
0x18005b846  xor     rax, rsp
0x18005b849  mov     [rsp+68h+var_30], rax
0x18005b84e  mov     rsi, r8
0x18005b851  mov     r15, rdx
0x18005b854  mov     rbx, rcx
0x18005b857  mov     r12d, 560h
0x18005b85d  lea     rcx, [r12+90h]; Size
0x18005b865  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005b86a  mov     [rsp+68h+var_48], rax
0x18005b86f  mov     r8d, 70h ; 'p'; Size
0x18005b875  lea     rdi, [r8+rax]
0x18005b879  mov     [rsp+68h+var_48], rdi
0x18005b87e  mov     [rdi+r12+8], rbx
0x18005b883  mov     rax, [rsi]
0x18005b886  xor     ebp, ebp
0x18005b888  mov     [rsi], rbp
0x18005b88b  mov     [rdi+r12+10h], rax
0x18005b890  lea     rax, Windows__Internal__CloudNotifications__CommonNotificationsInterface__CreateOrUpdateSubscriptionAsync$_ResumeCoro$1
0x18005b897  mov     [rdi], rax
0x18005b89a  mov     dword ptr [rdi+8], 10002h
0x18005b8a1  lea     rbx, [rdi-70h]
0x18005b8a5  xor     edx, edx; Val
0x18005b8a7  mov     rcx, rbx; void *
0x18005b8aa  call    memset_0
0x18005b8af  lea     r14, [rbx+10h]
0x18005b8b3  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCloudRequestorInterface@@UWebAccount@Credentials@Security@34@@experimental@std@@U?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>>::`vftable'
0x18005b8ba  mov     [r14], rax
0x18005b8bd  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCloudRequestorInterface@@UWebAccount@Credentials@Security@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18005b8c4  mov     [r14+8], rax
0x18005b8c8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005b8cf  mov     qword ptr [rbx+8], 1
0x18005b8d7  mov     [rbx+20h], rbp
0x18005b8db  mov     [rbx+28h], rbp
0x18005b8df  mov     [rbx+30h], bpl
0x18005b8e3  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCloudRequestorInterface@@UWebAccount@Credentials@Security@34@@experimental@std@@U?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,void>::`vftable'
0x18005b8ea  mov     [rbx], rax
0x18005b8ed  lea     rcx, [rbx+38h]
0x18005b8f1  mov     [rcx], rbp
0x18005b8f4  mov     [rcx+8], rbp
0x18005b8f8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005b8fe  mov     [rbx+48h], rbp
0x18005b902  mov     [rbx+50h], rbp
0x18005b906  mov     [rbx+58h], rbp
0x18005b90a  xor     eax, eax
0x18005b90c  mov     [rbx+60h], eax
0x18005b90f  mov     [rbx+64h], bpl
0x18005b913  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UCreateOrUpdateSubscriptionResult@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCloudRequestorInterface@@UWebAccount@Credentials@Security@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::CreateOrUpdateSubscriptionResult>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type::`vftable'
0x18005b91a  mov     [rbx], rax
0x18005b91d  mov     [rbx+68h], rbp
0x18005b921  mov     [r15], r14
0x18005b924  test    r14, r14
0x18005b927  jz      short loc_18005B939
0x18005b929  mov     rax, [r14]
0x18005b92c  mov     rcx, r14
0x18005b92f  mov     rax, [rax+8]
0x18005b933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b938  nop
0x18005b939  xor     eax, eax
0x18005b93b  mov     [rdi+r12], al
0x18005b93f  mov     rcx, rdi
0x18005b942  call    Windows__Internal__CloudNotifications__CommonNotificationsInterface__CreateOrUpdateSubscriptionAsync$_ResumeCoro$1
0x18005b947  nop
0x18005b948  mov     rbx, [rsi]
0x18005b94b  test    rbx, rbx
0x18005b94e  jz      short loc_18005B973
0x18005b950  or      eax, 0FFFFFFFFh
0x18005b953  lock xadd [rbx+18h], eax
0x18005b958  sub     eax, 1
0x18005b95b  jnz     short loc_18005B99C
0x18005b95d  nop
0x18005b95e  call    WINRT_IMPL_GetProcessHeap
0x18005b963  mov     rcx, rax; hHeap
0x18005b966  mov     r8, rbx; lpMem
0x18005b969  xor     edx, edx; dwFlags
0x18005b96b  call    WINRT_IMPL_HeapFree
0x18005b970  mov     [rsi], rbp
0x18005b973  mov     rax, r15
0x18005b976  mov     rcx, [rsp+68h+var_30]
0x18005b97b  xor     rcx, rsp; StackCookie
0x18005b97e  call    __security_check_cookie
0x18005b983  lea     r11, [rsp+68h+var_28]
0x18005b988  mov     rbx, [r11+30h]
0x18005b98c  mov     rbp, [r11+48h]
0x18005b990  mov     rsp, r11
0x18005b993  pop     r15
0x18005b995  pop     r14
0x18005b997  pop     r12
0x18005b999  pop     rdi
0x18005b99a  pop     rsi
0x18005b99b  retn
0x18005b99c  test    eax, eax
0x18005b99e  jns     short loc_18005B970
0x18005b9a0  call    cs:__imp_abort
```
