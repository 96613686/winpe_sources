# ??$call@AEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@winrt@@QEAA@AEBUhstring@param@6@@Z@@?$factory_cache_entry@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18001e83c`
- end: `0x18001e982`
- name: `??$call@AEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@winrt@@QEAA@AEBUhstring@param@6@@Z@@?$factory_cache_entry@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@2@QEAA@AEBUhstring@param@2@@Z@@Z`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e988`

## callees

- `0x180010c3c`
- `0x180012040`
- `0x18001a320`
- `0x18001aec0`
- `0x18001bbf0`
- `0x18001e83c`
- `0x18001e9f4`
- `0x180022389`
- `0x18002e010`

## string_xrefs

- `0x18001e85c`: `Windows.UI.Composition.CompositionEffectSourceParameter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ___call_AEAV_lambda_20____0___0CompositionEffectSourceParameter_Composition_UI_Windows_winrt__QEAA_AEBUhstring_param_6__Z____factory_cache_entry_UCompositionEffectSourceParameter_Composition_UI_Windows_winrt__UICompositionEffectSourceParameterFactory_2345__impl_winrt__QEAA_A_PAEAV_lambda_20____0___0CompositionEffectSourceParameter_Composition_UI_Windows_2_QEAA_AEBUhstring_param_2__Z__Z(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rdi
  int v7; // [rsp+28h] [rbp-38h] BYREF
  const char *v8; // [rsp+30h] [rbp-30h]
  __int64 v9; // [rsp+38h] [rbp-28h]
  _QWORD v10[4]; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v11; // [rsp+80h] [rbp+20h] BYREF
  __int64 *v12; // [rsp+98h] [rbp+38h] BYREF

  v11 = a1;
  winrt::param::hstring::create_string_reference(
    (winrt::param::hstring *)v10,
    L"Windows.UI.Composition.CompositionEffectSourceParameter",
    0x37u);
  v12 = 0;
  v7 = 6172;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
  v9 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    v10,
    (__int64)winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>,
    (__int64)&v12);
  winrt::check_hresult(&v11, (unsigned int)v11, &v7);
  v5 = v12;
  v11 = v12;
  if ( v12
    && (v12 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v12),
        v12) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
    v12 = &qword_18003F3D8;
    _InterlockedIncrement64(&qword_18003F3D8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>,
            (signed __int64)v5,
            0) )
    {
      v11 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    `winrt::Windows::UI::Composition::CompositionEffectSourceParameter::CompositionEffectSourceParameter'::`1'::_lambda_20__::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>);
    _InterlockedDecrement64(&qword_18003F3D8);
  }
  else
  {
    `winrt::Windows::UI::Composition::CompositionEffectSourceParameter::CompositionEffectSourceParameter'::`1'::_lambda_20__::operator()(
      a3,
      a2,
      &v11);
  }
  winrt::Windows::UI::Composition::ICompositionEffectFactory::~ICompositionEffectFactory((winrt::Windows::UI::Composition::ICompositionEffectFactory *)&v11);
  return a2;
}

