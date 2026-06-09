# ??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z

- ea: `0x1400238dc`
- end: `0x1400239ed`
- name: `??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140024f10`

## callees

- `0x140003539`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14001f304`
- `0x1400238dc`
- `0x140023f44`
- `0x140024374`
- `0x140029010`

## string_xrefs

- `0x1400238f6`: `Windows.System.Threading.ThreadPoolTimer`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::call<_lambda_b19cf72fe9674443383aa89d5c22450b_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.System.Threading.ThreadPoolTimer";
  v7[1] = 40;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::System::Threading::IThreadPoolTimerStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_140047158;
    _InterlockedIncrement64(&qword_140047158);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_140047160);
    }
    _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>);
    _InterlockedDecrement64(&qword_140047158);
  }
  else
  {
    _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x1400238dc  mov     [rsp-18h+arg_8], rbx
0x1400238e1  mov     [rsp-18h+arg_0], rcx
0x1400238e6  push    rbp
0x1400238e7  push    rsi
0x1400238e8  push    rdi
0x1400238e9  mov     rbp, rsp
0x1400238ec  sub     rsp, 60h
0x1400238f0  mov     rsi, r8
0x1400238f3  mov     rbx, rdx
0x1400238f6  lea     rax, aWindowsSystemT; "Windows.System.Threading.ThreadPoolTime"...
0x1400238fd  mov     [rbp+var_38], rax
0x140023901  mov     [rbp+var_30], 28h ; '('
0x140023909  lea     rdx, [rbp+var_38]
0x14002390d  lea     rcx, [rbp+var_28]
0x140023911  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x140023916  lea     rdx, [rbp+var_28]
0x14002391a  lea     rcx, [rbp+arg_0]
0x14002391e  call    ??$get_activation_factory@UIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@winrt@@YA?AUIThreadPoolTimerStatics@Threading@System@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::System::Threading::IThreadPoolTimerStatics>(winrt::param::hstring const &)
0x140023923  nop
0x140023924  mov     rdi, [rbp+arg_0]
0x140023928  test    rdi, rdi
0x14002392b  jz      loc_1400239C0
0x140023931  mov     [rbp+arg_18], 0
0x140023939  mov     rax, [rdi]
0x14002393c  lea     r8, [rbp+arg_18]
0x140023940  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x140023947  mov     rcx, rdi
0x14002394a  mov     rax, [rax]
0x14002394d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023952  mov     rax, [rbp+arg_18]
0x140023956  mov     [rbp+arg_18], rax
0x14002395a  test    rax, rax
0x14002395d  jz      short loc_1400239C0
0x14002395f  lea     rcx, [rbp+arg_18]
0x140023963  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140023968  lea     rax, qword_140047158
0x14002396f  mov     [rbp+arg_18], rax
0x140023973  lock inc cs:qword_140047158
0x14002397b  xor     eax, eax
0x14002397d  lock cmpxchg cs:??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x140023986  jnz     short loc_1400239A3
0x140023988  mov     [rbp+arg_0], 0
0x140023990  lea     rdx, stru_140047160; ListEntry
0x140023997  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x14002399e  call    WINRT_IMPL_InterlockedPushEntrySList
0x1400239a3  lea     r8, ??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x1400239aa  mov     rdx, rbx
0x1400239ad  mov     rcx, rsi
0x1400239b0  call    ??R_lambda_b19cf72fe9674443383aa89d5c22450b_@@QEBA@AEBUIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@Z; _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(winrt::Windows::System::Threading::IThreadPoolTimerStatics const &)
0x1400239b5  nop
0x1400239b6  lock dec cs:qword_140047158
0x1400239be  jmp     short loc_1400239D0
0x1400239c0  lea     r8, [rbp+arg_0]
0x1400239c4  mov     rdx, rbx
0x1400239c7  mov     rcx, rsi
0x1400239ca  call    ??R_lambda_b19cf72fe9674443383aa89d5c22450b_@@QEBA@AEBUIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@Z; _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(winrt::Windows::System::Threading::IThreadPoolTimerStatics const &)
0x1400239cf  nop
0x1400239d0  lea     rcx, [rbp+arg_0]
0x1400239d4  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1400239d9  mov     rax, rbx
0x1400239dc  mov     rbx, [rsp+60h+arg_8]
0x1400239e4  add     rsp, 60h
0x1400239e8  pop     rdi
0x1400239e9  pop     rsi
0x1400239ea  pop     rbp
0x1400239eb  retn
```
