# Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler::SendSubscriptionRequestAsync(winrt::hstring,winrt::hstring,winrt::hstring)

- ea: `0x18006bc40`
- end: `0x18006be3d`
- name: `?SendSubscriptionRequestAsync@AfsNotificationSubscriptionHandler@CloudNotifications@Internal@Windows@@UEAA?AU?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@4winrt@@Uhstring@7@00@Z`
- size: `509`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180002840`
- `0x180003384`
- `0x1800034f7`
- `0x1800035ab`
- `0x18006a080`
- `0x18006bc40`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006bd32`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18006bd32`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006be20`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006be2b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006be36`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006be20`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006be2b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18006be36`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler::SendSubscriptionRequestAsync(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3,
        volatile signed __int32 **a4,
        volatile signed __int32 **a5)
{
  _QWORD *v9; // rax
  __int64 v10; // rdi
  volatile signed __int32 *v11; // rax
  volatile signed __int32 *v12; // rax
  volatile signed __int32 *v13; // rax
  __int64 v14; // rbx
  volatile signed __int32 *v15; // rdi
  int v16; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v18; // rdi
  int v19; // eax
  HANDLE v20; // rax
  volatile signed __int32 *v21; // rdi
  int v22; // ebx
  HANDLE v23; // rax

  v9 = operator new(0x520u);
  v10 = (__int64)(v9 + 14);
  v9[159] = a1;
  v11 = *a3;
  *a3 = 0;
  *(_QWORD *)(v10 + 1168) = v11;
  v12 = *a4;
  *a4 = 0;
  *(_QWORD *)(v10 + 1176) = v12;
  v13 = *a5;
  *a5 = 0;
  *(_QWORD *)(v10 + 1184) = v13;
  *(_QWORD *)v10 = Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler::SendSubscriptionRequestAsync__ResumeCoro_1;
  *(_DWORD *)(v10 + 8) = 65538;
  v14 = v10 - 112;
  memset_0((void *)(v10 - 112), 0, 0x70u);
  *(_QWORD *)(v14 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>>::`vftable';
  *(_QWORD *)(v14 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(v14 + 8) = 1;
  *(_QWORD *)(v14 + 32) = 0;
  *(_QWORD *)(v14 + 40) = 0;
  *(_BYTE *)(v14 + 48) = 0;
  *(_QWORD *)v14 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,void>::`vftable';
  *(_QWORD *)(v14 + 56) = 0;
  *(_QWORD *)(v14 + 64) = 0;
  __ExceptionPtrCreate((void *)(v10 - 112 + 56));
  *(_QWORD *)(v14 + 72) = 0;
  *(_QWORD *)(v14 + 80) = 0;
  *(_QWORD *)(v14 + 88) = 0;
  *(_DWORD *)(v14 + 96) = 0;
  *(_BYTE *)(v14 + 100) = 0;
  *(_QWORD *)v14 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type::`vftable';
  *(_QWORD *)(v14 + 104) = 0;
  *a2 = v10 - 112 + 16;
  if ( v10 != 96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v14 + 16) + 8LL))(v14 + 16);
  *(_BYTE *)(v10 + 1152) = 0;
  Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler::SendSubscriptionRequestAsync__ResumeCoro_1(v10);
  v15 = *a3;
  if ( *a3 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
    }
    *a3 = 0;
  }
  v18 = *a4;
  if ( *a4 )
  {
    v19 = _InterlockedDecrement(v18 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      v20 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v20, 0, (LPVOID)v18);
    }
    *a4 = 0;
  }
  v21 = *a5;
  if ( *a5 )
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
    *a5 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18006bc40  mov     [rsp+arg_18], r9
