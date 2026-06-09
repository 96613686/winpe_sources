# Windows::Internal::CloudRequestor::CommonHttpInterface::ProcessRequestAsync(winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>)

- ea: `0x180054b50`
- end: `0x180054d3d`
- name: `?ProcessRequestAsync@CommonHttpInterface@CloudRequestor@Internal@Windows@@UEAA?AU?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@4winrt@@Uhstring@7@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@std@@@Z`
- size: `493`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002810`
- `0x180002840`
- `0x180003384`
- `0x1800034f7`
- `0x1800035ab`
- `0x180052980`
- `0x180054b50`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180054c50`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180054c50`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180054d36`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180054d36`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::Internal::CloudRequestor::CommonHttpInterface::ProcessRequestAsync(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3,
        _QWORD *a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rdi
  volatile signed __int32 *v10; // rax
  __int64 v11; // rbx
  volatile signed __int32 *v12; // rbx
  int v13; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v15; // rbx

  v8 = operator new(0x7F0u);
  v9 = (__int64)(v8 + 14);
  v8[249] = a1;
  v10 = *a3;
  *a3 = 0;
  *(_QWORD *)(v9 + 1888) = v10;
  *(_QWORD *)(v9 + 1896) = 0;
  *(_QWORD *)(v9 + 1904) = 0;
  *(_QWORD *)(v9 + 1896) = *a4;
  *(_QWORD *)(v9 + 1904) = a4[1];
  *a4 = 0;
  a4[1] = 0;
  *(_QWORD *)v9 = Windows::Internal::CloudRequestor::CommonHttpInterface::ProcessRequestAsync__ResumeCoro_1;
  *(_DWORD *)(v9 + 8) = 65538;
  v11 = v9 - 112;
  memset_0((void *)(v9 - 112), 0, 0x70u);
  *(_QWORD *)(v11 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,Windows::Internal::CloudRequestor::CommonHttpInterface *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>>::`vftable';
  *(_QWORD *)(v11 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(v11 + 8) = 1;
  *(_QWORD *)(v11 + 32) = 0;
  *(_QWORD *)(v11 + 40) = 0;
  *(_BYTE *)(v11 + 48) = 0;
  *(_QWORD *)v11 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,Windows::Internal::CloudRequestor::CommonHttpInterface *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,void>::`vftable';
  *(_QWORD *)(v11 + 56) = 0;
  *(_QWORD *)(v11 + 64) = 0;
  __ExceptionPtrCreate((void *)(v9 - 112 + 56));
  *(_QWORD *)(v11 + 72) = 0;
  *(_QWORD *)(v11 + 80) = 0;
  *(_QWORD *)(v11 + 88) = 0;
  *(_DWORD *)(v11 + 96) = 0;
  *(_BYTE *)(v11 + 100) = 0;
  *(_QWORD *)v11 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,Windows::Internal::CloudRequestor::CommonHttpInterface *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>>::promise_type::`vftable';
  *(_QWORD *)(v11 + 104) = 0;
  *a2 = v9 - 112 + 16;
  if ( v9 != 96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 16) + 8LL))(v11 + 16);
  *(_BYTE *)(v9 + 1872) = 0;
  Windows::Internal::CloudRequestor::CommonHttpInterface::ProcessRequestAsync__ResumeCoro_1(v9);
  v12 = *a3;
  if ( *a3 )
  {
    v13 = _InterlockedDecrement(v12 + 6);
    if ( v13 )
    {
      if ( v13 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v12);
    }
    *a3 = 0;
  }
  v15 = (volatile signed __int32 *)a4[1];
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180054b50  mov     rax, rsp
0x180054b53  mov     [rax+8], rbx
0x180054b57  mov     [rax+20h], r9
0x180054b5b  mov     [rax+18h], r8
0x180054b5f  mov     [rax+10h], rdx
0x180054b63  push    rbp
0x180054b64  push    rsi
0x180054b65  push    rdi
0x180054b66  push    r12
0x180054b68  push    r13
0x180054b6a  push    r14
0x180054b6c  push    r15
0x180054b6e  sub     rsp, 40h
0x180054b72  mov     rax, cs:__security_cookie
0x180054b79  xor     rax, rsp
0x180054b7c  mov     [rsp+78h+var_40], rax
0x180054b81  mov     r14, r9
0x180054b84  mov     rsi, r8
0x180054b87  mov     rbp, rdx
0x180054b8a  mov     rbx, rcx
0x180054b8d  mov     r13d, 750h
0x180054b93  lea     rcx, [r13+0A0h]; Size
0x180054b9a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054b9f  mov     [rsp+78h+var_58], rax
0x180054ba4  mov     r8d, 70h ; 'p'; Size
0x180054baa  lea     rdi, [r8+rax]
0x180054bae  mov     [rsp+78h+var_58], rdi
0x180054bb3  mov     [rdi+r13+8], rbx
0x180054bb8  mov     rax, [rsi]
0x180054bbb  xor     r12d, r12d
0x180054bbe  mov     [rsi], r12
0x180054bc1  mov     [rdi+r13+10h], rax
0x180054bc6  mov     [rdi+r13+18h], r12
0x180054bcb  mov     [rdi+r13+20h], r12
0x180054bd0  mov     rax, [r14]
0x180054bd3  mov     [rdi+r13+18h], rax
0x180054bd8  mov     rax, [r14+8]
0x180054bdc  mov     [rdi+r13+20h], rax
0x180054be1  mov     [r14], r12
0x180054be4  mov     [r14+8], r12
0x180054be8  lea     rax, Windows__Internal__CloudRequestor__CommonHttpInterface__ProcessRequestAsync$_ResumeCoro$1
0x180054bef  mov     [rdi], rax
0x180054bf2  mov     dword ptr [rdi+8], 10002h
0x180054bf9  lea     rbx, [rdi-70h]
0x180054bfd  xor     edx, edx; Val
0x180054bff  mov     rcx, rbx; void *
0x180054c02  call    memset_0
0x180054c07  lea     r15, [rbx+10h]
0x180054c0b  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCommonHttpInterface@CloudRequestor@Internal@3@Uhstring@4@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,Windows::Internal::CloudRequestor::CommonHttpInterface *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>>::`vftable'
0x180054c12  mov     [r15], rax
0x180054c15  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCloudRequestorInterface@@UWebAccount@Credentials@Security@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,CloudRequestorInterface *,winrt::Windows::Security::Credentials::WebAccount>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180054c1c  mov     [r15+8], rax
0x180054c20  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180054c27  mov     qword ptr [rbx+8], 1
0x180054c2f  mov     [rbx+20h], r12
0x180054c33  mov     [rbx+28h], r12
0x180054c37  mov     [rbx+30h], r12b
0x180054c3b  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCommonHttpInterface@CloudRequestor@Internal@3@Uhstring@4@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,Windows::Internal::CloudRequestor::CommonHttpInterface *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,void>::`vftable'
0x180054c42  mov     [rbx], rax
0x180054c45  lea     rcx, [rbx+38h]
0x180054c49  mov     [rcx], r12
0x180054c4c  mov     [rcx+8], r12
0x180054c50  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180054c56  mov     [rbx+48h], r12
0x180054c5a  mov     [rbx+50h], r12
0x180054c5e  mov     [rbx+58h], r12
0x180054c62  xor     eax, eax
0x180054c64  mov     [rbx+60h], eax
0x180054c67  mov     [rbx+64h], r12b
0x180054c6b  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UResponseDetails@CloudRequestor@Internal@Windows@winrt@@@Foundation@Windows@winrt@@PEAVCommonHttpInterface@CloudRequestor@Internal@3@Uhstring@4@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::CloudRequestor::ResponseDetails>,Windows::Internal::CloudRequestor::CommonHttpInterface *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>>::promise_type::`vftable'
0x180054c72  mov     [rbx], rax
0x180054c75  mov     [rbx+68h], r12
0x180054c79  mov     [rbp+0], r15
0x180054c7d  test    r15, r15
0x180054c80  jz      short loc_180054C92
0x180054c82  mov     rax, [r15]
0x180054c85  mov     rcx, r15
0x180054c88  mov     rax, [rax+8]
0x180054c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c91  nop
0x180054c92  xor     eax, eax
0x180054c94  mov     [rdi+r13], al
0x180054c98  mov     rcx, rdi
0x180054c9b  call    Windows__Internal__CloudRequestor__CommonHttpInterface__ProcessRequestAsync$_ResumeCoro$1
0x180054ca0  nop
0x180054ca1  mov     rbx, [rsi]
0x180054ca4  or      edi, 0FFFFFFFFh
0x180054ca7  test    rbx, rbx
0x180054caa  jz      short loc_180054CCE
0x180054cac  mov     eax, edi
0x180054cae  lock xadd [rbx+18h], eax
0x180054cb3  sub     eax, 1
0x180054cb6  jnz     short loc_180054D32
0x180054cb8  nop
0x180054cb9  call    WINRT_IMPL_GetProcessHeap
0x180054cbe  mov     rcx, rax; hHeap
0x180054cc1  mov     r8, rbx; lpMem
0x180054cc4  xor     edx, edx; dwFlags
0x180054cc6  call    WINRT_IMPL_HeapFree
0x180054ccb  mov     [rsi], r12
0x180054cce  mov     rbx, [r14+8]
0x180054cd2  test    rbx, rbx
0x180054cd5  jz      short loc_180054D0A
0x180054cd7  mov     eax, edi
0x180054cd9  lock xadd [rbx+8], eax
0x180054cde  add     eax, edi
0x180054ce0  jnz     short loc_180054D0A
0x180054ce2  mov     rax, [rbx]
0x180054ce5  mov     rcx, rbx
0x180054ce8  mov     rax, [rax]
0x180054ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054cf0  mov     eax, edi
0x180054cf2  lock xadd [rbx+0Ch], eax
0x180054cf7  add     eax, edi
0x180054cf9  jnz     short loc_180054D0A
0x180054cfb  mov     rax, [rbx]
0x180054cfe  mov     rcx, rbx
0x180054d01  mov     rax, [rax+8]
0x180054d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d0a  mov     rax, rbp
0x180054d0d  mov     rcx, [rsp+78h+var_40]
0x180054d12  xor     rcx, rsp; StackCookie
0x180054d15  call    __security_check_cookie
0x180054d1a  mov     rbx, [rsp+78h+arg_0]
0x180054d22  add     rsp, 40h
0x180054d26  pop     r15
0x180054d28  pop     r14
0x180054d2a  pop     r13
0x180054d2c  pop     r12
0x180054d2e  pop     rdi
0x180054d2f  pop     rsi
0x180054d30  pop     rbp
0x180054d31  retn
0x180054d32  test    eax, eax
0x180054d34  jns     short loc_180054CCB
0x180054d36  call    cs:__imp_abort
```
