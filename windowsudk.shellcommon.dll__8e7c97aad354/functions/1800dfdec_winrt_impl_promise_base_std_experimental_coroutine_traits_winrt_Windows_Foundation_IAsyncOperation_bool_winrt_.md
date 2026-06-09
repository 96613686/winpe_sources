# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::Rect>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::Cancel(void)

- ea: `0x1800dfdec`
- end: `0x1800dfefa`
- name: `?Cancel@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@URect@234@@experimental@std@@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800dfdc0`

## callees

- `0x18000ba10`
- `0x18000ba20`
- `0x180011e64`
- `0x180062d18`
- `0x1800dfdec`
- `0x1800dff28`
- `0x1800dff64`
- `0x18015e123`
- `0x18015e13b`
- `0x1804a2010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800dfe6f`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800dfe6f`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800dfe86`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800dfe86`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800dfe90`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800dfe90`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800dfe5a`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800dfe5a`

## pseudocode

```c
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<bool>,winrt::Windows::Foundation::Rect>::promise_type,winrt::Windows::Foundation::IAsyncOperation<bool>,void>::Cancel(
        RTL_SRWLOCK *a1)
{
  PVOID Ptr; // rbx
  PVOID v3; // rdi
  __int64 v4; // rcx
  RTL_SRWLOCK *v5; // rax
  PVOID v6; // [rsp+20h] [rbp-50h] BYREF
  __int128 v7; // [rsp+28h] [rbp-48h] BYREF
  int v8; // [rsp+38h] [rbp-38h] BYREF
  __int128 v9; // [rsp+40h] [rbp-30h]
  _BYTE v10[32]; // [rsp+50h] [rbp-20h] BYREF

  Ptr = 0;
  v6 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 9);
  v3 = 0;
  if ( !(unsigned int)std::_Atomic_storage<unsigned int,4>::load(&a1[12], 0) )
  {
    std::_Atomic_storage<enum winrt::Windows::Foundation::AsyncStatus,4>::store(v4, 2);
    v8 = 0;
    v9 = 0;
    winrt::hresult_error::hresult_error(v10, (unsigned int)winrt::impl::error_canceled, &v8);
    v7 = 0;
    __ExceptionPtrCreate(&v7);
    __ExceptionPtrCopyException(&v7, v10, &TI2_AUhresult_canceled_winrt__);
    winrt::hresult_error::~hresult_error((winrt::hresult_error *)v10);
    __ExceptionPtrAssign(&a1[7], &v7);
    __ExceptionPtrDestroy(&v7);
    v5 = a1 + 11;
    if ( &v6 != (PVOID *)&a1[11] )
    {
      Ptr = v5->Ptr;
      v5->Ptr = 0;
      v6 = Ptr;
      v3 = Ptr;
    }
  }
  ReleaseSRWLockExclusive_0(a1 + 9);
  if ( v3 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 24LL))(Ptr);
  winrt::cancellable_promise::cancel((winrt::cancellable_promise *)&a1[4]);
  if ( v3 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v6);
}

```

## disassembly

```asm
0x1800dfdec  mov     [rsp-18h+arg_8], rbx
0x1800dfdf1  mov     [rsp-18h+arg_10], rsi
0x1800dfdf6  push    rbp
0x1800dfdf7  push    rdi
0x1800dfdf8  push    r14
0x1800dfdfa  mov     rbp, rsp
0x1800dfdfd  sub     rsp, 70h
0x1800dfe01  mov     rsi, rcx
0x1800dfe04  xor     ebx, ebx
0x1800dfe06  mov     [rbp+var_50], rbx
0x1800dfe0a  add     rcx, 48h ; 'H'; SRWLock
0x1800dfe0e  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800dfe13  lea     rcx, [rsi+60h]
0x1800dfe17  xor     edi, edi
0x1800dfe19  xor     edx, edx
0x1800dfe1b  call    ?load@?$_Atomic_storage@I$03@std@@QEBAIW4memory_order@2@@Z; std::_Atomic_storage<uint,4>::load(std::memory_order)
0x1800dfe20  test    eax, eax
0x1800dfe22  jnz     loc_1800DFEB0
0x1800dfe28  lea     edx, [rbx+2]
0x1800dfe2b  call    ?store@?$_Atomic_storage@W4AsyncStatus@Foundation@Windows@winrt@@$03@std@@QEAAXW4AsyncStatus@Foundation@Windows@winrt@@W4memory_order@2@@Z; std::_Atomic_storage<winrt::Windows::Foundation::AsyncStatus,4>::store(winrt::Windows::Foundation::AsyncStatus,std::memory_order)
0x1800dfe30  mov     [rbp+var_38], ebx
0x1800dfe33  xorps   xmm0, xmm0
0x1800dfe36  movdqu  [rbp+var_30], xmm0
0x1800dfe3b  lea     r8, [rbp+var_38]
0x1800dfe3f  mov     edx, cs:?error_canceled@impl@winrt@@3Uhresult@2@B; winrt::hresult const winrt::impl::error_canceled
0x1800dfe45  lea     rcx, [rbp+var_20]
0x1800dfe49  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800dfe4e  xorps   xmm0, xmm0
0x1800dfe51  movdqu  [rbp+var_48], xmm0
0x1800dfe56  lea     rcx, [rbp+var_48]
0x1800dfe5a  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800dfe60  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x1800dfe67  lea     rdx, [rbp+var_20]
0x1800dfe6b  lea     rcx, [rbp+var_48]
0x1800dfe6f  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800dfe75  lea     rcx, [rbp+var_20]; this
0x1800dfe79  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x1800dfe7e  lea     rcx, [rsi+38h]
0x1800dfe82  lea     rdx, [rbp+var_48]
0x1800dfe86  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800dfe8c  lea     rcx, [rbp+var_48]
0x1800dfe90  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800dfe96  lea     rax, [rsi+58h]
0x1800dfe9a  lea     rcx, [rbp+var_50]
0x1800dfe9e  cmp     rcx, rax
0x1800dfea1  jz      short loc_1800DFEB0
0x1800dfea3  mov     rbx, [rax]
0x1800dfea6  mov     [rax], rdi
0x1800dfea9  mov     [rbp+var_50], rbx
0x1800dfead  mov     rdi, rbx
0x1800dfeb0  lea     rcx, [rsi+48h]; SRWLock
0x1800dfeb4  call    ReleaseSRWLockExclusive_0
0x1800dfeb9  test    rdi, rdi
0x1800dfebc  jz      short loc_1800DFECD
0x1800dfebe  mov     rax, [rbx]
0x1800dfec1  mov     rcx, rbx
0x1800dfec4  mov     rax, [rax+18h]
0x1800dfec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfecd  lea     rcx, [rsi+20h]; this
0x1800dfed1  call    ?cancel@cancellable_promise@winrt@@QEAAXXZ; winrt::cancellable_promise::cancel(void)
0x1800dfed6  test    rdi, rdi
0x1800dfed9  jz      short loc_1800DFEE5
0x1800dfedb  lea     rcx, [rbp+var_50]
0x1800dfedf  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800dfee4  nop
0x1800dfee5  lea     r11, [rsp+70h+var_s0]
0x1800dfeea  mov     rbx, [r11+28h]
0x1800dfeee  mov     rsi, [r11+30h]
0x1800dfef2  mov     rsp, r11
0x1800dfef5  pop     r14
0x1800dfef7  pop     rdi
0x1800dfef8  pop     rbp
0x1800dfef9  retn
```
