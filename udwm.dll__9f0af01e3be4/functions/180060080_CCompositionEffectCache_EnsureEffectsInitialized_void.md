# CCompositionEffectCache::EnsureEffectsInitialized(void)

- ea: `0x180060080`
- end: `0x18006048b`
- name: `?EnsureEffectsInitialized@CCompositionEffectCache@@AEAAXXZ`
- size: `1035`
- prototype: `void __fastcall(CCompositionEffectCache *__hidden this)`
- caller_count: `7`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005fe8c`
- `0x18005feac`
- `0x180060040`
- `0x180060060`
- `0x18008e9e4`
- `0x1800ab19c`
- `0x1800ab1bc`

## callees

- `0x180006aa8`
- `0x180060080`
- `0x180060494`
- `0x180060588`
- `0x1800ab1dc`
- `0x1800e05d4`
- `0x1800ea010`

## string_xrefs

- `0x180060371`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x180060386`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x18006039b`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x1800603b0`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x1800603c5`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x1800603da`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x1800603ef`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`
- `0x180060354`: `CCompositionEffectCache::EnsureEffectsInitialized`
- `0x18006034d`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCompositionEffectCache::EnsureEffectsInitialized(
        CCompositionEffectCache *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rdx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  struct Windows::UI::Composition::ICompositionBrush **v21; // r8
  int HostBackdropBrush; // eax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // r8
  unsigned int v39; // [rsp+20h] [rbp-30h]
  __int64 v40; // [rsp+30h] [rbp-20h] BYREF
  __int64 v41; // [rsp+38h] [rbp-18h] BYREF
  __int64 v42; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v44; // [rsp+70h] [rbp+20h] BYREF
  __int64 v45; // [rsp+78h] [rbp+28h] BYREF
  __int64 v46; // [rsp+80h] [rbp+30h] BYREF
  __int64 v47; // [rsp+88h] [rbp+38h] BYREF

  v4 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 53);
  if ( !*(_BYTE *)(v4 + 633) )
    AssertW(
      0,
      L"CDesktopManager::GetWindowList()->IsTransparencyAllowedBySystem()",
      L"CCompositionEffectCache::EnsureEffectsInitialized",
      L"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
      0x24u);
  if ( !*((_BYTE *)this + 72) )
  {
    v42 = 0;
    v5 = CCompositionEffectCache::CreateMicaBrush(CMicaSystemBackdropVisual::sc_darkThemeTintColor, v4, a3, &v42);
    if ( v5 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)v5,
        v39);
    v41 = 0;
    v8 = CCompositionEffectCache::CreateMicaBrush(CMicaSystemBackdropVisual::sc_lightThemeTintColor, v6, v7, &v41);
    if ( v8 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)v8,
        v39);
    v40 = 0;
    v11 = CCompositionEffectCache::CreateDesktopAcrylicBrush(
            CAcrylicSystemBackdropVisual::sc_darkThemeTintColor,
            v9,
            v10,
            &v40);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)v11,
        v39);
    v47 = 0;
    v14 = CCompositionEffectCache::CreateDesktopAcrylicBrush(
            CAcrylicSystemBackdropVisual::sc_lightThemeTintColor,
            v12,
            v13,
            &v47);
    if ( v14 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)v14,
        v39);
    v46 = 0;
    v17 = CCompositionEffectCache::CreateMicaBrush(
            CLightMicaSystemBackdropVisual::sc_darkThemeTintColor,
            v15,
            v16,
            &v46);
    if ( v17 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)v17,
        v39);
    v44 = 0;
    v20 = CCompositionEffectCache::CreateMicaBrush(
            CLightMicaSystemBackdropVisual::sc_lightThemeTintColor,
            v18,
            v19,
            &v44);
    if ( v20 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)v20,
        v39);
    v45 = 0;
    HostBackdropBrush = WindowsInternal::UI::CreateHostBackdropBrush(
                          *(__int64 (__fastcall ****)(WindowsInternal::UI *, GUID *, __int64 *))(*((_QWORD *)CDesktopManager::s_pDesktopManagerInstance
                                                                                                 + 6)
                                                                                               + 32LL),
                          (struct IDCompositionDesktopDevicePartner *)&v45,
                          v21);
    if ( HostBackdropBrush < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
        (const char *)(unsigned int)HostBackdropBrush,
        v39);
    v23 = v42;
    v42 = 0;
    v24 = *((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v23;
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v25 = v41;
    v41 = 0;
    v26 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v25;
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v27 = v40;
    v40 = 0;
    v28 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v27;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v29 = v47;
    v47 = 0;
    v30 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v29;
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v31 = v46;
    v46 = 0;
    v32 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v31;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v33 = v44;
    v34 = 0;
    v44 = 0;
    v35 = *((_QWORD *)this + 6);
    *((_QWORD *)this + 6) = v33;
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v34 = v44;
    }
    v36 = v45;
    v37 = 0;
    v45 = 0;
    v38 = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v36;
    if ( v38 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v34 = v44;
      v37 = v45;
    }
    *((_BYTE *)this + 72) = 1;
    if ( v37 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      v34 = v44;
    }
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
}

