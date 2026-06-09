# CCompositor::Initialize(void)

- ea: `0x18006d678`
- end: `0x18006da4c`
- name: `?Initialize@CCompositor@@IEAAJXZ`
- size: `980`
- prototype: `__int64 __fastcall(CCompositor *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d560`

## callees

- `0x1800029dc`
- `0x180052df0`
- `0x1800680c4`
- `0x18006d678`
- `0x1800776f4`
- `0x1800812a4`
- `0x1800814a4`
- `0x180081a68`
- `0x180095130`
- `0x1800abf58`
- `0x1800e1860`
- `0x1800e4338`
- `0x1800e4770`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006d753`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006d753`

## string_xrefs

- `0x18006d6b3`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d702`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d766`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d7c3`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d841`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d8a7`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d934`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d9c7`: `clientcore\windows\dwm\udwm\compositor.cpp`
- `0x18006d72c`: `Windows.UI.Composition.Compositor`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CCompositor::Initialize(CCompositor *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rax
  int ActivationFactory; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, GUID *, __int64); // r9
  __int64 v12; // r10
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, _QWORD, CCompositor *, struct CMilCommandStream *); // r14
  char *v17; // rbx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // esi
  __int64 v22; // rax
  __int64 (__fastcall *v23)(__int64, GUID *, __int64); // r9
  __int64 v24; // r10
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(__int64, GUID *, __int64); // r9
  __int64 v30; // r10
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 (__fastcall ***v34)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v35)(_QWORD, GUID *, __int64); // r14
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int v40; // [rsp+20h] [rbp-59h]
  __int64 v41; // [rsp+40h] [rbp-39h] BYREF
  __int64 v42; // [rsp+48h] [rbp-31h] BYREF
  struct IDwmChannelProvider *v43; // [rsp+50h] [rbp-29h] BYREF
  __int64 v44; // [rsp+58h] [rbp-21h] BYREF
  struct CMilCommandStream *v45; // [rsp+60h] [rbp-19h] BYREF
  struct CMilBackChannel *v46; // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v48; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = CCompositor::CoinitializeWrapper(this);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v45 = 0;
    v46 = 0;
    v4 = CMilBackChannel::Create(&v46);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 49;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
        (const char *)(unsigned int)v4,
        v40);
LABEL_35:
      wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v46);
      wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v45);
      return v3;
    }
    v45 = 0;
    v4 = CMilCommandStream::Create(v46, &v45);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 50;
      goto LABEL_7;
    }
    v42 = 0;
    v48 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.UI.Composition.Compositor",
      0x22u,
      0x21u);
    v7 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
           &v42,
           v6);
    ActivationFactory = RoGetActivationFactory(v48, &GUID_00000035_0000_0000_c000_000000000046, v7);
    v3 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v40);
LABEL_10:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      goto LABEL_35;
    }
    v41 = 0;
    v10 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            &v41,
            v9);
    v13 = v11(v12, &GUID_2699d281_19e7_4fef_a570_d7768278f7eb, v10);
    v3 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
        (const char *)(unsigned int)v13,
        v40);
LABEL_13:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v41);
      goto LABEL_10;
    }
    v15 = v41;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, CCompositor *, struct CMilCommandStream *))(*(_QWORD *)v41 + 48LL);
    v17 = (char *)this + 40;
    v18 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
      (char *)this + 40,
      v14);
    v19 = v16(v15, 0, this, v45);
    v21 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
        (const char *)(unsigned int)v19,
        (int)&GUID_b403ca50_7f8c_4e83_985f_cc45060036d8);
LABEL_18:
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      v3 = v21;
      goto LABEL_35;
    }
    v43 = 0;
    v22 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
            &v43,
            v20);
    v21 = v23(v24, &GUID_6d3e7e62_c627_40c0_8054_284bb9213812, v22);
    if ( v21 >= 0 )
    {
      v26 = wil::out_param<std::unique_ptr<CCommandBatch>>(&hstringHeader, (char *)this + 24);
      v21 = CMilChannel::Create(v45, v43, (struct CMilChannel **)(v26 + 8));
      wil::details::out_param_t<std::unique_ptr<CMilChannel>>::~out_param_t<std::unique_ptr<CMilChannel>>(&hstringHeader);
      if ( v21 >= 0 )
      {
        v44 = 0;
        v28 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                &v44,
                v27);
        v21 = v29(v30, &GUID_ddda6469_6c17_4be6_8c72_188063dea2ef, v28);
        if ( v21 >= 0 )
        {
          LOBYTE(v31) = 1;
          v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 184LL))(v44, v31);
          if ( v21 >= 0 )
          {
            v34 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))v17;
            v35 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v17;
            v36 = *((_QWORD *)this + 4);
            *((_QWORD *)this + 4) = 0;
            if ( v36 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            v37 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                    (char *)this + 32,
                    v33);
            v38 = v35(v34, &GUID_e01eb649_787e_4560_b398_0de7a2065d8b, v37);
            v3 = v38;
            if ( v38 >= 0 )
            {
              wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v44);
              wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v43);
              wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v41);
              wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
              v3 = 0;
              goto LABEL_35;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x50,
              (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
              (const char *)(unsigned int)v38,
              (int)&GUID_b403ca50_7f8c_4e83_985f_cc45060036d8);
            wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v44);
            wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v43);
            goto LABEL_13;
          }
          v32 = 77;
        }
        else
        {
          v32 = 76;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
          (const char *)(unsigned int)v21,
          (int)&GUID_b403ca50_7f8c_4e83_985f_cc45060036d8);
        wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v44);
        goto LABEL_22;
      }
      v25 = 72;
    }
    else
    {
      v25 = 67;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
      (const char *)(unsigned int)v21,
      (int)&GUID_b403ca50_7f8c_4e83_985f_cc45060036d8);
LABEL_22:
    wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(&v43);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositor.cpp",
    (const char *)(unsigned int)v2,
    v40);
  return v3;
}

```

