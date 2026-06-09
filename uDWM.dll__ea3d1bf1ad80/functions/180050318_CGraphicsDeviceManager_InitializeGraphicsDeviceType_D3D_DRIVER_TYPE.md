# CGraphicsDeviceManager::InitializeGraphicsDeviceType(D3D_DRIVER_TYPE)

- ea: `0x180050318`
- end: `0x18005083c`
- name: `?InitializeGraphicsDeviceType@CGraphicsDeviceManager@@IEAAJW4D3D_DRIVER_TYPE@@@Z`
- size: `1316`
- prototype: `int(CGraphicsDeviceManager *__hidden this, enum D3D_DRIVER_TYPE)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180088a5c`

## callees

- `0x1800029dc`
- `0x180050318`
- `0x1800508a0`
- `0x180050dfc`
- `0x180050e2c`
- `0x180052df0`
- `0x180081a68`
- `0x18008ce54`
- `0x1800ea010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x180050571`
- `d2d1!__imp_D2D1CreateFactory` at `0x180050571`
- `d3d11!D3D11CreateDevice` at `0x180050373`
- `d3d11!D3D11CreateDevice` at `0x180050373`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HRESULT __fastcall CGraphicsDeviceManager::InitializeGraphicsDeviceType(wil::details **this, enum D3D_DRIVER_TYPE a2)
{
  ID3D11Device **ppDevice; // rsi
  HRESULT result; // eax
  __int64 v6; // rax
  __int64 (__fastcall **v7)(__int64, GUID *, __int64); // rdx
  __int64 v8; // r9
  int v9; // eax
  int v10; // ebx
  __int64 v11; // rax
  __int64 (__fastcall **v12)(__int64, GUID *, __int64); // rdx
  __int64 v13; // r9
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, GUID *, __int64); // rbx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64, GUID *, __int64); // r9
  __int64 v23; // r10
  int v24; // eax
  void *v25; // rdx
  __int64 v26; // rdx
  void *v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // rdx
  _QWORD **v31; // rdi
  void **v32; // rax
  HRESULT Factory; // eax
  __int64 v34; // rax
  __int64 (__fastcall **v35)(__int64, GUID *, __int64); // rdx
  __int64 v36; // r9
  _QWORD *v37; // rdi
  __int64 (__fastcall *v38)(_QWORD *, __int64, wil::details **); // rbx
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 (__fastcall *v41)(__int64, GUID *, __int64); // r9
  __int64 v42; // r10
  int v43; // eax
  __int64 v44; // rax
  __int64 (__fastcall **v45)(__int64, GUID *, __int64); // rdx
  __int64 v46; // r9
  int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, wil::details *, wil::details **); // rbx
  _QWORD *v51; // rsi
  __int64 (__fastcall *v52)(_QWORD *, wil::details *, wil::details **); // rdi
  int v53; // eax
  int pFeatureLevels; // [rsp+20h] [rbp-50h]
  _QWORD *v55; // [rsp+50h] [rbp-20h] BYREF
  __int64 v56; // [rsp+58h] [rbp-18h] BYREF
  __int64 v57; // [rsp+60h] [rbp-10h] BYREF
  __int64 v58; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  D3D_FEATURE_LEVEL pFeatureLevel; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v61; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v62; // [rsp+C8h] [rbp+58h] BYREF

  pFeatureLevel = 0;
  ppDevice = (ID3D11Device **)(this + 8);
  wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(this + 8);
  result = D3D11CreateDevice(0, a2, 0, 0x20u, 0, 0, 7u, ppDevice, &pFeatureLevel, 0);
  if ( result >= 0 )
  {
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(this + 9);
    v6 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
           this + 9,
           (*ppDevice)->lpVtbl);
    v9 = (*v7)(v8, &GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0, v6);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v9,
        pFeatureLevels);
      return v10;
    }
    v57 = 0;
    v11 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            &v57,
            (*ppDevice)->lpVtbl);
    v14 = (*v12)(v13, &GUID_77db970f_6276_48ba_ba28_070143b4392c, v11);
    v10 = v14;
    if ( v14 < 0 )
    {
      v15 = 124;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v14,
        pFeatureLevels);
LABEL_46:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v57);
      return v10;
    }
    v16 = v57;
    v17 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v57 + 48LL);
    wil::com_ptr_t<IDXGIAdapter,wil::err_returncode_policy>::reset(this + 5);
    v19 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            this + 5,
            v18);
    v14 = v17(v16, &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0, v19);
    v10 = v14;
    if ( v14 < 0 )
    {
      v15 = 127;
      goto LABEL_9;
    }
    v61 = 0;
    v21 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            &v61,
            v20);
    v24 = v22(v23, &GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8, v21);
    v10 = v24;
    if ( v24 < 0 )
    {
      v26 = 130;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v24,
        pFeatureLevels);