```

## disassembly

```asm
0x18001e83c  mov     [rsp-18h+arg_8], rbx
0x18001e841  mov     [rsp-18h+arg_0], rcx
0x18001e846  push    rbp
0x18001e847  push    rsi
0x18001e848  push    rdi
0x18001e849  mov     rbp, rsp
0x18001e84c  sub     rsp, 60h
0x18001e850  mov     rsi, r8
0x18001e853  mov     rbx, rdx
0x18001e856  mov     r8d, 37h ; '7'; unsigned __int64
0x18001e85c  lea     rdx, aWindowsUiCompo; "Windows.UI.Composition.CompositionEffec"...
0x18001e863  lea     rcx, [rbp+var_20]; this
0x18001e867  call    ?create_string_reference@hstring@param@winrt@@AEAAXQEBG_K@Z; winrt::param::hstring::create_string_reference(ushort const * const,unsigned __int64)
0x18001e86c  mov     [rbp+arg_18], 0
0x18001e874  mov     [rbp+var_38], 181Ch
0x18001e87b  lea     rax, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001e882  mov     [rbp+var_30], rax
0x18001e886  mov     [rbp+var_28], 0
0x18001e88e  lea     r9, [rbp+arg_18]
0x18001e892  lea     r8, ??$guid_v@UICompositionEffectSourceParameterFactory@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>
0x18001e899  lea     rdx, [rbp+var_20]
0x18001e89d  lea     rcx, [rbp+arg_0]
0x18001e8a1  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18001e8a6  lea     r8, [rbp+var_38]
0x18001e8aa  mov     edx, dword ptr [rbp+arg_0]
0x18001e8ad  lea     rcx, [rbp+arg_0]
0x18001e8b1  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e8b6  mov     rdi, [rbp+arg_18]
0x18001e8ba  mov     [rbp+arg_0], rdi
0x18001e8be  test    rdi, rdi
0x18001e8c1  jz      loc_18001E956
0x18001e8c7  mov     [rbp+arg_18], 0
0x18001e8cf  mov     rax, [rdi]
0x18001e8d2  lea     r8, [rbp+arg_18]
0x18001e8d6  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001e8dd  mov     rcx, rdi
0x18001e8e0  mov     rax, [rax]
0x18001e8e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e8  mov     rax, [rbp+arg_18]
0x18001e8ec  mov     [rbp+arg_18], rax
0x18001e8f0  test    rax, rax
0x18001e8f3  jz      short loc_18001E956
0x18001e8f5  lea     rcx, [rbp+arg_18]
0x18001e8f9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e8fe  lea     rax, qword_18003F3D8
0x18001e905  mov     [rbp+arg_18], rax
0x18001e909  lock inc cs:qword_18003F3D8
0x18001e911  xor     eax, eax
0x18001e913  lock cmpxchg cs:??$factory_cache_entry_v@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>
0x18001e91c  jnz     short loc_18001E939
0x18001e91e  mov     [rbp+arg_0], 0
0x18001e926  lea     rdx, ListEntry; ListEntry
0x18001e92d  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001e934  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001e939  lea     r8, ??$factory_cache_entry_v@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Composition::CompositionEffectSourceParameter,winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory>
0x18001e940  mov     rdx, rbx
0x18001e943  mov     rcx, rsi
0x18001e946  call    ??R_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@QEBA@AEBUICompositionEffectSourceParameterFactory@2345@@Z; `winrt::Windows::UI::Composition::CompositionEffectSourceParameter::CompositionEffectSourceParameter(winrt::param::hstring const &)'::`1'::_lambda_20__::operator()(winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory const &)
0x18001e94b  nop
0x18001e94c  lock dec cs:qword_18003F3D8
0x18001e954  jmp     short loc_18001E966
0x18001e956  lea     r8, [rbp+arg_0]
0x18001e95a  mov     rdx, rbx
0x18001e95d  mov     rcx, rsi
0x18001e960  call    ??R_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@winrt@@QEAA@AEBUhstring@param@5@@Z@QEBA@AEBUICompositionEffectSourceParameterFactory@2345@@Z; `winrt::Windows::UI::Composition::CompositionEffectSourceParameter::CompositionEffectSourceParameter(winrt::param::hstring const &)'::`1'::_lambda_20__::operator()(winrt::Windows::UI::Composition::ICompositionEffectSourceParameterFactory const &)
0x18001e965  nop
0x18001e966  lea     rcx, [rbp+arg_0]; this
0x18001e96a  call    ??1ICompositionEffectFactory@Composition@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Composition::ICompositionEffectFactory::~ICompositionEffectFactory(void)
0x18001e96f  mov     rax, rbx
0x18001e972  mov     rbx, [rsp+60h+arg_8]
0x18001e97a  add     rsp, 60h
0x18001e97e  pop     rdi
0x18001e97f  pop     rsi
0x18001e980  pop     rbp
0x18001e981  retn
```
