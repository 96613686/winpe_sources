# CreateEffect<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect>(void)

- ea: `0x18001254c`
- end: `0x1800125af`
- name: `??$CreateEffect@VOpacityEffect@Effects@Composition@UI@Internal@Microsoft@@U123456winrt@@@@YA?AUOpacityEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@XZ`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010ecc`

## callees

- `0x18001254c`
- `0x1800125b8`
- `0x1800129e0`
- `0x1800130b0`
- `0x18001eaa0`

## string_xrefs

- `0x180012574`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateEffect<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect>(
        __int64 a1)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,Microsoft::Internal::UI::Composition::Effects::OpacityEffect,>(&v6);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
      (const char *)(unsigned int)v2,
      v4);
  winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect,Microsoft::Internal::UI::Composition::Effects::OpacityEffect,0>(
    a1,
    v6);
  if ( v6 )
    winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::OpacityEffect>::unconditional_release_ref(&v6);
  return a1;
}

```

## disassembly

```asm
0x18001254c  push    rdi
0x18001254e  sub     rsp, 30h
0x180012552  mov     rdi, rcx
0x180012555  mov     [rsp+38h+arg_8], 0
0x18001255e  lea     rcx, [rsp+38h+arg_8]
0x180012563  call    ??$MakeAndInitialize@VOpacityEffect@Effects@Composition@UI@Internal@Microsoft@@V123456@$$V@Details@WRL@Microsoft@@YAJPEAPEAVOpacityEffect@Effects@Composition@UI@Internal@2@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Internal::UI::Composition::Effects::OpacityEffect,Microsoft::Internal::UI::Composition::Effects::OpacityEffect,>(Microsoft::Internal::UI::Composition::Effects::OpacityEffect * *)
0x180012568  mov     rcx, [rsp+38h]; this
0x18001256d  test    eax, eax
0x18001256f  jns     short loc_180012586
0x180012571  mov     r9d, eax; char *
0x180012574  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18001257b  mov     edx, 1Dh; void *
0x180012580  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012586  mov     rdx, [rsp+38h+arg_8]
0x18001258b  mov     rcx, rdi
0x18001258e  call    ??$as@UOpacityEffect@Effects@Composition@UI@Internal@Microsoft@winrt@@V123456@$0A@@impl@winrt@@YA?AUOpacityEffect@Effects@Composition@UI@Internal@Microsoft@1@PEAV234567@@Z; winrt::impl::as<winrt::Microsoft::Internal::UI::Composition::Effects::OpacityEffect,Microsoft::Internal::UI::Composition::Effects::OpacityEffect,0>(Microsoft::Internal::UI::Composition::Effects::OpacityEffect *)
0x180012593  nop
0x180012594  cmp     [rsp+38h+arg_8], 0
0x18001259a  jz      short loc_1800125A6
0x18001259c  lea     rcx, [rsp+38h+arg_8]
0x1800125a1  call    ?unconditional_release_ref@?$com_ptr@VOpacityEffect@Effects@Composition@UI@Internal@Microsoft@@@winrt@@AEAAXXZ; winrt::com_ptr<Microsoft::Internal::UI::Composition::Effects::OpacityEffect>::unconditional_release_ref(void)
0x1800125a6  mov     rax, rdi
0x1800125a9  add     rsp, 30h
0x1800125ad  pop     rdi
0x1800125ae  retn
```
