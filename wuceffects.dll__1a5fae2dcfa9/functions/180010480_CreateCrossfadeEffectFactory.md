# CreateCrossfadeEffectFactory

- ea: `0x180010480`
- end: `0x18001085e`
- name: `CreateCrossfadeEffectFactory`
- size: `990`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180010224`
- `0x1800102e0`
- `0x180010358`
- `0x180010480`
- `0x180010864`
- `0x180010c3c`
- `0x180012040`
- `0x180013664`
- `0x18001e988`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x18001059d`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`
- `0x180010690`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\microsoft.internal.ui.composition.effects.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CreateCrossfadeEffectFactory(__int64 a1, int ***a2)
{
  __int64 v4; // rbx
  const wchar_t *v5; // rdi
  int **v6; // rdx
  int **v7; // rsi
  int v8; // eax
  const wchar_t *v9; // rdi
  int **v10; // rdx
  int **v11; // rsi
  int v12; // eax
  int v13; // eax
  int **v14; // rdi
  const char *v15; // r9
  __int64 result; // rax
  __int64 v17; // [rsp+20h] [rbp-78h] BYREF
  const wchar_t *v18; // [rsp+28h] [rbp-70h] BYREF
  unsigned __int64 v19; // [rsp+30h] [rbp-68h] BYREF
  __int64 v20; // [rsp+38h] [rbp-60h] BYREF
  __int64 v21; // [rsp+40h] [rbp-58h]
  const wchar_t *v22; // [rsp+48h] [rbp-50h]
  int *v23; // [rsp+50h] [rbp-48h] BYREF
  int v24; // [rsp+58h] [rbp-40h] BYREF
  int v25; // [rsp+5Ch] [rbp-3Ch]
  const wchar_t *v26; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v28; // [rsp+A0h] [rbp+8h] BYREF
  int **v29; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+20h] BYREF

  v4 = 0;
  v17 = 0;
  if ( a1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    v4 = a1;
    v17 = a1;
  }
  try
  {
    CreateEffect<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>(&v28);
    v20 = 0x900000001LL;
    v22 = L"Crossfade";
    v19 = (unsigned __int64)&v20;
    winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(
      &v28,
      &v19);
    v24 = 1;
    v25 = 7;
    v26 = L"source1";
    v23 = &v24;
    v29 = &v23;
    ___call_factory_UCompositionEffectSourceParameter_Composition_UI_Windows_winrt__UICompositionEffectSourceParameterFactory_2345_V_lambda_20____0___012345_QEAA_AEBUhstring_param_5__Z__impl_winrt__YA_A_P__QEAV_lambda_20____0___0CompositionEffectSourceParameter_Composition_UI_Windows_1_QEAA_AEBUhstring_param_1__Z__Z(
      &v18,
      &v29);
    v5 = v18;
    if ( v18 )
    {
      v29 = 0;
      (**(void (__fastcall ***)(const wchar_t *, __int64 *, int ***))v18)(
        v18,
        winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>,
        &v29);
      v6 = v29;
      v7 = v29;
    }
    else
    {
      v6 = 0;
      v7 = 0;
    }
    v29 = v6;
    LODWORD(v19) = 1017;
    v20 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
    v21 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 72LL))(v28);
    if ( v8 < 0 )
      winrt::throw_hresult((unsigned int)v8, &v19);
    if ( v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
    if ( v5 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
    v24 = 1;
    v25 = 7;
    v26 = L"source2";
    v23 = &v24;
    v29 = &v23;
    ___call_factory_UCompositionEffectSourceParameter_Composition_UI_Windows_winrt__UICompositionEffectSourceParameterFactory_2345_V_lambda_20____0___012345_QEAA_AEBUhstring_param_5__Z__impl_winrt__YA_A_P__QEAV_lambda_20____0___0CompositionEffectSourceParameter_Composition_UI_Windows_1_QEAA_AEBUhstring_param_1__Z__Z(
      &v18,
      &v29);
    v9 = v18;
    if ( v18 )
    {
      v29 = 0;
      (**(void (__fastcall ***)(const wchar_t *, __int64 *, int ***))v18)(
        v18,
        winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>,
        &v29);
      v10 = v29;
      v11 = v29;
    }
    else
    {
      v10 = 0;
      v11 = 0;
    }
    v29 = v10;
    LODWORD(v19) = 1051;
    v20 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
    v21 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 88LL))(v28);
    if ( v12 < 0 )
      winrt::throw_hresult((unsigned int)v12, &v19);
    if ( v11 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
    if ( v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v18);
    LODWORD(v19) = 983;
    v20 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\microsoft.internal.ui.composition.effects.h";
    v21 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 56LL))(v28);
    if ( v13 < 0 )
      winrt::throw_hresult((unsigned int)v13, &v19);
    v18 = L"Crossfade.Weight";
    winrt::impl::make_scoped_input_iterable<winrt::hstring,unsigned short const * const *>((winrt *)&v19);
    LOBYTE(v21) = 1;
    v29 = 0;
    if ( v28 )
    {
      (**(void (__fastcall ***)(__int64, __int64 *, int ***))v28)(
        v28,
        winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffect>,
        &v29);
      v14 = v29;
    }
    else
    {
      v14 = 0;
    }
    winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(
      &v17,
      &v30,
      &v29,
      &v19,
      v17);
    if ( v14 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v29);
    if ( v20 )
      *(_BYTE *)v20 = 1;
    v19 &= -(__int64)((_BYTE)v21 != 0);
    winrt::Windows::UI::Composition::ICompositionEffectFactory::~ICompositionEffectFactory((winrt::Windows::UI::Composition::ICompositionEffectFactory *)&v19);
    winrt::impl::as<Windows::UI::Composition::ICompositionEffectFactory,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
      &v29,
      v30);
    *a2 = v29;
    if ( v30 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v30);
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
    if ( v4 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v17);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v28) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xDB,
                     (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
                     v15);
    return (unsigned int)v28;
  }
  return result;
}

```

