# XamlUI::OnLayoutUpdated(winrt::Windows::Foundation::IInspectable const &,winrt::Windows::Foundation::IInspectable const &)

- ea: `0x140024f10`
- end: `0x14002502a`
- name: `?OnLayoutUpdated@XamlUI@@AEAAXAEBUIInspectable@Foundation@Windows@winrt@@0@Z`
- size: `282`
- prototype: `void __fastcall(XamlUI *__hidden this, const struct IInspectable *, const struct IInspectable *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002760`
- `0x140009ee0`
- `0x14000ccdc`
- `0x14001f32c`
- `0x14002364c`
- `0x1400238dc`
- `0x140024374`
- `0x140024f10`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall XamlUI::OnLayoutUpdated(XamlUI *this, const struct IInspectable *a2, const struct IInspectable *a3)
{
  __int64 v4; // rdi
  char *v5; // rax
  void (__fastcall ***v6)(_QWORD, __int64 *, __int64 **); // rcx
  _QWORD *v7; // rdx
  __int64 *v8; // rbx
  __int64 v9; // rax
  const char *v10; // r9
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  char v12[8]; // [rsp+28h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _QWORD *v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v16 = 250;
  std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(v12, &v16, a3);
  v4 = *(_QWORD *)this;
  try
  {
    v5 = (char *)operator new(0x18u);
    winrt::impl::implements_delegate_base::implements_delegate_base((winrt::impl::implements_delegate_base *)(v5 + 8));
    v7[2] = v4;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *v7 = off_14002B5A8;
    v15 = v7;
    v13[0] = &v15;
    v13[1] = v12;
    v16 = (__int64)&qword_140047158;
    _InterlockedIncrement64(&qword_140047158);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> )
    {
      _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(
        v13,
        &v11,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>);
      _InterlockedDecrement64(&qword_140047158);
    }
    else
    {
      _InterlockedDecrement64(&qword_140047158);
      winrt::impl::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::call<_lambda_b19cf72fe9674443383aa89d5c22450b_ &>(
        v6,
        (__int64)&v11,
        (__int64)v13);
    }
    v8 = (__int64 *)((char *)this + 80);
    if ( v8 != &v11 )
    {
      if ( *v8 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
      v9 = v11;
      v11 = 0;
      *v8 = v9;
    }
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
    if ( v15 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v15);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA6,
      (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
      v10);
  }
}

```

## disassembly

```asm
0x140024f10  mov     rax, rsp
0x140024f13  mov     [rax+10h], rbx
0x140024f17  push    rdi
0x140024f18  sub     rsp, 40h
0x140024f1c  mov     rbx, rcx
0x140024f1f  mov     qword ptr [rax+20h], 0FAh
0x140024f27  lea     rdx, [rax+20h]
0x140024f2b  lea     rcx, [rax-20h]
0x140024f2f  call    ??$?0_JU?$ratio@$00$0DOI@@std@@$0A@@?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@12@@Z; std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x140024f34  mov     rdi, [rbx]
0x140024f37  mov     ecx, 18h; Size
0x140024f3c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140024f41  mov     rdx, rax
0x140024f44  lea     rcx, [rax+8]; this
0x140024f48  call    ??0implements_delegate_base@impl@winrt@@QEAA@XZ; winrt::impl::implements_delegate_base::implements_delegate_base(void)
0x140024f4d  mov     [rdx+10h], rdi
0x140024f51  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x140024f58  lea     rax, off_14002B5A8
0x140024f5f  mov     [rdx], rax
0x140024f62  mov     [rsp+48h+arg_0], rdx
0x140024f67  lea     rax, [rsp+48h+arg_0]
0x140024f6c  mov     [rsp+48h+var_18], rax
0x140024f71  lea     rax, [rsp+48h+var_20]
0x140024f76  mov     [rsp+48h+var_10], rax
0x140024f7b  lea     rax, qword_140047158
0x140024f82  mov     [rsp+48h+arg_18], rax
0x140024f87  lock inc cs:qword_140047158
0x140024f8f  cmp     cs:??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x140024f97  jz      short loc_140024FBA
0x140024f99  lea     r8, ??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x140024fa0  lea     rdx, [rsp+48h+var_28]
0x140024fa5  lea     rcx, [rsp+48h+var_18]
0x140024faa  call    ??R_lambda_b19cf72fe9674443383aa89d5c22450b_@@QEBA@AEBUIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@Z; _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(winrt::Windows::System::Threading::IThreadPoolTimerStatics const &)
0x140024faf  nop
0x140024fb0  lock dec cs:qword_140047158
0x140024fb8  jmp     short loc_140024FD1
0x140024fba  lock dec cs:qword_140047158
0x140024fc2  lea     r8, [rsp+48h+var_18]
0x140024fc7  lea     rdx, [rsp+48h+var_28]
0x140024fcc  call    ??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z
0x140024fd1  add     rbx, 50h ; 'P'
0x140024fd5  lea     rax, [rsp+48h+var_28]
0x140024fda  cmp     rbx, rax
0x140024fdd  jz      short loc_140024FFE
0x140024fdf  cmp     qword ptr [rbx], 0
0x140024fe3  jz      short loc_140024FED
0x140024fe5  mov     rcx, rbx
0x140024fe8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x140024fed  mov     rax, [rsp+48h+var_28]
0x140024ff2  mov     [rsp+48h+var_28], 0
0x140024ffb  mov     [rbx], rax
0x140024ffe  lea     rcx, [rsp+48h+var_28]
0x140025003  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x140025008  nop
0x140025009  cmp     [rsp+48h+arg_0], 0
0x14002500f  jz      short loc_14002501C
0x140025011  lea     rcx, [rsp+48h+arg_0]
0x140025016  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x14002501b  nop
0x14002501c  jmp     short $+2
0x14002501e  mov     rbx, [rsp+48h+arg_8]
0x140025023  add     rsp, 40h
0x140025027  pop     rdi
0x140025028  retn
```