LABEL_45:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v61);
      goto LABEL_46;
    }
    wil::details::ResetEvent(this[10], v25);
    v24 = (*(__int64 (__fastcall **)(__int64, wil::details *, char *))(*(_QWORD *)v61 + 240LL))(
            v61,
            this[10],
            (char *)this + 112);
    v10 = v24;
    if ( v24 < 0 )
    {
      v26 = 133;
      goto LABEL_12;
    }
    wil::details::ResetEvent(this[11], v27);
    v62 = 0;
    v28 = wil::com_ptr_t<ID3D11Device,wil::err_returncode_policy>::query_to<ID3D11Device4>(ppDevice, &v62);
    v10 = v28;
    if ( v28 < 0 )
    {
      v29 = 137;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v28,
        pFeatureLevels);
LABEL_44:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v62);
      goto LABEL_45;
    }
    v28 = (*(__int64 (__fastcall **)(__int64, wil::details *, char *))(*(_QWORD *)v62 + 520LL))(
            v62,
            this[11],
            (char *)this + 116);
    v10 = v28;
    if ( v28 < 0 )
    {
      v29 = 138;
      goto LABEL_17;
    }
    v31 = (_QWORD **)(this + 2);
    if ( !this[2] )
    {
      *v31 = 0;
      v32 = (void **)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                       this + 2,
                       v30);
      Factory = D2D1CreateFactory(D2D1_FACTORY_TYPE_MULTI_THREADED, &GUID_94f81a73_9212_4376_9c58_b16a3a0d3992, 0, v32);
      v10 = Factory;
      if ( Factory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
          (const char *)(unsigned int)Factory,
          pFeatureLevels);
        if ( v62 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
        if ( v61 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
        if ( v57 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        return v10;
      }
    }
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(this + 3);
    v34 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            this + 3,
            **v31);
    v28 = (*v35)(v36, &GUID_31e6e7bc_e0ff_4d46_8c64_a0a8c41c15d3, v34);
    v10 = v28;
    if ( v28 < 0 )
    {
      v29 = 145;
      goto LABEL_17;
    }
    v37 = *v31;
    v38 = *(__int64 (__fastcall **)(_QWORD *, __int64, wil::details **))(*v37 + 136LL);
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(this + 4);
    v28 = v38(v37, v57, this + 4);
    v10 = v28;
    if ( v28 < 0 )
    {
      v29 = 147;
      goto LABEL_17;
    }
    v55 = 0;
    v40 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            &v55,
            v39);
    v43 = v41(v42, &GUID_25297d5c_3ad4_4c9c_b5cf_e36a38512330, v40);
    v10 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v43,
        pFeatureLevels);
LABEL_43:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v55);
      goto LABEL_44;
    }
    v56 = 0;
    v44 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            &v56,
            *v55);
    v47 = (*v45)(v46, &GUID_75f6468d_1b8e_447c_9bc6_75fea80b5b25, v44);
    v10 = v47;
    if ( v47 < 0 )
    {
      v48 = 153;
LABEL_37:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v48,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v47,
        pFeatureLevels);
