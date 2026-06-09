# Windows::UI::Composition::TemperatureAndTintEffectType::GetShaderFragmentName(void)

- ea: `0x1800281f0`
- end: `0x1800281f8`
- name: `?GetShaderFragmentName@TemperatureAndTintEffectType@Composition@UI@Windows@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Windows::UI::Composition::TemperatureAndTintEffectType *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x1800281f0`: `TempTint`

## pseudocode

```c
const char *__fastcall Windows::UI::Composition::TemperatureAndTintEffectType::GetShaderFragmentName(
        Windows::UI::Composition::TemperatureAndTintEffectType *this)
{
  return "TempTint";
}

```

## disassembly

```asm
0x1800281f0  lea     rax, aTemptint; "TempTint"
0x1800281f7  retn
```