```

## disassembly

```asm
0x180060080  push    rbp
0x180060082  push    rbx
0x180060083  push    rdi
0x180060084  mov     rbp, rsp
0x180060087  sub     rsp, 50h
0x18006008b  mov     rbx, rcx
0x18006008e  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180060095  mov     rdx, [rax+1A8h]
0x18006009c  xor     edi, edi
0x18006009e  cmp     [rdx+279h], dil
0x1800600a5  jz      loc_180060345
0x1800600ab  cmp     [rbx+48h], dil
0x1800600af  jz      short loc_1800600B9
0x1800600b1  add     rsp, 50h
0x1800600b5  pop     rdi
0x1800600b6  pop     rbx
0x1800600b7  pop     rbp
0x1800600b8  retn
0x1800600b9  mov     [rbp+var_10], rdi
0x1800600bd  lea     r9, [rbp+var_10]
0x1800600c1  movss   xmm2, cs:__real@3f800000
0x1800600c9  movss   xmm1, cs:__real@3f4ccccd
0x1800600d1  mov     ecx, cs:?sc_darkThemeTintColor@CMicaSystemBackdropVisual@@2UColor@UI@Windows@@B; Windows::UI::Color const CMicaSystemBackdropVisual::sc_darkThemeTintColor
0x1800600d7  call    ?CreateMicaBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z; CCompositionEffectCache::CreateMicaBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)
0x1800600dc  mov     rcx, [rbp+18h]; this
0x1800600e0  test    eax, eax
0x1800600e2  js      loc_18006036E
0x1800600e8  mov     [rbp+var_18], rdi
0x1800600ec  lea     r9, [rbp+var_18]
0x1800600f0  movss   xmm2, cs:__real@3f800000
0x1800600f8  movss   xmm1, cs:__real@3f000000
0x180060100  mov     ecx, cs:?sc_lightThemeTintColor@CMicaSystemBackdropVisual@@2UColor@UI@Windows@@B; Windows::UI::Color const CMicaSystemBackdropVisual::sc_lightThemeTintColor
0x180060106  call    ?CreateMicaBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z; CCompositionEffectCache::CreateMicaBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)
0x18006010b  mov     rcx, [rbp+18h]; this
0x18006010f  test    eax, eax
0x180060111  js      loc_180060383
0x180060117  mov     [rbp+var_20], rdi
0x18006011b  lea     r9, [rbp+var_20]
0x18006011f  movss   xmm2, cs:__real@3f23d70a
0x180060127  xorps   xmm1, xmm1
0x18006012a  mov     ecx, cs:?sc_darkThemeTintColor@CAcrylicSystemBackdropVisual@@2UColor@UI@Windows@@B; Windows::UI::Color const CAcrylicSystemBackdropVisual::sc_darkThemeTintColor
0x180060130  call    ?CreateDesktopAcrylicBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z; CCompositionEffectCache::CreateDesktopAcrylicBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)
0x180060135  mov     rcx, [rbp+18h]; this
0x180060139  test    eax, eax
0x18006013b  js      loc_180060398
0x180060141  mov     [rbp+arg_18], rdi
0x180060145  lea     r9, [rbp+arg_18]
0x180060149  movss   xmm2, cs:__real@3f23d70a
0x180060151  xorps   xmm1, xmm1
0x180060154  mov     ecx, cs:?sc_lightThemeTintColor@CAcrylicSystemBackdropVisual@@2UColor@UI@Windows@@B; Windows::UI::Color const CAcrylicSystemBackdropVisual::sc_lightThemeTintColor
0x18006015a  call    ?CreateDesktopAcrylicBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z; CCompositionEffectCache::CreateDesktopAcrylicBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)
0x18006015f  mov     rcx, [rbp+18h]; this
0x180060163  test    eax, eax
0x180060165  js      loc_1800603AD
0x18006016b  mov     [rbp+arg_10], rdi
0x18006016f  lea     r9, [rbp+arg_10]
0x180060173  movss   xmm2, cs:__real@3f800000
0x18006017b  xorps   xmm1, xmm1
0x18006017e  mov     ecx, cs:?sc_darkThemeTintColor@CLightMicaSystemBackdropVisual@@2UColor@UI@Windows@@B; Windows::UI::Color const CLightMicaSystemBackdropVisual::sc_darkThemeTintColor
0x180060184  call    ?CreateMicaBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z; CCompositionEffectCache::CreateMicaBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)
0x180060189  mov     rcx, [rbp+18h]; this
0x18006018d  test    eax, eax
0x18006018f  js      loc_1800603C2
0x180060195  mov     [rbp+arg_0], rdi
0x180060199  lea     r9, [rbp+arg_0]
0x18006019d  movss   xmm2, cs:__real@3f800000
0x1800601a5  movss   xmm1, cs:__real@3f000000
0x1800601ad  mov     ecx, cs:?sc_lightThemeTintColor@CLightMicaSystemBackdropVisual@@2UColor@UI@Windows@@B; Windows::UI::Color const CLightMicaSystemBackdropVisual::sc_lightThemeTintColor
0x1800601b3  call    ?CreateMicaBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z; CCompositionEffectCache::CreateMicaBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)
0x1800601b8  mov     rcx, [rbp+18h]; this
0x1800601bc  test    eax, eax
0x1800601be  js      loc_1800603D7
0x1800601c4  mov     [rbp+arg_8], rdi
0x1800601c8  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800601cf  mov     rcx, [rax+30h]
0x1800601d3  lea     rdx, [rbp+arg_8]; struct IDCompositionDesktopDevicePartner *
0x1800601d7  mov     rcx, [rcx+20h]; this
0x1800601db  call    ?CreateHostBackdropBrush@UI@WindowsInternal@@YAJPEAUIDCompositionDesktopDevicePartner@@PEAPEAUICompositionBrush@Composition@1Windows@@@Z; WindowsInternal::UI::CreateHostBackdropBrush(IDCompositionDesktopDevicePartner *,Windows::UI::Composition::ICompositionBrush * *)
0x1800601e0  mov     rcx, [rbp+18h]; this
0x1800601e4  test    eax, eax
0x1800601e6  js      loc_1800603EC
0x1800601ec  mov     rax, [rbp+var_10]
0x1800601f0  mov     [rbp+var_10], rdi
0x1800601f4  mov     rcx, [rbx+8]
0x1800601f8  mov     [rbx+8], rax
0x1800601fc  test    rcx, rcx
0x1800601ff  jnz     loc_180060401
0x180060205  mov     rax, [rbp+var_18]
0x180060209  mov     [rbp+var_18], rdi
0x18006020d  mov     rcx, [rbx+10h]
0x180060211  mov     [rbx+10h], rax
0x180060215  test    rcx, rcx
0x180060218  jnz     loc_180060412
0x18006021e  mov     rax, [rbp+var_20]
0x180060222  mov     [rbp+var_20], rdi
0x180060226  mov     rcx, [rbx+18h]
0x18006022a  mov     [rbx+18h], rax
0x18006022e  test    rcx, rcx
0x180060231  jnz     loc_180060423
0x180060237  mov     rax, [rbp+arg_18]
0x18006023b  mov     [rbp+arg_18], rdi
0x18006023f  mov     rcx, [rbx+20h]
0x180060243  mov     [rbx+20h], rax
0x180060247  test    rcx, rcx
0x18006024a  jnz     loc_180060434
0x180060250  mov     rax, [rbp+arg_10]
0x180060254  mov     [rbp+arg_10], rdi
0x180060258  mov     rcx, [rbx+28h]
0x18006025c  mov     [rbx+28h], rax
0x180060260  test    rcx, rcx
0x180060263  jnz     loc_180060445
0x180060269  mov     rax, [rbp+arg_0]
0x18006026d  mov     rcx, rdi
0x180060270  mov     [rbp+arg_0], rcx
0x180060274  mov     rdx, [rbx+30h]
0x180060278  mov     [rbx+30h], rax
0x18006027c  test    rdx, rdx
0x18006027f  jnz     loc_180060456
0x180060285  mov     rdx, [rbp+arg_8]
0x180060289  mov     rax, rdi
0x18006028c  mov     [rbp+arg_8], rax
0x180060290  mov     r8, [rbx+38h]
0x180060294  mov     [rbx+38h], rdx
0x180060298  test    r8, r8
0x18006029b  jnz     loc_18006046E
0x1800602a1  mov     byte ptr [rbx+48h], 1
0x1800602a5  test    rax, rax
0x1800602a8  jz      short loc_1800602C0
0x1800602aa  mov     rcx, [rax]
0x1800602ad  mov     rdx, [rcx+10h]
0x1800602b1  mov     rcx, rax
0x1800602b4  mov     rax, rdx
0x1800602b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602bc  mov     rcx, [rbp+arg_0]
0x1800602c0  test    rcx, rcx
0x1800602c3  jz      short loc_1800602D2
0x1800602c5  mov     rax, [rcx]
0x1800602c8  mov     rax, [rax+10h]
0x1800602cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602d1  nop
0x1800602d2  mov     rcx, [rbp+arg_10]
0x1800602d6  test    rcx, rcx
0x1800602d9  jz      short loc_1800602E8
0x1800602db  mov     rax, [rcx]
0x1800602de  mov     rax, [rax+10h]
0x1800602e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602e7  nop
0x1800602e8  mov     rcx, [rbp+arg_18]
0x1800602ec  test    rcx, rcx
0x1800602ef  jz      short loc_1800602FE
0x1800602f1  mov     rax, [rcx]
0x1800602f4  mov     rax, [rax+10h]
0x1800602f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602fd  nop
0x1800602fe  mov     rcx, [rbp+var_20]
0x180060302  test    rcx, rcx
0x180060305  jz      short loc_180060314
0x180060307  mov     rax, [rcx]
0x18006030a  mov     rax, [rax+10h]
0x18006030e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060313  nop
0x180060314  mov     rcx, [rbp+var_18]
0x180060318  test    rcx, rcx
0x18006031b  jz      short loc_18006032A
0x18006031d  mov     rax, [rcx]
0x180060320  mov     rax, [rax+10h]
0x180060324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060329  nop
0x18006032a  mov     rcx, [rbp+var_10]
0x18006032e  test    rcx, rcx
0x180060331  jz      short loc_180060340
0x180060333  mov     rax, [rcx]
0x180060336  mov     rax, [rax+10h]
0x18006033a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006033f  nop
0x180060340  jmp     loc_1800600B1
0x180060345  mov     [rsp+50h+var_30], 24h ; '$'; unsigned int
0x18006034d  lea     r9, aClientcoreWind; "clientcore\\windows\\dwm\\udwm\\composi"...
0x180060354  lea     r8, aCcompositionef; "CCompositionEffectCache::EnsureEffectsI"...
0x18006035b  lea     rdx, aCdesktopmanage_0; "CDesktopManager::GetWindowList()->IsTra"...
0x180060362  xor     ecx, ecx; unsigned __int16 *
0x180060364  call    ?AssertW@@YAXPEBG000K@Z; AssertW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180060369  jmp     loc_1800600AB
0x18006036e  mov     r9d, eax; char *
0x180060371  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x180060378  mov     edx, 31h ; '1'; void *
0x18006037d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180060383  mov     r9d, eax; char *
0x180060386  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006038d  mov     edx, 38h ; '8'; void *
0x180060392  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180060398  mov     r9d, eax; char *
0x18006039b  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x1800603a2  mov     edx, 40h ; '@'; void *
0x1800603a7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800603ad  mov     r9d, eax; char *
0x1800603b0  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x1800603b7  mov     edx, 47h ; 'G'; void *
0x1800603bc  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800603c2  mov     r9d, eax; char *
0x1800603c5  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x1800603cc  mov     edx, 4Fh ; 'O'; void *
0x1800603d1  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800603d7  mov     r9d, eax; char *
0x1800603da  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x1800603e1  mov     edx, 56h ; 'V'; void *
0x1800603e6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800603ec  mov     r9d, eax; char *
0x1800603ef  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x1800603f6  mov     edx, 5Dh ; ']'; void *
0x1800603fb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180060401  mov     rax, [rcx]
0x180060404  mov     rax, [rax+10h]
0x180060408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006040d  jmp     loc_180060205
0x180060412  mov     rax, [rcx]
0x180060415  mov     rax, [rax+10h]
0x180060419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006041e  jmp     loc_18006021E
0x180060423  mov     rax, [rcx]
0x180060426  mov     rax, [rax+10h]
0x18006042a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006042f  jmp     loc_180060237
0x180060434  mov     rax, [rcx]
0x180060437  mov     rax, [rax+10h]
0x18006043b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060440  jmp     loc_180060250
0x180060445  mov     rax, [rcx]
0x180060448  mov     rax, [rax+10h]
0x18006044c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060451  jmp     loc_180060269
0x180060456  mov     rax, [rdx]
0x180060459  mov     rcx, rdx
0x18006045c  mov     rax, [rax+10h]
0x180060460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060465  mov     rcx, [rbp+arg_0]
0x180060469  jmp     loc_180060285
0x18006046e  mov     rax, [r8]
0x180060471  mov     rcx, r8
0x180060474  mov     rax, [rax+10h]
0x180060478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006047d  mov     rcx, [rbp+arg_0]
0x180060481  mov     rax, [rbp+arg_8]
0x180060485  jmp     loc_1800602A1
```
