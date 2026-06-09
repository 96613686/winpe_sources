# Windows::UI::Composition::CompositeEffectType::GetShaderFragmentName(void)

- ea: `0x18001b6c0`
- end: `0x18001b6c8`
- name: `?GetShaderFragmentName@CompositeEffectType@Composition@UI@Windows@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Windows::UI::Composition::CompositeEffectType *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x18001b6c0`: `Composite`

## pseudocode

```c
const char *__fastcall Windows::UI::Composition::CompositeEffectType::GetShaderFragmentName(
        Windows::UI::Composition::CompositeEffectType *this)
{
  return "Composite";
}

```

## disassembly

```asm
0x18001b6c0  lea     rax, aComposite; "Composite"
0x18001b6c7  retn
```
