# CreateEffect<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect>(void)

- ea: `0x18001295c`
- end: `0x1800129bf`
- name: `??$CreateEffect@VColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010ecc`

## callees

- `0x18001295c`
- `0x1800129c8`
- `0x180012a64`
- `0x180012b1c`
- `0x18001eaa0`

## string_xrefs

- `0x180012984`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateEffect<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect>(
        __int64 a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,>(&v6);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
      (const char *)(unsigned int)v2,
      v4);
  winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,0>(
    a1,
    v6);
  if ( v6 )
    winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::unconditional_release_ref(&v6);
  return a1;
}

```

## disassembly

```asm
0x18001295c  push    rdi
0x18001295e  sub     rsp, 30h
0x180012962  mov     rdi, rcx
0x180012965  mov     [rsp+38h+arg_8], 0
0x18001296e  lea     rcx, [rsp+38h+arg_8]
0x180012973  call    ??$MakeAndInitialize@VColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@V123456@$$V@Details@WRL@Microsoft@@YAJPEAPEAVColorSourceEffect@Effects@Composition@UI@Internal@2@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,>(Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect * *)
0x180012978  mov     rcx, [rsp+38h]; this
0x18001297d  test    eax, eax
0x18001297f  jns     short loc_180012996
0x180012981  mov     r9d, eax; char *
0x180012984  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18001298b  mov     edx, 1Dh; void *
0x180012990  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012996  mov     rdx, [rsp+38h+arg_8]
0x18001299b  mov     rcx, rdi
0x18001299e  call    ??$as@UColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@V123456@$0A@@impl@winrt@@YA?AUColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@1@PEAV234567@@Z; winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect,0>(Microsoft::Internal::UI::Composition::Effects::ColorSourceEffect *)
0x1800129a3  nop
0x1800129a4  cmp     [rsp+38h+arg_8], 0
0x1800129aa  jz      short loc_1800129B6
0x1800129ac  lea     rcx, [rsp+38h+arg_8]
0x1800129b1  call    ?unconditional_release_ref@?$com_ptr@VCrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@@winrt@@AEAAXXZ; winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect>::unconditional_release_ref(void)
0x1800129b6  mov     rax, rdi
0x1800129b9  add     rsp, 30h
0x1800129bd  pop     rdi
0x1800129be  retn
```