## disassembly

```asm
0x180010480  push    rbx
0x180010482  push    rsi
0x180010483  push    rdi
0x180010484  push    r13
0x180010486  push    r14
0x180010488  sub     rsp, 70h
0x18001048c  mov     r14, rdx
0x18001048f  mov     rdi, rcx
0x180010492  xor     ebx, ebx
0x180010494  mov     [rsp+98h+var_78], rbx
0x180010499  test    rcx, rcx
0x18001049c  jz      short loc_1800104B2
0x18001049e  mov     rax, [rcx]
0x1800104a1  mov     rax, [rax+8]
0x1800104a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104aa  mov     rbx, rdi
0x1800104ad  mov     [rsp+98h+var_78], rbx
0x1800104b2  lea     rcx, [rsp+98h+arg_0]
0x1800104ba  call    ??$CreateEffect@VCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ; CreateEffect<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect,winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>(void)
0x1800104bf  nop
0x1800104c0  mov     dword ptr [rsp+98h+var_60], 1
0x1800104c8  mov     dword ptr [rsp+98h+var_60+4], 9
0x1800104d0  lea     rax, S2; "Crossfade"
0x1800104d7  mov     [rsp+98h+var_50], rax
0x1800104dc  lea     rax, [rsp+98h+var_60]
0x1800104e1  mov     [rsp+98h+var_68], rax
0x1800104e6  lea     rdx, [rsp+98h+var_68]
0x1800104eb  lea     rcx, [rsp+98h+arg_0]
0x1800104f3  call    ?Name@?$consume_Windows_Graphics_Effects_IGraphicsEffect@UCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Graphics_Effects_IGraphicsEffect<winrt::Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::Name(winrt::param::hstring const &)
0x1800104f8  mov     [rsp+98h+var_40], 1
0x180010500  mov     r13d, 7
0x180010506  mov     [rsp+98h+var_3C], r13d
0x18001050b  lea     rax, aSource1; "source1"
0x180010512  mov     [rsp+98h+var_30], rax
0x180010517  lea     rax, [rsp+98h+var_40]
0x18001051c  mov     [rsp+98h+var_48], rax
0x180010521  lea     rax, [rsp+98h+var_48]
0x180010526  mov     [rsp+98h+arg_10], rax
0x18001052e  lea     rdx, [rsp+98h+arg_10]
0x180010536  lea     rcx, [rsp+98h+var_70]
0x18001053b  call    ??$call_factory@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@V_lambda_20__@?0???012345@QEAA@AEBUhstring@param@5@@Z@@impl@winrt@@YA?A_P$$QEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@1@QEAA@AEBUhstring@param@1@@Z@@Z
0x180010540  nop
0x180010541  mov     rdi, [rsp+98h+var_70]
0x180010546  test    rdi, rdi
0x180010549  jnz     short loc_180010551
0x18001054b  xor     edx, edx
0x18001054d  xor     esi, esi
0x18001054f  jmp     short loc_180010585
0x180010551  mov     [rsp+98h+arg_10], 0
0x18001055d  mov     rax, [rdi]
0x180010560  lea     r8, [rsp+98h+arg_10]
0x180010568  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x18001056f  mov     rcx, rdi
0x180010572  mov     rax, [rax]
0x180010575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001057a  mov     rdx, [rsp+98h+arg_10]
0x180010582  mov     rsi, rdx
0x180010585  mov     [rsp+98h+arg_10], rdx
0x18001058d  mov     rcx, [rsp+98h+arg_0]
0x180010595  mov     dword ptr [rsp+98h+var_68], 3F9h
0x18001059d  lea     rax, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800105a4  mov     [rsp+98h+var_60], rax
0x1800105a9  mov     [rsp+98h+var_58], 0
0x1800105b2  mov     rax, [rcx]
0x1800105b5  mov     rax, [rax+48h]
0x1800105b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105be  test    eax, eax
0x1800105c0  jns     short loc_1800105CF
0x1800105c2  lea     rdx, [rsp+98h+var_68]
0x1800105c7  mov     ecx, eax
0x1800105c9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800105cf  test    rsi, rsi
0x1800105d2  jz      short loc_1800105E2
0x1800105d4  lea     rcx, [rsp+98h+arg_10]
0x1800105dc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800105e1  nop
0x1800105e2  test    rdi, rdi
0x1800105e5  jz      short loc_1800105F1
0x1800105e7  lea     rcx, [rsp+98h+var_70]
0x1800105ec  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800105f1  mov     [rsp+98h+var_40], 1
0x1800105f9  mov     [rsp+98h+var_3C], r13d
0x1800105fe  lea     rax, aSource2; "source2"
0x180010605  mov     [rsp+98h+var_30], rax
0x18001060a  lea     rax, [rsp+98h+var_40]
0x18001060f  mov     [rsp+98h+var_48], rax
0x180010614  lea     rax, [rsp+98h+var_48]
0x180010619  mov     [rsp+98h+arg_10], rax
0x180010621  lea     rdx, [rsp+98h+arg_10]
0x180010629  lea     rcx, [rsp+98h+var_70]
0x18001062e  call    ??$call_factory@UCompositionEffectSourceParameter@Composition@UI@Windows@winrt@@UICompositionEffectSourceParameterFactory@2345@V_lambda_20__@?0???012345@QEAA@AEBUhstring@param@5@@Z@@impl@winrt@@YA?A_P$$QEAV_lambda_20__@?0???0CompositionEffectSourceParameter@Composition@UI@Windows@1@QEAA@AEBUhstring@param@1@@Z@@Z
0x180010633  nop
0x180010634  mov     rdi, [rsp+98h+var_70]
0x180010639  test    rdi, rdi
0x18001063c  jnz     short loc_180010644
0x18001063e  xor     edx, edx
0x180010640  xor     esi, esi
0x180010642  jmp     short loc_180010678
0x180010644  mov     [rsp+98h+arg_10], 0
0x180010650  mov     rax, [rdi]
0x180010653  lea     r8, [rsp+98h+arg_10]
0x18001065b  lea     rdx, ??$guid_v@UIGraphicsEffectSource@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffectSource>
0x180010662  mov     rcx, rdi
0x180010665  mov     rax, [rax]
0x180010668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001066d  mov     rdx, [rsp+98h+arg_10]
0x180010675  mov     rsi, rdx
0x180010678  mov     [rsp+98h+arg_10], rdx
0x180010680  mov     rcx, [rsp+98h+arg_0]
0x180010688  mov     dword ptr [rsp+98h+var_68], 41Bh
0x180010690  lea     r13, aOnecoreuapInte_0; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010697  mov     [rsp+98h+var_60], r13
0x18001069c  mov     [rsp+98h+var_58], 0
0x1800106a5  mov     rax, [rcx]
0x1800106a8  mov     rax, [rax+58h]
0x1800106ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106b1  test    eax, eax
0x1800106b3  jns     short loc_1800106C2
0x1800106b5  lea     rdx, [rsp+98h+var_68]
0x1800106ba  mov     ecx, eax
0x1800106bc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800106c2  test    rsi, rsi
0x1800106c5  jz      short loc_1800106D5
0x1800106c7  lea     rcx, [rsp+98h+arg_10]
0x1800106cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800106d4  nop
0x1800106d5  test    rdi, rdi
0x1800106d8  jz      short loc_1800106E4
0x1800106da  lea     rcx, [rsp+98h+var_70]
0x1800106df  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800106e4  mov     rcx, [rsp+98h+arg_0]
0x1800106ec  mov     dword ptr [rsp+98h+var_68], 3D7h
0x1800106f4  mov     [rsp+98h+var_60], r13
0x1800106f9  mov     [rsp+98h+var_58], 0
0x180010702  mov     rax, [rcx]
0x180010705  xorps   xmm1, xmm1
0x180010708  mov     rax, [rax+38h]
0x18001070c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010711  test    eax, eax
0x180010713  jns     short loc_180010721
0x180010715  lea     rdx, [rsp+98h+var_68]
0x18001071a  mov     ecx, eax
0x18001071c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010721  lea     rax, aCrossfadeWeigh; "Crossfade.Weight"
0x180010728  mov     [rsp+98h+var_70], rax
0x18001072d  lea     r8, [rsp+98h+var_68]
0x180010732  lea     rdx, [rsp+98h+var_70]
0x180010737  lea     rcx, [rsp+98h+var_68]; this
0x18001073c  call    ??$make_scoped_input_iterable@Uhstring@winrt@@PEBQEBG@impl@winrt@@YA?A_PPEBQEBG0@Z
0x180010741  mov     byte ptr [rsp+98h+var_58], 1
0x180010746  mov     rcx, [rsp+98h+arg_0]
0x18001074e  mov     [rsp+98h+arg_10], 0
0x18001075a  test    rcx, rcx
0x18001075d  jnz     short loc_180010763
0x18001075f  xor     edi, edi
0x180010761  jmp     short loc_18001078D
0x180010763  mov     rax, [rcx]
0x180010766  lea     r8, [rsp+98h+arg_10]
0x18001076e  lea     rdx, ??$guid_v@UIGraphicsEffect@Effects@Graphics@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Graphics::Effects::IGraphicsEffect>
0x180010775  mov     rax, [rax]
0x180010778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001077d  mov     rdi, [rsp+98h+arg_10]
0x180010785  mov     [rsp+98h+arg_10], rdi
0x18001078d  lea     r9, [rsp+98h+var_68]
0x180010792  lea     r8, [rsp+98h+arg_10]
0x18001079a  lea     rdx, [rsp+98h+arg_18]
0x1800107a2  lea     rcx, [rsp+98h+var_78]
0x1800107a7  call    ?CreateEffectFactory@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUIGraphicsEffect@Effects@Graphics@Windows@3@AEBU?$iterable@Uhstring@winrt@@@param@3@@Z; winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateEffectFactory(winrt::Windows::Graphics::Effects::IGraphicsEffect const &,winrt::param::iterable<winrt::hstring> const &)
0x1800107ac  nop
0x1800107ad  test    rdi, rdi
0x1800107b0  jz      short loc_1800107C0
0x1800107b2  lea     rcx, [rsp+98h+arg_10]
0x1800107ba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800107bf  nop
0x1800107c0  mov     rax, [rsp+98h+var_60]
0x1800107c5  test    rax, rax
0x1800107c8  jz      short loc_1800107CD
0x1800107ca  mov     byte ptr [rax], 1
0x1800107cd  mov     al, byte ptr [rsp+98h+var_58]
0x1800107d1  neg     al
0x1800107d3  sbb     rcx, rcx
0x1800107d6  and     [rsp+98h+var_68], rcx
0x1800107db  lea     rcx, [rsp+98h+var_68]; this
0x1800107e0  call    ??1ICompositionEffectFactory@Composition@UI@Windows@winrt@@QEAA@XZ; winrt::Windows::UI::Composition::ICompositionEffectFactory::~ICompositionEffectFactory(void)
0x1800107e5  mov     rdx, [rsp+98h+arg_18]
0x1800107ed  lea     rcx, [rsp+98h+arg_10]
0x1800107f5  call    ??$as@UICompositionEffectFactory@Composition@UI@Windows@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@$0A@@impl@winrt@@YA?AU?$com_ptr@UICompositionEffectFactory@Composition@UI@Windows@@@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<Windows::UI::Composition::ICompositionEffectFactory,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x1800107fa  mov     rax, [rsp+98h+arg_10]
0x180010802  mov     [r14], rax
0x180010805  cmp     [rsp+98h+arg_18], 0
0x18001080e  jz      short loc_18001081E
0x180010810  lea     rcx, [rsp+98h+arg_18]
0x180010818  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001081d  nop
0x18001081e  cmp     [rsp+98h+arg_0], 0
0x180010827  jz      short loc_180010837
0x180010829  lea     rcx, [rsp+98h+arg_0]
0x180010831  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010836  nop
0x180010837  test    rbx, rbx
0x18001083a  jz      short loc_180010847
0x18001083c  lea     rcx, [rsp+98h+var_78]
0x180010841  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180010846  nop
0x180010847  xor     eax, eax
0x180010849  jmp     short loc_180010852
0x18001084b  mov     eax, dword ptr [rsp+98h+arg_0]
0x180010852  add     rsp, 70h
0x180010856  pop     r14
0x180010858  pop     r13
0x18001085a  pop     rdi
0x18001085b  pop     rsi
0x18001085c  pop     rbx
0x18001085d  retn
```