## disassembly

```asm
0x18006d678  push    rbp
0x18006d67a  push    rbx
0x18006d67b  push    rsi
0x18006d67c  push    rdi
0x18006d67d  push    r14
0x18006d67f  push    r15
0x18006d681  lea     rbp, [rsp-2Fh]
0x18006d686  sub     rsp, 0A8h
0x18006d68d  mov     rax, cs:__security_cookie
0x18006d694  xor     rax, rsp
0x18006d697  mov     [rbp+57h+var_40], rax
0x18006d69b  mov     rdi, rcx
0x18006d69e  call    ?CoinitializeWrapper@CCompositor@@AEAAJXZ; CCompositor::CoinitializeWrapper(void)
0x18006d6a3  mov     ebx, eax
0x18006d6a5  xor     r15d, r15d
0x18006d6a8  test    eax, eax
0x18006d6aa  jns     short loc_18006D6C8
0x18006d6ac  mov     rcx, [rbp+5Fh]; this
0x18006d6b0  mov     r9d, eax; char *
0x18006d6b3  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d6ba  lea     edx, [r15+2Ch]; void *
0x18006d6be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d6c3  jmp     loc_18006DA2E
0x18006d6c8  mov     [rbp+57h+var_70], r15
0x18006d6cc  mov     [rbp+57h+var_68], r15
0x18006d6d0  lea     rcx, [rbp+57h+var_68]; struct CMilBackChannel **
0x18006d6d4  call    ?Create@CMilBackChannel@@SAJPEAPEAV1@@Z; CMilBackChannel::Create(CMilBackChannel * *)
0x18006d6d9  mov     ebx, eax
0x18006d6db  test    eax, eax
0x18006d6dd  jns     short loc_18006D6E6
0x18006d6df  mov     edx, 31h ; '1'
0x18006d6e4  jmp     short loc_18006D702
0x18006d6e6  mov     [rbp+57h+var_70], r15
0x18006d6ea  lea     rdx, [rbp+57h+var_70]; struct CMilCommandStream **
0x18006d6ee  mov     rcx, [rbp+57h+var_68]; struct CMilBackChannel *
0x18006d6f2  call    ?Create@CMilCommandStream@@SAJPEAVCMilBackChannel@@PEAPEAV1@@Z; CMilCommandStream::Create(CMilBackChannel *,CMilCommandStream * *)
0x18006d6f7  mov     ebx, eax
0x18006d6f9  test    eax, eax
0x18006d6fb  jns     short loc_18006D71A
0x18006d6fd  mov     edx, 32h ; '2'; void *
0x18006d702  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d709  mov     r9d, eax; char *
0x18006d70c  mov     rcx, [rbp+5Fh]; this
0x18006d710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d715  jmp     loc_18006DA1B
0x18006d71a  mov     [rbp+57h+var_88], r15
0x18006d71e  mov     [rbp+57h+var_48], r15
0x18006d722  mov     r9d, 21h ; '!'; unsigned int
0x18006d728  lea     r8d, [r9+1]; unsigned int
0x18006d72c  lea     rdx, ?RuntimeClass_Windows_UI_Composition_Compositor@@3QBGB; "Windows.UI.Composition.Compositor"
0x18006d733  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18006d737  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006d73c  lea     rcx, [rbp+57h+var_88]
0x18006d740  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18006d745  mov     r8, rax
0x18006d748  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18006d74f  mov     rcx, [rbp+57h+var_48]
0x18006d753  call    cs:__imp_RoGetActivationFactory
0x18006d759  mov     ebx, eax
0x18006d75b  test    eax, eax
0x18006d75d  jns     short loc_18006D786
0x18006d75f  mov     rcx, [rbp+5Fh]; this
0x18006d763  mov     r9d, eax; char *
0x18006d766  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d76d  mov     edx, 36h ; '6'; void *
0x18006d772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d777  nop
0x18006d778  lea     rcx, [rbp+57h+var_88]
0x18006d77c  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d781  jmp     loc_18006DA1B
0x18006d786  mov     [rbp+57h+var_90], r15
0x18006d78a  mov     r10, [rbp+57h+var_88]
0x18006d78e  mov     rax, [r10]
0x18006d791  mov     r9, [rax]
0x18006d794  mov     [rbp+57h+var_90], r15
0x18006d798  lea     rcx, [rbp+57h+var_90]
0x18006d79c  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18006d7a1  mov     r8, rax
0x18006d7a4  lea     rdx, _GUID_2699d281_19e7_4fef_a570_d7768278f7eb
0x18006d7ab  mov     rcx, r10
0x18006d7ae  mov     rax, r9
0x18006d7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d7b6  mov     ebx, eax
0x18006d7b8  test    eax, eax
0x18006d7ba  jns     short loc_18006D7E0
0x18006d7bc  mov     rcx, [rbp+5Fh]; this
0x18006d7c0  mov     r9d, eax; char *
0x18006d7c3  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d7ca  mov     edx, 3Ch ; '<'; void *
0x18006d7cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d7d4  nop
0x18006d7d5  lea     rcx, [rbp+57h+var_90]
0x18006d7d9  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d7de  jmp     short loc_18006D778
0x18006d7e0  mov     rsi, [rbp+57h+var_90]
0x18006d7e4  mov     rax, [rsi]
0x18006d7e7  mov     r14, [rax+30h]
0x18006d7eb  lea     rbx, [rdi+28h]
0x18006d7ef  mov     rcx, [rbx]
0x18006d7f2  mov     [rbx], r15
0x18006d7f5  test    rcx, rcx
0x18006d7f8  jz      short loc_18006D807
0x18006d7fa  mov     rax, [rcx]
0x18006d7fd  mov     rax, [rax+10h]
0x18006d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d806  nop
0x18006d807  mov     rcx, rbx
0x18006d80a  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18006d80f  mov     [rsp+0D0h+var_A8], rax
0x18006d814  lea     rax, _GUID_b403ca50_7f8c_4e83_985f_cc45060036d8
0x18006d81b  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18006d820  mov     r9, [rbp+57h+var_70]
0x18006d824  mov     r8, rdi
0x18006d827  xor     edx, edx
0x18006d829  mov     rcx, rsi
0x18006d82c  mov     rax, r14
0x18006d82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d834  mov     esi, eax
0x18006d836  test    eax, eax
0x18006d838  jns     short loc_18006D86D
0x18006d83a  mov     rcx, [rbp+5Fh]; this
0x18006d83e  mov     r9d, eax; char *
0x18006d841  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d848  mov     edx, 40h ; '@'; void *
0x18006d84d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d852  nop
0x18006d853  lea     rcx, [rbp+57h+var_90]
0x18006d857  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d85c  nop
0x18006d85d  lea     rcx, [rbp+57h+var_88]
0x18006d861  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d866  mov     ebx, esi
0x18006d868  jmp     loc_18006DA1B
0x18006d86d  mov     [rbp+57h+var_80], r15
0x18006d871  mov     r10, [rbx]
0x18006d874  mov     rax, [r10]
0x18006d877  mov     r9, [rax]
0x18006d87a  mov     [rbp+57h+var_80], r15
0x18006d87e  lea     rcx, [rbp+57h+var_80]
0x18006d882  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18006d887  mov     r8, rax
0x18006d88a  lea     rdx, _GUID_6d3e7e62_c627_40c0_8054_284bb9213812
0x18006d891  mov     rcx, r10
0x18006d894  mov     rax, r9
0x18006d897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d89c  mov     esi, eax
0x18006d89e  test    eax, eax
0x18006d8a0  jns     short loc_18006D8C6
0x18006d8a2  mov     edx, 43h ; 'C'; void *
0x18006d8a7  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d8ae  mov     r9d, esi; char *
0x18006d8b1  mov     rcx, [rbp+5Fh]; this
0x18006d8b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d8ba  nop
0x18006d8bb  lea     rcx, [rbp+57h+var_80]
0x18006d8bf  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x18006d8c4  jmp     short loc_18006D853
0x18006d8c6  lea     rdx, [rdi+18h]
0x18006d8ca  lea     rcx, [rbp+57h+hstringHeader]
0x18006d8ce  call    ??$out_param@V?$unique_ptr@VCCommandBatch@@U?$default_delete@VCCommandBatch@@@std@@@std@@@wil@@YA?AU?$out_param_t@V?$unique_ptr@VCCommandBatch@@U?$default_delete@VCCommandBatch@@@std@@@std@@@details@0@AEAV?$unique_ptr@VCCommandBatch@@U?$default_delete@VCCommandBatch@@@std@@@std@@@Z; wil::out_param<std::unique_ptr<CCommandBatch>>(std::unique_ptr<CCommandBatch> &)
0x18006d8d3  lea     r8, [rax+8]; struct CMilChannel **
0x18006d8d7  mov     rdx, [rbp+57h+var_80]; struct IDwmChannelProvider *
0x18006d8db  mov     rcx, [rbp+57h+var_70]; struct CMilCommandStream *
0x18006d8df  call    ?Create@CMilChannel@@SAJPEAVCMilCommandStream@@PEAUIDwmChannelProvider@@PEAPEAV1@@Z; CMilChannel::Create(CMilCommandStream *,IDwmChannelProvider *,CMilChannel * *)
0x18006d8e4  mov     esi, eax
0x18006d8e6  lea     rcx, [rbp+57h+hstringHeader]
0x18006d8ea  call    ??1?$out_param_t@V?$unique_ptr@VCMilChannel@@U?$default_delete@VCMilChannel@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<CMilChannel>>::~out_param_t<std::unique_ptr<CMilChannel>>(void)
0x18006d8ef  test    esi, esi
0x18006d8f1  jns     short loc_18006D8FA
0x18006d8f3  mov     edx, 48h ; 'H'
0x18006d8f8  jmp     short loc_18006D8A7
0x18006d8fa  mov     [rbp+57h+var_78], r15
0x18006d8fe  mov     r10, [rbx]
0x18006d901  mov     rax, [r10]
0x18006d904  mov     r9, [rax]
0x18006d907  mov     [rbp+57h+var_78], r15
0x18006d90b  lea     rcx, [rbp+57h+var_78]
0x18006d90f  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18006d914  mov     r8, rax
0x18006d917  lea     rdx, _GUID_ddda6469_6c17_4be6_8c72_188063dea2ef
0x18006d91e  mov     rcx, r10
0x18006d921  mov     rax, r9
0x18006d924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d929  mov     esi, eax
0x18006d92b  test    eax, eax
0x18006d92d  jns     short loc_18006D956
0x18006d92f  mov     edx, 4Ch ; 'L'; void *
0x18006d934  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d93b  mov     r9d, esi; char *
0x18006d93e  mov     rcx, [rbp+5Fh]; this
0x18006d942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d947  nop
0x18006d948  lea     rcx, [rbp+57h+var_78]
0x18006d94c  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d951  jmp     loc_18006D8BB
0x18006d956  mov     rcx, [rbp+57h+var_78]
0x18006d95a  mov     rax, [rcx]
0x18006d95d  mov     dl, 1
0x18006d95f  mov     rax, [rax+0B8h]
0x18006d966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d96b  mov     esi, eax
0x18006d96d  test    eax, eax
0x18006d96f  jns     short loc_18006D978
0x18006d971  mov     edx, 4Dh ; 'M'
0x18006d976  jmp     short loc_18006D934
0x18006d978  mov     rsi, [rbx]
0x18006d97b  mov     rax, [rsi]
0x18006d97e  mov     r14, [rax]
0x18006d981  lea     rbx, [rdi+20h]
0x18006d985  mov     rcx, [rbx]
0x18006d988  mov     [rbx], r15
0x18006d98b  test    rcx, rcx
0x18006d98e  jz      short loc_18006D99D
0x18006d990  mov     rax, [rcx]
0x18006d993  mov     rax, [rax+10h]
0x18006d997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d99c  nop
0x18006d99d  mov     rcx, rbx
0x18006d9a0  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18006d9a5  mov     r8, rax
0x18006d9a8  lea     rdx, _GUID_e01eb649_787e_4560_b398_0de7a2065d8b
0x18006d9af  mov     rcx, rsi
0x18006d9b2  mov     rax, r14
0x18006d9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d9ba  mov     ebx, eax
0x18006d9bc  test    eax, eax
0x18006d9be  jns     short loc_18006D9F1
0x18006d9c0  mov     rcx, [rbp+5Fh]; this
0x18006d9c4  mov     r9d, eax; char *
0x18006d9c7  lea     r8, aClientcoreWind_24; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006d9ce  mov     edx, 50h ; 'P'; void *
0x18006d9d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006d9d8  nop
0x18006d9d9  lea     rcx, [rbp+57h+var_78]
0x18006d9dd  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d9e2  nop
0x18006d9e3  lea     rcx, [rbp+57h+var_80]
0x18006d9e7  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x18006d9ec  jmp     loc_18006D7D5
0x18006d9f1  lea     rcx, [rbp+57h+var_78]
0x18006d9f5  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006d9fa  nop
0x18006d9fb  lea     rcx, [rbp+57h+var_80]
0x18006d9ff  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x18006da04  nop
0x18006da05  lea     rcx, [rbp+57h+var_90]
0x18006da09  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006da0e  nop
0x18006da0f  lea     rcx, [rbp+57h+var_88]
0x18006da13  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x18006da18  mov     ebx, r15d
0x18006da1b  lea     rcx, [rbp+57h+var_68]
0x18006da1f  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x18006da24  nop
0x18006da25  lea     rcx, [rbp+57h+var_70]
0x18006da29  call    ??1?$com_ptr_t@UICompositionVisualSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>::~com_ptr_t<Windows::UI::Composition::ICompositionVisualSurface,wil::err_returncode_policy>(void)
0x18006da2e  mov     eax, ebx
0x18006da30  mov     rcx, [rbp+57h+var_40]
0x18006da34  xor     rcx, rsp; StackCookie
0x18006da37  call    __security_check_cookie
0x18006da3c  add     rsp, 0A8h
0x18006da43  pop     r15
0x18006da45  pop     r14
0x18006da47  pop     rdi
0x18006da48  pop     rsi
0x18006da49  pop     rbx
0x18006da4a  pop     rbp
0x18006da4b  retn
```
