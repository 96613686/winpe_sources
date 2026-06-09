# winrt::Udwm::Transitions::Private::implementation::WindowMoveResizeCrossfadeTransition::StartCrossfadeAnimation(void)

- ea: `0x180064768`
- end: `0x180064900`
- name: `?StartCrossfadeAnimation@WindowMoveResizeCrossfadeTransition@implementation@Private@Transitions@Udwm@winrt@@AEAAXXZ`
- size: `408`
- prototype: `void __fastcall(winrt::Udwm::Transitions::Private::implementation::WindowMoveResizeCrossfadeTransition *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038f6c`

## callees

- `0x180039974`
- `0x180039bdc`
- `0x180039c08`
- `0x180064768`
- `0x180064974`
- `0x180064990`
- `0x180064d60`
- `0x180064dec`
- `0x180065044`
- `0x1800d090c`
- `0x1800ea010`

## string_xrefs

- `0x18006479f`: `clientcore\windows\dwm\udwm\transitions.windowmoveresizecrossfadetransition.cpp`
- `0x1800647ec`: `clientcore\windows\dwm\udwm\transitions.windowmoveresizecrossfadetransition.cpp`
- `0x18006483f`: `clientcore\windows\dwm\udwm\transitions.windowmoveresizecrossfadetransition.cpp`
- `0x180064875`: `clientcore\windows\dwm\udwm\transitions.windowmoveresizecrossfadetransition.cpp`
- `0x1800648ca`: `clientcore\windows\dwm\udwm\transitions.windowmoveresizecrossfadetransition.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Udwm::Transitions::Private::implementation::WindowMoveResizeCrossfadeTransition::StartCrossfadeAnimation(
        winrt::Udwm::Transitions::Private::implementation::WindowMoveResizeCrossfadeTransition *this)
{
  struct CAnimationResource **v2; // rbx
  int v3; // eax
  float v4; // xmm7_4
  int v5; // eax
  const struct CDesktopManager::WindowAnimationSettings *WindowAnimationSettings; // rax
  int v7; // eax
  const struct CDesktopManager::WindowAnimationSettings *v8; // rax
  int v9; // eax
  struct CAnimationResource *v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rax
  int v13; // eax
  int v14; // [rsp+20h] [rbp-38h]
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v18; // [rsp+60h] [rbp+8h] BYREF

  v2 = (struct CAnimationResource **)((char *)this + 64);
  wil::com_ptr_t<CAnimationResource,wil::err_returncode_policy>::reset((char *)this + 64);
  v3 = CAnimationResource::Create(v2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\transitions.windowmoveresizecrossfadetransition.cpp",
      (const char *)(unsigned int)v3,
      v14);
  v4 = *((float *)CDesktopManager::GetWindowAnimationSettings() + 7);
  v5 = CAnimationResource::AddCubic(*v2, 0.0, 1.0, 0.0, 0.0, 0.0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\transitions.windowmoveresizecrossfadetransition.cpp",
      (const char *)(unsigned int)v5,
      v15);
  WindowAnimationSettings = CDesktopManager::GetWindowAnimationSettings();
  v7 = CAnimationResource::AddCubic(*v2, *((float *)WindowAnimationSettings + 6), 1.0, -1.0 / v4, 0.0, 0.0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\transitions.windowmoveresizecrossfadetransition.cpp",
      (const char *)(unsigned int)v7,
      v16);
  v8 = CDesktopManager::GetWindowAnimationSettings();
  v9 = CAnimationResource::End(*v2, (float)(v4 + *((float *)v8 + 6)), 0.0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x132,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\transitions.windowmoveresizecrossfadetransition.cpp",
      (const char *)(unsigned int)v9,
      v16);
  v10 = *v2;
  winrt::impl::as<ITransitionAnimationVisualNative,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
    &v18,
    *((_QWORD *)this + 5));
  v11 = v18;
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18);
  v13 = CAnimationResource::AddBinding(v10, v12, 7);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\transitions.windowmoveresizecrossfadetransition.cpp",
      (const char *)(unsigned int)v13,
      v16);
  if ( v11 )
    winrt::com_ptr<IBitmapManager>::unconditional_release_ref(&v18);
}

```

## disassembly

