# ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z

- ea: `0x18001a69c`
- end: `0x18001a861`
- name: `??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z`
- size: `453`
- prototype: `signed __int64 *__fastcall(signed __int64, signed __int64 *, _QWORD **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800214d8`

## callees

- `0x1800045c9`
- `0x1800066dc`
- `0x180010550`
- `0x180017b60`
- `0x18001a69c`
- `0x180029010`

## string_xrefs

- `0x18001a6c4`: `Windows.Foundation.Uri`

## pseudocode

```c
signed __int64 *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
        signed __int64 a1,
        signed __int64 *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v9; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h]
  _DWORD *v11; // [rsp+48h] [rbp-28h] BYREF
  _DWORD v12[4]; // [rsp+50h] [rbp-20h] BYREF
  const wchar_t *v13; // [rsp+60h] [rbp-10h]
  signed __int64 v14; // [rsp+90h] [rbp+20h] BYREF
  signed __int64 v15; // [rsp+A8h] [rbp+38h] BYREF

  v14 = a1;
  v12[0] = 1;
  v12[1] = 22;
  v13 = L"Windows.Foundation.Uri";
  v11 = v12;
  v15 = 0;
  v9 = 0;
  v10 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v14,
    &v11,
    winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>,
    &v15);
  if ( (int)v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, &v9);
  v5 = v15;
  v14 = v15;
  if ( !v15
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, signed __int64 *))v5)(
          v5,
          winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    v9 = 0;
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, signed __int64 *))(*(_QWORD *)v5 + 48LL))(v5, **a3, &v15);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7, &v9);
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v15);
  _InterlockedIncrement64(&qword_180034AD8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
          v5,
          0) )
  {
    v5 = 0;
    v14 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180034AE0);
  }
  v15 = 0;
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, signed __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                                    + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
         **a3,
         &v15);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v9);
  *a2 = v15;
  _InterlockedDecrement64(&qword_180034AD8);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v14);
  return a2;
}

```

## disassembly

```asm
0x18001a69c  mov     [rsp-18h+arg_8], rbx
0x18001a6a1  mov     [rsp-18h+arg_0], rcx
0x18001a6a6  push    rbp
0x18001a6a7  push    rsi
0x18001a6a8  push    rdi
0x18001a6a9  mov     rbp, rsp
0x18001a6ac  sub     rsp, 70h
0x18001a6b0  mov     rsi, r8
0x18001a6b3  mov     rdi, rdx
0x18001a6b6  mov     [rbp+var_20], 1
0x18001a6bd  mov     [rbp+var_1C], 16h
0x18001a6c4  lea     rax, aWindowsFoundat; "Windows.Foundation.Uri"
0x18001a6cb  mov     [rbp+var_10], rax
0x18001a6cf  lea     rax, [rbp+var_20]
0x18001a6d3  mov     [rbp+var_28], rax
0x18001a6d7  mov     [rbp+arg_18], 0
0x18001a6df  mov     [rbp+var_40], 0
0x18001a6e6  xorps   xmm0, xmm0
0x18001a6e9  movdqu  [rbp+var_38], xmm0
0x18001a6ee  lea     r9, [rbp+arg_18]
0x18001a6f2  lea     r8, ??$guid_v@UIUriRuntimeClassFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18001a6f9  lea     rdx, [rbp+var_28]
0x18001a6fd  lea     rcx, [rbp+arg_0]
0x18001a701  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001a706  mov     ecx, dword ptr [rbp+arg_0]
0x18001a709  test    ecx, ecx
0x18001a70b  js      loc_18001A84B
0x18001a711  mov     rbx, [rbp+arg_18]
0x18001a715  mov     [rbp+arg_0], rbx
0x18001a719  test    rbx, rbx
0x18001a71c  jz      loc_18001A7E8
0x18001a722  mov     [rbp+arg_18], 0
0x18001a72a  mov     rax, [rbx]
0x18001a72d  lea     r8, [rbp+arg_18]
0x18001a731  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001a738  mov     rcx, rbx
0x18001a73b  mov     rax, [rax]
0x18001a73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a743  mov     rax, [rbp+arg_18]
0x18001a747  mov     [rbp+arg_18], rax
0x18001a74b  test    rax, rax
0x18001a74e  jz      loc_18001A7E8
0x18001a754  lea     rcx, [rbp+arg_18]
0x18001a758  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001a75d  lea     rax, qword_180034AD8
0x18001a764  mov     [rbp+var_48], rax
0x18001a768  lock inc cs:qword_180034AD8
0x18001a770  xor     eax, eax
0x18001a772  lock cmpxchg cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A, rbx; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18001a77b  jnz     short loc_18001A796
0x18001a77d  xor     ebx, ebx
0x18001a77f  mov     [rbp+arg_0], rbx
0x18001a783  lea     rdx, stru_180034AE0; ListEntry
0x18001a78a  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001a791  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001a796  mov     [rbp+arg_18], 0
0x18001a79e  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x18001a7a5  mov     [rbp+var_40], 0
0x18001a7ac  xorps   xmm0, xmm0
0x18001a7af  movdqu  [rbp+var_38], xmm0
0x18001a7b4  mov     rax, [rcx]
0x18001a7b7  mov     rdx, [rsi]
0x18001a7ba  lea     r8, [rbp+arg_18]
0x18001a7be  mov     rdx, [rdx]
0x18001a7c1  mov     rax, [rax+30h]
0x18001a7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7ca  test    eax, eax
0x18001a7cc  js      loc_18001A855
0x18001a7d2  mov     rax, [rbp+arg_18]
0x18001a7d6  mov     [rdi], rax
0x18001a7d9  lock dec cs:qword_180034AD8
0x18001a7e1  test    rbx, rbx
0x18001a7e4  jz      short loc_18001A82C
0x18001a7e6  jmp     short loc_18001A823
0x18001a7e8  mov     [rbp+arg_18], 0
0x18001a7f0  mov     [rbp+var_40], 0
0x18001a7f7  xorps   xmm0, xmm0
0x18001a7fa  movdqu  [rbp+var_38], xmm0
0x18001a7ff  mov     rax, [rbx]
0x18001a802  mov     rdx, [rsi]
0x18001a805  lea     r8, [rbp+arg_18]
0x18001a809  mov     rdx, [rdx]
0x18001a80c  mov     rcx, rbx
0x18001a80f  mov     rax, [rax+30h]
0x18001a813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a818  test    eax, eax
0x18001a81a  js      short loc_18001A83F
0x18001a81c  mov     rax, [rbp+arg_18]
0x18001a820  mov     [rdi], rax
0x18001a823  lea     rcx, [rbp+arg_0]
0x18001a827  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001a82c  mov     rax, rdi
0x18001a82f  mov     rbx, [rsp+70h+arg_8]
0x18001a837  add     rsp, 70h
0x18001a83b  pop     rdi
0x18001a83c  pop     rsi
0x18001a83d  pop     rbp
0x18001a83e  retn
0x18001a83f  lea     rdx, [rbp+var_40]
0x18001a843  mov     ecx, eax
0x18001a845  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001a84b  lea     rdx, [rbp+var_40]
0x18001a84f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001a855  lea     rdx, [rbp+var_40]
0x18001a859  mov     ecx, eax
0x18001a85b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