LABEL_42:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v56);
      goto LABEL_43;
    }
    v49 = v56;
    v50 = *(__int64 (__fastcall **)(__int64, wil::details *, wil::details **))(*(_QWORD *)v56 + 56LL);
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(this + 6);
    v47 = v50(v49, this[4], this + 6);
    v10 = v47;
    if ( v47 < 0 )
    {
      v48 = 154;
      goto LABEL_37;
    }
    v58 = 0;
    v51 = v55;
    v52 = *(__int64 (__fastcall **)(_QWORD *, wil::details *, wil::details **))(*v55 + 40LL);
    wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(this + 7);
    v53 = v52(v51, this[6], this + 7);
    v10 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\graphicsdevicemanager.cpp",
        (const char *)(unsigned int)v53,
        pFeatureLevels);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v58);
      goto LABEL_42;
    }
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    if ( v55 )
      (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
    if ( v62 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
    if ( v61 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180050318  push    rbp
0x18005031a  push    rbx
0x18005031b  push    rsi
0x18005031c  push    rdi
0x18005031d  push    r12
0x18005031f  push    r14
0x180050321  push    r15
0x180050323  mov     rbp, rsp
0x180050326  sub     rsp, 70h
0x18005032a  mov     ebx, edx
0x18005032c  mov     r14, rcx
0x18005032f  xor     r12d, r12d
0x180050332  mov     [rbp+arg_0], r12d
0x180050336  lea     rsi, [rcx+40h]
0x18005033a  mov     rcx, rsi
0x18005033d  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x180050342  mov     [rsp+70h+ppImmediateContext], r12; ppImmediateContext
0x180050347  lea     rax, [rbp+arg_0]
0x18005034b  mov     [rsp+70h+pFeatureLevel], rax; pFeatureLevel
0x180050350  mov     [rsp+70h+ppDevice], rsi; ppDevice
0x180050355  mov     [rsp+70h+SDKVersion], 7; SDKVersion
0x18005035d  mov     [rsp+70h+FeatureLevels], r12d; FeatureLevels
0x180050362  mov     [rsp+70h+pFeatureLevels], r12; int
0x180050367  lea     r9d, [r12+20h]; Flags
0x18005036c  xor     r8d, r8d; Software
0x18005036f  mov     edx, ebx; DriverType
0x180050371  xor     ecx, ecx; pAdapter
0x180050373  call    cs:__imp_D3D11CreateDevice
0x180050379  test    eax, eax
0x18005037b  js      loc_18005082D
0x180050381  lea     rcx, [r14+48h]
0x180050385  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x18005038a  mov     r9, [rsi]
0x18005038d  mov     rdx, [r9]
0x180050390  lea     rcx, [r14+48h]
0x180050394  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050399  mov     r8, rax
0x18005039c  mov     rax, [rdx]
0x18005039f  lea     rdx, _GUID_9b7e4e00_342c_4106_a19f_4f2704f689f0
0x1800503a6  mov     rcx, r9
0x1800503a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503ae  mov     ebx, eax
0x1800503b0  test    eax, eax
0x1800503b2  jns     short loc_1800503D3
0x1800503b4  mov     rcx, [rbp+38h]; this
0x1800503b8  mov     r9d, eax; char *
0x1800503bb  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x1800503c2  lea     edx, [r12+79h]; void *
0x1800503c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800503cc  mov     eax, ebx
0x1800503ce  jmp     loc_18005082D
0x1800503d3  mov     [rbp+var_10], r12
0x1800503d7  mov     r9, [rsi]
0x1800503da  mov     rdx, [r9]
0x1800503dd  lea     rcx, [rbp+var_10]
0x1800503e1  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x1800503e6  mov     r8, rax
0x1800503e9  mov     rax, [rdx]
0x1800503ec  lea     rdx, _GUID_77db970f_6276_48ba_ba28_070143b4392c
0x1800503f3  mov     rcx, r9
0x1800503f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503fb  mov     ebx, eax
0x1800503fd  test    eax, eax
0x1800503ff  jns     short loc_180050408
0x180050401  mov     edx, 7Ch ; '|'
0x180050406  jmp     short loc_180050447
0x180050408  mov     rdi, [rbp+var_10]
0x18005040c  mov     rax, [rdi]
0x18005040f  mov     rbx, [rax+30h]
0x180050413  lea     r15, [r14+28h]
0x180050417  mov     rcx, r15
0x18005041a  call    ?reset@?$com_ptr_t@UIDXGIAdapter@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGIAdapter,wil::err_returncode_policy>::reset(void)
0x18005041f  mov     rcx, r15
0x180050422  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050427  mov     r8, rax
0x18005042a  lea     rdx, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180050431  mov     rcx, rdi
0x180050434  mov     rax, rbx
0x180050437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005043c  mov     ebx, eax
0x18005043e  test    eax, eax
0x180050440  jns     short loc_18005045F
0x180050442  mov     edx, 7Fh; void *
0x180050447  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x18005044e  mov     r9d, eax; char *
0x180050451  mov     rcx, [rbp+38h]; this
0x180050455  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005045a  jmp     loc_1800507AF
0x18005045f  mov     [rbp+arg_10], r12
0x180050463  mov     r10, [r15]
0x180050466  mov     rax, [r10]
0x180050469  mov     r9, [rax+30h]
0x18005046d  mov     [rbp+arg_10], r12
0x180050471  lea     rcx, [rbp+arg_10]
0x180050475  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18005047a  mov     r8, rax
0x18005047d  lea     rdx, _GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8
0x180050484  mov     rcx, r10
0x180050487  mov     rax, r9
0x18005048a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005048f  mov     ebx, eax
0x180050491  test    eax, eax
0x180050493  jns     short loc_1800504B2
0x180050495  mov     edx, 82h; void *
0x18005049a  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x1800504a1  mov     r9d, eax; char *
0x1800504a4  mov     rcx, [rbp+38h]; this
0x1800504a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800504ad  jmp     loc_1800507A5
0x1800504b2  mov     rcx, [r14+50h]; this
0x1800504b6  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1800504bb  mov     rcx, [rbp+arg_10]
0x1800504bf  mov     rax, [rcx]
0x1800504c2  lea     r8, [r14+70h]
0x1800504c6  mov     rdx, [r14+50h]
0x1800504ca  mov     rax, [rax+0F0h]
0x1800504d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504d6  mov     ebx, eax
0x1800504d8  test    eax, eax
0x1800504da  jns     short loc_1800504E3
0x1800504dc  mov     edx, 85h
0x1800504e1  jmp     short loc_18005049A
0x1800504e3  mov     rcx, [r14+58h]; this
0x1800504e7  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1800504ec  nop
0x1800504ed  mov     [rbp+arg_18], r12
0x1800504f1  lea     rdx, [rbp+arg_18]
0x1800504f5  mov     rcx, rsi
0x1800504f8  call    ??$query_to@UID3D11Device4@@@?$com_ptr_t@UID3D11Device@@Uerr_returncode_policy@wil@@@wil@@QEBAJPEAPEAUID3D11Device4@@@Z; wil::com_ptr_t<ID3D11Device,wil::err_returncode_policy>::query_to<ID3D11Device4>(ID3D11Device4 * *)
0x1800504fd  mov     ebx, eax
0x1800504ff  test    eax, eax
0x180050501  jns     short loc_180050520
0x180050503  mov     edx, 89h; void *
0x180050508  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x18005050f  mov     r9d, eax; char *
0x180050512  mov     rcx, [rbp+38h]; this
0x180050516  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005051b  jmp     loc_18005079B
0x180050520  mov     rcx, [rbp+arg_18]
0x180050524  mov     rax, [rcx]
0x180050527  lea     r8, [r14+74h]
0x18005052b  mov     rdx, [r14+58h]
0x18005052f  mov     rax, [rax+208h]
0x180050536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005053b  mov     ebx, eax
0x18005053d  test    eax, eax
0x18005053f  jns     short loc_180050548
0x180050541  mov     edx, 8Ah
0x180050546  jmp     short loc_180050508
0x180050548  lea     rdi, [r14+10h]
0x18005054c  cmp     [rdi], r12
0x18005054f  jnz     loc_1800505DD
0x180050555  mov     [rdi], r12
0x180050558  mov     rcx, rdi
0x18005055b  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x180050560  mov     r9, rax; ppIFactory
0x180050563  xor     r8d, r8d; pFactoryOptions
0x180050566  lea     rdx, _GUID_94f81a73_9212_4376_9c58_b16a3a0d3992; riid
0x18005056d  lea     ecx, [r8+1]; factoryType
0x180050571  call    cs:__imp_D2D1CreateFactory
0x180050577  mov     ebx, eax
0x180050579  test    eax, eax
0x18005057b  jns     short loc_1800505DD
0x18005057d  mov     rcx, [rbp+38h]; this
0x180050581  mov     r9d, eax; char *
0x180050584  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x18005058b  mov     edx, 8Eh; void *
0x180050590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050595  nop
0x180050596  mov     rcx, [rbp+arg_18]
0x18005059a  test    rcx, rcx
0x18005059d  jz      short loc_1800505AC
0x18005059f  mov     rax, [rcx]
0x1800505a2  mov     rax, [rax+10h]
0x1800505a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505ab  nop
0x1800505ac  mov     rcx, [rbp+arg_10]
0x1800505b0  test    rcx, rcx
0x1800505b3  jz      short loc_1800505C2
0x1800505b5  mov     rax, [rcx]
0x1800505b8  mov     rax, [rax+10h]
0x1800505bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505c1  nop
0x1800505c2  mov     rcx, [rbp+var_10]
0x1800505c6  test    rcx, rcx
0x1800505c9  jz      short loc_1800505D8
0x1800505cb  mov     rax, [rcx]
0x1800505ce  mov     rax, [rax+10h]
0x1800505d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505d7  nop
0x1800505d8  jmp     loc_1800503CC
0x1800505dd  lea     rcx, [r14+18h]
0x1800505e1  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x1800505e6  mov     r9, [rdi]
0x1800505e9  mov     rdx, [r9]
0x1800505ec  lea     rcx, [r14+18h]
0x1800505f0  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x1800505f5  mov     r8, rax
0x1800505f8  mov     rax, [rdx]
0x1800505fb  lea     rdx, _GUID_31e6e7bc_e0ff_4d46_8c64_a0a8c41c15d3
0x180050602  mov     rcx, r9
0x180050605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005060a  mov     ebx, eax
0x18005060c  test    eax, eax
0x18005060e  jns     short loc_18005061A
0x180050610  mov     edx, 91h
0x180050615  jmp     loc_180050508
0x18005061a  mov     rdi, [rdi]
0x18005061d  mov     rax, [rdi]
0x180050620  mov     rbx, [rax+88h]
0x180050627  lea     rsi, [r14+20h]
0x18005062b  mov     rcx, rsi
0x18005062e  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x180050633  mov     r8, rsi
0x180050636  mov     rdx, [rbp+var_10]
0x18005063a  mov     rcx, rdi
0x18005063d  mov     rax, rbx
0x180050640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050645  mov     ebx, eax
0x180050647  test    eax, eax
0x180050649  jns     short loc_180050655
0x18005064b  mov     edx, 93h
0x180050650  jmp     loc_180050508
0x180050655  mov     [rbp+var_20], r12
0x180050659  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180050660  mov     rcx, [rax+30h]
0x180050664  mov     r10, [rcx+20h]
0x180050668  mov     rax, [r10]
0x18005066b  mov     r9, [rax]
0x18005066e  mov     [rbp+var_20], r12
0x180050672  lea     rcx, [rbp+var_20]
0x180050676  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18005067b  mov     r8, rax
0x18005067e  lea     rdx, _GUID_25297d5c_3ad4_4c9c_b5cf_e36a38512330
0x180050685  mov     rcx, r10
0x180050688  mov     rax, r9
0x18005068b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050690  mov     ebx, eax
0x180050692  test    eax, eax
0x180050694  jns     short loc_1800506B3
0x180050696  mov     rcx, [rbp+38h]; this
0x18005069a  mov     r9d, eax; char *
0x18005069d  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x1800506a4  mov     edx, 96h; void *
0x1800506a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800506ae  jmp     loc_180050791
0x1800506b3  mov     [rbp+var_18], r12
0x1800506b7  mov     r9, [rbp+var_20]
0x1800506bb  mov     rdx, [r9]
0x1800506be  lea     rcx, [rbp+var_18]
0x1800506c2  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x1800506c7  mov     r8, rax
0x1800506ca  mov     rax, [rdx]
0x1800506cd  lea     rdx, _GUID_75f6468d_1b8e_447c_9bc6_75fea80b5b25
0x1800506d4  mov     rcx, r9
0x1800506d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506dc  mov     ebx, eax
0x1800506de  test    eax, eax
0x1800506e0  jns     short loc_1800506FF
0x1800506e2  mov     edx, 99h; void *
0x1800506e7  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x1800506ee  mov     r9d, eax; char *
0x1800506f1  mov     rcx, [rbp+38h]; this
0x1800506f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800506fa  jmp     loc_180050787
0x1800506ff  mov     rdi, [rbp+var_18]
0x180050703  mov     rax, [rdi]
0x180050706  mov     rbx, [rax+38h]
0x18005070a  lea     r15, [r14+30h]
0x18005070e  mov     rcx, r15
0x180050711  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x180050716  mov     r8, r15
0x180050719  mov     rdx, [rsi]
0x18005071c  mov     rcx, rdi
0x18005071f  mov     rax, rbx
0x180050722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050727  mov     ebx, eax
0x180050729  test    eax, eax
0x18005072b  jns     short loc_180050734
0x18005072d  mov     edx, 9Ah
0x180050732  jmp     short loc_1800506E7
0x180050734  mov     [rbp+var_8], r12
0x180050738  mov     rsi, [rbp+var_20]
0x18005073c  mov     rax, [rsi]
0x18005073f  mov     rdi, [rax+28h]
0x180050743  lea     rcx, [r14+38h]
0x180050747  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x18005074c  lea     r8, [r14+38h]
0x180050750  mov     rdx, [r15]
0x180050753  mov     rcx, rsi
0x180050756  mov     rax, rdi
0x180050759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005075e  mov     ebx, eax
0x180050760  test    eax, eax
0x180050762  jns     short loc_1800507BD
0x180050764  mov     rcx, [rbp+38h]; this
0x180050768  mov     r9d, eax; char *
0x18005076b  lea     r8, aClientcoreWind_47; "clientcore\\windows\\dwm\\udwm\\graphic"...
0x180050772  mov     edx, 9Dh; void *
0x180050777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