```asm
0x180064768  mov     [rsp+arg_8], rbx
0x18006476d  push    rdi
0x18006476e  sub     rsp, 50h
0x180064772  movaps  [rsp+58h+var_18], xmm6
0x180064777  movaps  [rsp+58h+var_28], xmm7
0x18006477c  mov     rdi, rcx
0x18006477f  lea     rbx, [rcx+40h]
0x180064783  mov     rcx, rbx
0x180064786  call    ?reset@?$com_ptr_t@VCAnimationResource@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CAnimationResource,wil::err_returncode_policy>::reset(void)
0x18006478b  mov     rcx, rbx; struct CAnimationResource **
0x18006478e  call    ?Create@CAnimationResource@@SAJPEAPEAV1@@Z; CAnimationResource::Create(CAnimationResource * *)
0x180064793  mov     rcx, [rsp+58h]; this
0x180064798  test    eax, eax
0x18006479a  jns     short loc_1800647B1
0x18006479c  mov     r9d, eax; char *
0x18006479f  lea     r8, aClientcoreWind_45; "clientcore\\windows\\dwm\\udwm\\transit"...
0x1800647a6  mov     edx, 11Ah; void *
0x1800647ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800647b1  call    ?GetWindowAnimationSettings@CDesktopManager@@SAAEBUWindowAnimationSettings@1@XZ; CDesktopManager::GetWindowAnimationSettings(void)
0x1800647b6  movss   xmm7, dword ptr [rax+1Ch]
0x1800647bb  xorps   xmm6, xmm6
0x1800647be  movss   [rsp+58h+var_30], xmm6; float
0x1800647c4  movss   [rsp+58h+var_38], xmm6; int
0x1800647ca  xorps   xmm3, xmm3; float
0x1800647cd  movss   xmm2, cs:__real@3f800000; float
0x1800647d5  xorps   xmm1, xmm1; double
0x1800647d8  mov     rcx, [rbx]; this
0x1800647db  call    ?AddCubic@CAnimationResource@@UEAAJNMMMM@Z; CAnimationResource::AddCubic(double,float,float,float,float)
0x1800647e0  mov     rcx, [rsp+58h]; this
0x1800647e5  test    eax, eax
0x1800647e7  jns     short loc_1800647FE
0x1800647e9  mov     r9d, eax; char *
0x1800647ec  lea     r8, aClientcoreWind_45; "clientcore\\windows\\dwm\\udwm\\transit"...
0x1800647f3  mov     edx, 124h; void *
0x1800647f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800647fe  movss   xmm3, cs:__real@bf800000
0x180064806  divss   xmm3, xmm7
0x18006480a  call    ?GetWindowAnimationSettings@CDesktopManager@@SAAEBUWindowAnimationSettings@1@XZ; CDesktopManager::GetWindowAnimationSettings(void)
0x18006480f  movss   xmm1, dword ptr [rax+18h]
0x180064814  cvtps2pd xmm1, xmm1; double
0x180064817  movss   [rsp+58h+var_30], xmm6; float
0x18006481d  movss   [rsp+58h+var_38], xmm6; int
0x180064823  movss   xmm2, cs:__real@3f800000; float
0x18006482b  mov     rcx, [rbx]; this
0x18006482e  call    ?AddCubic@CAnimationResource@@UEAAJNMMMM@Z; CAnimationResource::AddCubic(double,float,float,float,float)
0x180064833  mov     rcx, [rsp+58h]; this
0x180064838  test    eax, eax
0x18006483a  jns     short loc_180064851
0x18006483c  mov     r9d, eax; char *
0x18006483f  lea     r8, aClientcoreWind_45; "clientcore\\windows\\dwm\\udwm\\transit"...
0x180064846  mov     edx, 12Dh; void *
0x18006484b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064851  call    ?GetWindowAnimationSettings@CDesktopManager@@SAAEBUWindowAnimationSettings@1@XZ; CDesktopManager::GetWindowAnimationSettings(void)
0x180064856  addss   xmm7, dword ptr [rax+18h]
0x18006485b  cvtps2pd xmm1, xmm7; double
0x18006485e  xorps   xmm2, xmm2; float
0x180064861  mov     rcx, [rbx]; this
0x180064864  call    ?End@CAnimationResource@@UEAAJNM@Z; CAnimationResource::End(double,float)
0x180064869  mov     rcx, [rsp+58h]; this
0x18006486e  test    eax, eax
0x180064870  jns     short loc_180064887
0x180064872  mov     r9d, eax; char *
0x180064875  lea     r8, aClientcoreWind_45; "clientcore\\windows\\dwm\\udwm\\transit"...
0x18006487c  mov     edx, 132h; void *
0x180064881  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180064887  mov     rbx, [rbx]
0x18006488a  mov     rdx, [rdi+28h]
0x18006488e  lea     rcx, [rsp+58h+arg_0]
0x180064893  call    ??$as@UITransitionAnimationVisualNative@@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@$0A@@impl@winrt@@YA?AU?$com_ptr@UITransitionAnimationVisualNative@@@1@PEAUtype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@01@@Z; winrt::impl::as<ITransitionAnimationVisualNative,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type *)
0x180064898  nop
0x180064899  mov     rdi, [rsp+58h+arg_0]
0x18006489e  mov     rax, [rdi]
0x1800648a1  mov     rcx, rdi
0x1800648a4  mov     rax, [rax+30h]
0x1800648a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648ad  mov     r8d, 7
0x1800648b3  mov     rdx, rax
0x1800648b6  mov     rcx, rbx
0x1800648b9  call    ?AddBinding@CAnimationResource@@QEAAJPEAVCResourceProxy@@W4Enum@DwmResourceProperty@@@Z; CAnimationResource::AddBinding(CResourceProxy *,DwmResourceProperty::Enum)
0x1800648be  mov     rcx, [rsp+58h]; this
0x1800648c3  test    eax, eax
0x1800648c5  jns     short loc_1800648DC
0x1800648c7  mov     r9d, eax; char *
0x1800648ca  lea     r8, aClientcoreWind_45; "clientcore\\windows\\dwm\\udwm\\transit"...
0x1800648d1  mov     edx, 138h; void *
0x1800648d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800648dc  test    rdi, rdi
0x1800648df  jz      short loc_1800648EB
0x1800648e1  lea     rcx, [rsp+58h+arg_0]
0x1800648e6  call    ?unconditional_release_ref@?$com_ptr@UIBitmapManager@@@winrt@@AEAAXXZ; winrt::com_ptr<IBitmapManager>::unconditional_release_ref(void)
0x1800648eb  mov     rbx, [rsp+58h+arg_8]
0x1800648f0  movaps  xmm6, [rsp+58h+var_18]
0x1800648f5  movaps  xmm7, [rsp+58h+var_28]
0x1800648fa  add     rsp, 50h
0x1800648fe  pop     rdi
0x1800648ff  retn
```