0x18006bc45  mov     [rsp+arg_10], r8
0x18006bc4a  mov     [rsp+arg_8], rdx
0x18006bc4f  push    rbx
0x18006bc50  push    rbp
0x18006bc51  push    rsi
0x18006bc52  push    rdi
0x18006bc53  push    r12
0x18006bc55  push    r13
0x18006bc57  push    r14
0x18006bc59  push    r15
0x18006bc5b  sub     rsp, 38h
0x18006bc5f  mov     rsi, r9
0x18006bc62  mov     r14, r8
0x18006bc65  mov     r12, rdx
0x18006bc68  mov     rbx, rcx
0x18006bc6b  mov     r15d, 480h
0x18006bc71  lea     rcx, [r15+0A0h]; Size
0x18006bc78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bc7d  mov     [rsp+78h+arg_0], rax
0x18006bc85  mov     r8d, 70h ; 'p'; Size
0x18006bc8b  lea     rdi, [r8+rax]
0x18006bc8f  mov     [rsp+78h+arg_0], rdi
0x18006bc97  mov     [rdi+r15+8], rbx
0x18006bc9c  mov     rax, [r14]
0x18006bc9f  xor     r13d, r13d
0x18006bca2  mov     [r14], r13
0x18006bca5  mov     [rdi+r15+10h], rax
0x18006bcaa  mov     rax, [rsi]
0x18006bcad  mov     [rsi], r13
0x18006bcb0  mov     [rdi+r15+18h], rax
0x18006bcb5  mov     rbp, [rsp+78h+arg_20]
0x18006bcbd  mov     rax, [rbp+0]
0x18006bcc1  mov     [rbp+0], r13
0x18006bcc5  mov     [rdi+r15+20h], rax
0x18006bcca  lea     rax, Windows__Internal__CloudNotifications__AfsNotificationSubscriptionHandler__SendSubscriptionRequestAsync$_ResumeCoro$1
0x18006bcd1  mov     [rdi], rax
0x18006bcd4  mov     dword ptr [rdi+8], 10002h
0x18006bcdb  lea     rbx, [rdi-70h]
0x18006bcdf  xor     edx, edx; Val
0x18006bce1  mov     rcx, rbx; void *
0x18006bce4  call    memset_0
0x18006bce9  lea     r15, [rbx+10h]
0x18006bced  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVAfsNotificationSubscriptionHandler@CloudNotifications@Internal@3@Uhstring@4@U84@U84@@experimental@std@@U?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>>::`vftable'
0x18006bcf4  mov     [r15], rax
0x18006bcf7  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVAfsNotificationSubscriptionHandler@CloudNotifications@Internal@3@Uhstring@4@U84@U84@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18006bcfe  mov     [r15+8], rax
0x18006bd02  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18006bd09  mov     qword ptr [rbx+8], 1
0x18006bd11  mov     [rbx+20h], r13
0x18006bd15  mov     [rbx+28h], r13
0x18006bd19  mov     [rbx+30h], r13b
0x18006bd1d  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVAfsNotificationSubscriptionHandler@CloudNotifications@Internal@3@Uhstring@4@U84@U84@@experimental@std@@U?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,void>::`vftable'
0x18006bd24  mov     [rbx], rax
0x18006bd27  lea     rcx, [rbx+38h]
0x18006bd2b  mov     [rcx], r13
0x18006bd2e  mov     [rcx+8], r13
0x18006bd32  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18006bd38  mov     [rbx+48h], r13
0x18006bd3c  mov     [rbx+50h], r13
0x18006bd40  mov     [rbx+58h], r13
0x18006bd44  xor     eax, eax
0x18006bd46  mov     [rbx+60h], eax
0x18006bd49  mov     [rbx+64h], r13b
0x18006bd4d  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UNotificationSubscriptionResponse@CloudNotifications@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVAfsNotificationSubscriptionHandler@CloudNotifications@Internal@3@Uhstring@4@U84@U84@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudNotifications::NotificationSubscriptionResponse>,Windows::Internal::CloudNotifications::AfsNotificationSubscriptionHandler *,winrt::hstring,winrt::hstring,winrt::hstring>::promise_type::`vftable'
0x18006bd54  mov     [rbx], rax
0x18006bd57  mov     [rbx+68h], r13
0x18006bd5b  mov     [r12], r15
0x18006bd5f  test    r15, r15
0x18006bd62  jz      short loc_18006BD74
0x18006bd64  mov     rax, [r15]
0x18006bd67  mov     rcx, r15
0x18006bd6a  mov     rax, [rax+8]
0x18006bd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd73  nop
0x18006bd74  xor     eax, eax
0x18006bd76  mov     ecx, 480h
0x18006bd7b  mov     [rdi+rcx], al
0x18006bd7e  mov     rcx, rdi
0x18006bd81  call    Windows__Internal__CloudNotifications__AfsNotificationSubscriptionHandler__SendSubscriptionRequestAsync$_ResumeCoro$1
0x18006bd86  nop
0x18006bd87  mov     rdi, [r14]
0x18006bd8a  or      ebx, 0FFFFFFFFh
0x18006bd8d  test    rdi, rdi
0x18006bd90  jz      short loc_18006BDB4
0x18006bd92  mov     eax, ebx
0x18006bd94  lock xadd [rdi+18h], eax
0x18006bd99  sub     eax, 1
0x18006bd9c  jnz     short loc_18006BE1C
0x18006bd9e  nop
0x18006bd9f  call    WINRT_IMPL_GetProcessHeap
0x18006bda4  mov     rcx, rax; hHeap
0x18006bda7  mov     r8, rdi; lpMem
0x18006bdaa  xor     edx, edx; dwFlags
0x18006bdac  call    WINRT_IMPL_HeapFree
0x18006bdb1  mov     [r14], r13
0x18006bdb4  mov     rdi, [rsi]
0x18006bdb7  test    rdi, rdi
0x18006bdba  jz      short loc_18006BDDE
0x18006bdbc  mov     eax, ebx
0x18006bdbe  lock xadd [rdi+18h], eax
0x18006bdc3  sub     eax, 1
0x18006bdc6  jnz     short loc_18006BE27
0x18006bdc8  nop
0x18006bdc9  call    WINRT_IMPL_GetProcessHeap
0x18006bdce  mov     rcx, rax; hHeap
0x18006bdd1  mov     r8, rdi; lpMem
0x18006bdd4  xor     edx, edx; dwFlags
0x18006bdd6  call    WINRT_IMPL_HeapFree
0x18006bddb  mov     [rsi], r13
0x18006bdde  mov     rdi, [rbp+0]
0x18006bde2  test    rdi, rdi
0x18006bde5  jz      short loc_18006BE08
0x18006bde7  lock xadd [rdi+18h], ebx
0x18006bdec  sub     ebx, 1
0x18006bdef  jnz     short loc_18006BE32
0x18006bdf1  nop
0x18006bdf2  call    WINRT_IMPL_GetProcessHeap
0x18006bdf7  mov     rcx, rax; hHeap
0x18006bdfa  mov     r8, rdi; lpMem
0x18006bdfd  xor     edx, edx; dwFlags
0x18006bdff  call    WINRT_IMPL_HeapFree
0x18006be04  mov     [rbp+0], r13
0x18006be08  mov     rax, r12
0x18006be0b  add     rsp, 38h
0x18006be0f  pop     r15
0x18006be11  pop     r14
0x18006be13  pop     r13
0x18006be15  pop     r12
0x18006be17  pop     rdi
0x18006be18  pop     rsi
0x18006be19  pop     rbp
0x18006be1a  pop     rbx
0x18006be1b  retn
0x18006be1c  test    eax, eax
0x18006be1e  jns     short loc_18006BDB1
0x18006be20  call    cs:__imp_abort
0x18006be27  test    eax, eax
0x18006be29  jns     short loc_18006BDDB
0x18006be2b  call    cs:__imp_abort
0x18006be32  test    ebx, ebx
0x18006be34  jns     short loc_18006BE04
0x18006be36  call    cs:__imp_abort
```
