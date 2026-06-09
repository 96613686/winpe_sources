# ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z

- ea: `0x140051c48`
- end: `0x140051d2e`
- name: `??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140051d34`

## callees

- `0x14000f804`
- `0x1400106d4`
- `0x140010855`
- `0x140051c48`
- `0x140052bf8`
- `0x14005d654`
- `0x14005fbb4`
- `0x140067010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(
        __int64 *a1,
        int a2)
{
  const struct winrt::impl::slim_source_location *v3; // rdx
  HANDLE EventW; // rsi
  _DWORD *v5; // rax
  char *v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _DWORD *v11; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+28h] [rbp-28h]
  int v13; // [rsp+38h] [rbp-18h] BYREF
  __int128 v14; // [rsp+40h] [rbp-10h]
  int v15; // [rsp+78h] [rbp+28h] BYREF
  _DWORD *v16; // [rsp+80h] [rbp+30h]

  v15 = a2;
  LODWORD(v11) = 0;
  v12 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    winrt::throw_last_error((winrt *)&v11, v3);
  v5 = operator new(0x20u);
  v16 = v5;
  v5[2] = 1;
  v6 = (char *)(v5 + 4);
  *((_QWORD *)v5 + 2) = EventW;
  v5[6] = 0;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v5 = ___7__delegate_U__AsyncOperationCompletedHandler__N_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation__N_Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation__N_234_I_Z__impl_winrt__6B_;
  v11 = v5;
  *(_QWORD *)&v12 = v5 + 4;
  v7 = *a1;
  v13 = 0;
  v14 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))(v7);
  winrt::check_hresult(&v15, v8, &v13);
  WaitForSingleObject_0(*(HANDLE *)v6, 0xFFFFFFFF);
  v9 = *((_DWORD *)v6 + 2);
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v11);
  return v9;
}

```

## disassembly

```asm
0x140051c48  mov     [rsp-18h+arg_0], rbx
0x140051c4d  mov     [rsp-18h+arg_18], rsi
0x140051c52  mov     [rsp-18h+arg_8], edx
0x140051c56  push    rbp
0x140051c57  push    rdi
0x140051c58  push    r14
0x140051c5a  mov     rbp, rsp
0x140051c5d  sub     rsp, 50h
0x140051c61  mov     r14, rcx
0x140051c64  mov     dword ptr [rbp+var_30], 0
0x140051c6b  xorps   xmm0, xmm0
0x140051c6e  movdqu  [rbp+var_28], xmm0
0x140051c73  xor     r9d, r9d; lpName
0x140051c76  xor     r8d, r8d; bInitialState
0x140051c79  lea     edi, [r9+1]
0x140051c7d  mov     edx, edi; bManualReset
0x140051c7f  xor     ecx, ecx; lpEventAttributes
0x140051c81  call    WINRT_IMPL_CreateEventW
0x140051c86  mov     rsi, rax
0x140051c89  test    rax, rax
0x140051c8c  jnz     short loc_140051C98
0x140051c8e  lea     rcx, [rbp+var_30]; this
0x140051c92  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
0x140051c98  mov     [rbp+var_30], rsi
0x140051c9c  xor     ebx, ebx
0x140051c9e  mov     qword ptr [rbp+var_28], rbx
0x140051ca2  lea     ecx, [rbx+20h]; Size
0x140051ca5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140051caa  mov     rdx, rax
0x140051cad  mov     [rbp+arg_10], rax
0x140051cb1  mov     [rax+8], edi
0x140051cb4  lea     rdi, [rax+10h]
0x140051cb8  mov     [rdi], rsi
0x140051cbb  mov     [rdi+8], ebx
0x140051cbe  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140051cc5  lea     rax, ??_7?$delegate@U?$AsyncOperationCompletedHandler@_N@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@_N@234@I@Z@@impl@winrt@@6B@
0x140051ccc  mov     [rdx], rax
0x140051ccf  mov     [rbp+var_30], rdx
0x140051cd3  mov     qword ptr [rbp+var_28], rdi
0x140051cd7  mov     rcx, [r14]
0x140051cda  mov     [rbp+var_18], ebx
0x140051cdd  xorps   xmm0, xmm0
0x140051ce0  movdqu  [rbp+var_10], xmm0
0x140051ce5  mov     rax, [rcx]
0x140051ce8  mov     rax, [rax+30h]
0x140051cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051cf1  lea     r8, [rbp+var_18]
0x140051cf5  mov     edx, eax
0x140051cf7  lea     rcx, [rbp+arg_8]
0x140051cfb  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140051d00  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140051d03  mov     rcx, [rdi]; hHandle
0x140051d06  call    WaitForSingleObject_0
0x140051d0b  mov     ebx, [rdi+8]
0x140051d0e  lea     rcx, [rbp+var_30]; this
0x140051d12  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x140051d17  mov     eax, ebx
0x140051d19  lea     r11, [rsp+50h+var_s0]
0x140051d1e  mov     rbx, [r11+20h]
0x140051d22  mov     rsi, [r11+38h]
0x140051d26  mov     rsp, r11
0x140051d29  pop     r14
0x140051d2b  pop     rdi
0x140051d2c  pop     rbp
0x140051d2d  retn
```
