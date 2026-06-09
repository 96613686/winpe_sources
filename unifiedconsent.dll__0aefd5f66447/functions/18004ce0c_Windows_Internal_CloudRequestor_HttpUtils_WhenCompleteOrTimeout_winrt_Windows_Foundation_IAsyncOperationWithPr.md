# Windows::Internal::CloudRequestor::HttpUtils::WhenCompleteOrTimeout<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpResponseMessage,0>(winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,std::chrono::duration<__int64,std::ratio<1,10000000>>,winrt::Windows::Web::Http::HttpResponseMessage)

- ea: `0x18004ce0c`
- end: `0x18004d0dd`
- name: `??$WhenCompleteOrTimeout@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@UHttpResponseMessage@Http@Web@34@$0A@@HttpUtils@CloudRequestor@Internal@Windows@@YA?AU?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@3winrt@@U4536@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@UHttpResponseMessage@Http@Web@36@@Z`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004f160`

## callees

- `0x180002840`
- `0x180003384`
- `0x18000ed24`
- `0x18004ca90`
- `0x18004ce0c`
- `0x18004e100`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004cf04`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004d034`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004cf04`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004d034`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
_QWORD *__fastcall Windows::Internal::CloudRequestor::HttpUtils::WhenCompleteOrTimeout<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpResponseMessage,0>(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-41h] BYREF
  __int64 v17; // [rsp+38h] [rbp-39h] BYREF
  _QWORD *v18; // [rsp+40h] [rbp-31h] BYREF
  _QWORD *v19; // [rsp+48h] [rbp-29h]
  __int64 *v20; // [rsp+50h] [rbp-21h]
  __int64 *v21; // [rsp+58h] [rbp-19h]
  char v22; // [rsp+E8h] [rbp+77h] BYREF
  _QWORD *v23; // [rsp+F0h] [rbp+7Fh]

  v23 = a4;
  v20 = (__int64 *)&v18;
  v22 = 0;
  v8 = *a4;
  *a4 = 0;
  v16 = v8;
  v21 = &v16;
  v9 = operator new(0x120u);
  v19 = v9 + 16;
  v9[33] = &v22;
  v9[34] = a3;
  v10 = v16;
  v16 = 0;
  v9[35] = v10;
  v9[16] = lambda_29ca8c67725922f04d1500a82c8067c5___ResumeCoro_1::operator();
  *((_DWORD *)v9 + 34) = 65538;
  memset_0(v9, 0, 0x78u);
  v9[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,_lambda_29ca8c67725922f04d1500a82c8067c5_ const *,std::chrono::duration<__int64,std::ratio<1,10000000>>,winrt::Windows::Web::Http::HttpResponseMessage>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::`vftable';
  v9[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v9[1] = 1;
  v9[4] = 0;
  v9[5] = 0;
  *((_BYTE *)v9 + 48) = 0;
  *v9 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::`vftable';
  v9[7] = 0;
  v9[8] = 0;
  __ExceptionPtrCreate(v9 + 7);
  v9[9] = 0;
  v9[10] = 0;
  v9[11] = 0;
  *((_DWORD *)v9 + 24) = 0;
  *((_BYTE *)v9 + 100) = 0;
  *v9 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type::`vftable';
  v9[13] = 0;
  v9[14] = 0;
  v18 = v9 + 2;
  if ( v9 != (_QWORD *)-16LL )
    (*(void (__fastcall **)(_QWORD *))(v9[2] + 8LL))(v9 + 2);
  *((_BYTE *)v9 + 256) = 0;
  lambda_29ca8c67725922f04d1500a82c8067c5___ResumeCoro_1::operator()(v9 + 16);
  if ( v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v16);
  v21 = (__int64 *)&v18;
  v11 = *a2;
  v17 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v20 = &v17;
  v12 = operator new(0x150u);
  v19 = v12 + 16;
  v13 = v17;
  v17 = 0;
  v12[39] = v13;
  v14 = v18;
  v18 = 0;
  v12[40] = v14;
  v12[16] = Windows::Internal::CloudRequestor::HttpUtils::WhenAnyCancelOthers__ResumeCoro_1_winrt::Windows::Foundation::IAsyncOperationWithProgress_winrt::Windows::Web::Http::HttpResponseMessage_winrt::Windows::Web::Http::HttpProgress__winrt::Windows::Foundation::IAsyncOperationWithProgress_winrt::Windows::Web::Http::HttpResponseMessage_winrt::Windows::Web::Http::HttpProgress___;
  *((_DWORD *)v12 + 34) = 65538;
  memset_0(v12, 0, 0x78u);
  v12[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,_lambda_29ca8c67725922f04d1500a82c8067c5_ const *,std::chrono::duration<__int64,std::ratio<1,10000000>>,winrt::Windows::Web::Http::HttpResponseMessage>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::`vftable';
  v12[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v12[1] = 1;
  v12[4] = 0;
  v12[5] = 0;
  *((_BYTE *)v12 + 48) = 0;
  *v12 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::`vftable';
  v12[7] = 0;
  v12[8] = 0;
  __ExceptionPtrCreate(v12 + 7);
  v12[9] = 0;
  v12[10] = 0;
  v12[11] = 0;
  *((_DWORD *)v12 + 24) = 0;
  *((_BYTE *)v12 + 100) = 0;
  *v12 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type::`vftable';
  v12[13] = 0;
  v12[14] = 0;
  *a1 = v12 + 2;
  if ( v12 != (_QWORD *)-16LL )
    (*(void (__fastcall **)(_QWORD *))(v12[2] + 8LL))(v12 + 2);
  *((_BYTE *)v12 + 304) = 0;
  Windows::Internal::CloudRequestor::HttpUtils::WhenAnyCancelOthers__ResumeCoro_1_winrt::Windows::Foundation::IAsyncOperationWithProgress_winrt::Windows::Web::Http::HttpResponseMessage_winrt::Windows::Web::Http::HttpProgress__winrt::Windows::Foundation::IAsyncOperationWithProgress_winrt::Windows::Web::Http::HttpResponseMessage_winrt::Windows::Web::Http::HttpProgress___(v12 + 16);
  if ( v17 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
  if ( v18 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  if ( *a4 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a4);
  return a1;
}

```

## disassembly

```asm
0x18004ce0c  mov     rax, rsp
0x18004ce0f  mov     [rax+20h], r9
0x18004ce13  mov     [rax+10h], rdx
0x18004ce17  mov     [rax+8], rcx
0x18004ce1b  push    rbp
0x18004ce1c  push    rbx
0x18004ce1d  push    rsi
0x18004ce1e  push    rdi
0x18004ce1f  push    r12
0x18004ce21  push    r13
0x18004ce23  push    r14
0x18004ce25  push    r15
0x18004ce27  lea     rbp, [rax-5Fh]
0x18004ce2b  sub     rsp, 88h
0x18004ce32  mov     r15, r9
0x18004ce35  mov     rbx, r8
0x18004ce38  mov     r14, rdx
0x18004ce3b  mov     r12, rcx
0x18004ce3e  xor     r13d, r13d
0x18004ce41  lea     rax, [rbp+57h+var_88]
0x18004ce45  mov     [rbp+57h+var_78], rax
0x18004ce49  mov     [rbp+57h+arg_10], r13b
0x18004ce4d  mov     rax, [r9]
0x18004ce50  mov     [r9], r13
0x18004ce53  mov     [rbp+57h+var_98], rax
0x18004ce57  lea     rax, [rbp+57h+var_98]
0x18004ce5b  mov     [rbp+57h+var_70], rax
0x18004ce5f  mov     ecx, 120h; Size
0x18004ce64  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ce69  mov     rdi, rax
0x18004ce6c  mov     [rbp+57h+var_80], rax
0x18004ce70  lea     rsi, [rax+80h]
0x18004ce77  mov     [rbp+57h+var_80], rsi
0x18004ce7b  lea     rax, [rbp+57h+arg_10]
0x18004ce7f  mov     [rsi+88h], rax
0x18004ce86  mov     [rsi+90h], rbx
0x18004ce8d  mov     rcx, [rbp+57h+var_98]
0x18004ce91  mov     [rbp+57h+var_98], r13
0x18004ce95  mov     [rsi+98h], rcx
0x18004ce9c  lea     rax, _lambda_29ca8c67725922f04d1500a82c8067c5_$_ResumeCoro$1__operator__
0x18004cea3  mov     [rsi], rax
0x18004cea6  mov     dword ptr [rsi+8], 10002h
0x18004cead  xor     edx, edx; Val
0x18004ceaf  lea     r8d, [r13+78h]; Size
0x18004ceb3  mov     rcx, rdi; void *
0x18004ceb6  call    memset_0
0x18004cebb  lea     rbx, [rdi+10h]
0x18004cebf  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@PEBV_lambda_29ca8c67725922f04d1500a82c8067c5_@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@UHttpResponseMessage@Http@Web@34@@experimental@std@@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,_lambda_29ca8c67725922f04d1500a82c8067c5_ const *,std::chrono::duration<__int64,std::ratio<1,10000000>>,winrt::Windows::Web::Http::HttpResponseMessage>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::`vftable'
0x18004cec6  mov     [rbx], rax
0x18004cec9  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18004ced0  mov     [rbx+8], rax
0x18004ced4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004cedb  mov     qword ptr [rdi+8], 1
0x18004cee3  mov     [rdi+20h], r13
0x18004cee7  mov     [rdi+28h], r13
0x18004ceeb  mov     [rdi+30h], r13b
0x18004ceef  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@UHttpProgress@Http@Web@78@@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::`vftable'
0x18004cef6  mov     [rdi], rax
0x18004cef9  lea     rcx, [rdi+38h]
0x18004cefd  mov     [rcx], r13
0x18004cf00  mov     [rcx+8], r13
0x18004cf04  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004cf0a  mov     [rdi+48h], r13
0x18004cf0e  mov     [rdi+50h], r13
0x18004cf12  mov     [rdi+58h], r13
0x18004cf16  xor     eax, eax
0x18004cf18  mov     [rdi+60h], eax
0x18004cf1b  mov     [rdi+64h], r13b
0x18004cf1f  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type::`vftable'
0x18004cf26  mov     [rdi], rax
0x18004cf29  mov     [rdi+68h], r13
0x18004cf2d  mov     [rdi+70h], r13
0x18004cf31  mov     [rbp+57h+var_88], rbx
0x18004cf35  test    rbx, rbx
0x18004cf38  jz      short loc_18004CF4A
0x18004cf3a  mov     rax, [rbx]
0x18004cf3d  mov     rcx, rbx
0x18004cf40  mov     rax, [rax+8]
0x18004cf44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf49  nop
0x18004cf4a  xor     eax, eax
0x18004cf4c  mov     [rsi+80h], al
0x18004cf52  mov     rcx, rsi
0x18004cf55  call    _lambda_29ca8c67725922f04d1500a82c8067c5_$_ResumeCoro$1__operator__
0x18004cf5a  nop
0x18004cf5b  cmp     [rbp+57h+var_98], r13
0x18004cf5f  jz      short loc_18004CF6A
0x18004cf61  lea     rcx, [rbp+57h+var_98]
0x18004cf65  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004cf6a  lea     rax, [rbp+57h+var_88]
0x18004cf6e  mov     [rbp+57h+var_70], rax
0x18004cf72  mov     rcx, [r14]
0x18004cf75  mov     [rbp+57h+var_90], rcx
0x18004cf79  test    rcx, rcx
0x18004cf7c  jz      short loc_18004CF8A
0x18004cf7e  mov     rax, [rcx]
0x18004cf81  mov     rax, [rax+8]
0x18004cf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf8a  lea     rax, [rbp+57h+var_90]
0x18004cf8e  mov     [rbp+57h+var_78], rax
0x18004cf92  mov     ecx, 150h; Size
0x18004cf97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004cf9c  mov     rbx, rax
0x18004cf9f  mov     [rbp+57h+var_80], rax
0x18004cfa3  lea     rdi, [rax+80h]
0x18004cfaa  mov     [rbp+57h+var_80], rdi
0x18004cfae  mov     rcx, [rbp+57h+var_90]
0x18004cfb2  mov     [rbp+57h+var_90], r13
0x18004cfb6  mov     [rdi+0B8h], rcx
0x18004cfbd  mov     rcx, [rbp+57h+var_88]
0x18004cfc1  mov     [rbp+57h+var_88], r13
0x18004cfc5  mov     [rdi+0C0h], rcx
0x18004cfcc  lea     rax, Windows__Internal__CloudRequestor__HttpUtils__WhenAnyCancelOthers$_ResumeCoro$1_winrt__Windows__Foundation__IAsyncOperationWithProgress_winrt__Windows__Web__Http__HttpResponseMessage_winrt__Windows__Web__Http__HttpProgress__winrt__Windows__Foundation__IAsyncOperationWithProgress_winrt__Windows__Web__Http__HttpResponseMessage_winrt__Windows__Web__Http__HttpProgress___
0x18004cfd3  mov     [rdi], rax
0x18004cfd6  mov     dword ptr [rdi+8], 10002h
0x18004cfdd  xor     edx, edx; Val
0x18004cfdf  lea     r8d, [rdx+78h]; Size
0x18004cfe3  mov     rcx, rbx; void *
0x18004cfe6  call    memset_0
0x18004cfeb  lea     rsi, [rbx+10h]
0x18004cfef  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@PEBV_lambda_29ca8c67725922f04d1500a82c8067c5_@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@UHttpResponseMessage@Http@Web@34@@experimental@std@@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,_lambda_29ca8c67725922f04d1500a82c8067c5_ const *,std::chrono::duration<__int64,std::ratio<1,10000000>>,winrt::Windows::Web::Http::HttpResponseMessage>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>>::`vftable'
0x18004cff6  mov     [rsi], rax
0x18004cff9  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18004d000  mov     [rsi+8], rax
0x18004d004  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004d00b  mov     qword ptr [rbx+8], 1
0x18004d013  mov     [rbx+20h], r13
0x18004d017  mov     [rbx+28h], r13
0x18004d01b  mov     [rbx+30h], r13b
0x18004d01f  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@UHttpProgress@Http@Web@78@@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Web::Http::HttpProgress>::`vftable'
0x18004d026  mov     [rbx], rax
0x18004d029  lea     rcx, [rbx+38h]
0x18004d02d  mov     [rcx], r13
0x18004d030  mov     [rcx+8], r13
0x18004d034  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004d03a  mov     [rbx+48h], r13
0x18004d03e  mov     [rbx+50h], r13
0x18004d042  mov     [rbx+58h], r13
0x18004d046  xor     eax, eax
0x18004d048  mov     [rbx+60h], eax
0x18004d04b  mov     [rbx+64h], r13b
0x18004d04f  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UHttpResponseMessage@Http@Web@Windows@winrt@@UHttpProgress@2345@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress>,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Web::Http::HttpResponseMessage,winrt::Windows::Web::Http::HttpProgress> const &>::promise_type::`vftable'
0x18004d056  mov     [rbx], rax
0x18004d059  mov     [rbx+68h], r13
0x18004d05d  mov     [rbx+70h], r13
0x18004d061  mov     [r12], rsi
0x18004d065  test    rsi, rsi
0x18004d068  jz      short loc_18004D07A
0x18004d06a  mov     rax, [rsi]
0x18004d06d  mov     rcx, rsi
0x18004d070  mov     rax, [rax+8]
0x18004d074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d079  nop
0x18004d07a  xor     eax, eax
0x18004d07c  mov     [rdi+0B0h], al
0x18004d082  mov     rcx, rdi
0x18004d085  call    Windows__Internal__CloudRequestor__HttpUtils__WhenAnyCancelOthers$_ResumeCoro$1_winrt__Windows__Foundation__IAsyncOperationWithProgress_winrt__Windows__Web__Http__HttpResponseMessage_winrt__Windows__Web__Http__HttpProgress__winrt__Windows__Foundation__IAsyncOperationWithProgress_winrt__Windows__Web__Http__HttpResponseMessage_winrt__Windows__Web__Http__HttpProgress___
0x18004d08a  nop
0x18004d08b  cmp     [rbp+57h+var_90], r13
0x18004d08f  jz      short loc_18004D09B
0x18004d091  lea     rcx, [rbp+57h+var_90]
0x18004d095  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004d09a  nop
0x18004d09b  cmp     [rbp+57h+var_88], r13
0x18004d09f  jz      short loc_18004D0AB
0x18004d0a1  lea     rcx, [rbp+57h+var_88]
0x18004d0a5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004d0aa  nop
0x18004d0ab  cmp     [r14], r13
0x18004d0ae  jz      short loc_18004D0B9
0x18004d0b0  mov     rcx, r14
0x18004d0b3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004d0b8  nop
0x18004d0b9  cmp     [r15], r13
0x18004d0bc  jz      short loc_18004D0C6
0x18004d0be  mov     rcx, r15
0x18004d0c1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004d0c6  mov     rax, r12
0x18004d0c9  add     rsp, 88h
0x18004d0d0  pop     r15
0x18004d0d2  pop     r14
0x18004d0d4  pop     r13
0x18004d0d6  pop     r12
0x18004d0d8  pop     rdi
0x18004d0d9  pop     rsi
0x18004d0da  pop     rbx
0x18004d0db  pop     rbp
0x18004d0dc  retn
```
