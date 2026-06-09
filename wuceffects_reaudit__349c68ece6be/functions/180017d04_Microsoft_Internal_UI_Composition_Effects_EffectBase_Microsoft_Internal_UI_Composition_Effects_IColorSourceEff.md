# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>::~EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>(void)

- ea: `0x180017d04`
- end: `0x180017d2c`
- name: `??1?$EffectBase@UIColorSourceEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@UEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017bec`
- `0x180017c14`
- `0x18001b1a0`
- `0x1800294b0`

## callees

- `0x180017d34`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017d11`

## pseudocode

```c
__int64 __fastcall Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>::~EffectBase<Microsoft::Internal::UI::Composition::Effects::IColorSourceEffect>(
        __int64 a1)
{
  WindowsDeleteString(*(HSTRING *)(a1 + 56));
  *(_QWORD *)(a1 + 56) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>(a1);
}

```

## disassembly

```asm
0x180017d04  push    rbx
0x180017d06  sub     rsp, 20h
0x180017d0a  mov     rbx, rcx
0x180017d0d  mov     rcx, [rcx+38h]; string
0x180017d11  call    cs:__imp_WindowsDeleteString
0x180017d17  mov     rcx, rbx
0x180017d1a  mov     qword ptr [rbx+38h], 0
0x180017d22  add     rsp, 20h
0x180017d26  pop     rbx
0x180017d27  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIGraphicsEffect@Effects@Graphics@Windows@@UIGraphicsEffectSource@567@UIGraphicsEffectD2D1Interop@567@UIOpacityEffect@5Composition@UI@Internal@3@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IOpacityEffect>(void)
```
