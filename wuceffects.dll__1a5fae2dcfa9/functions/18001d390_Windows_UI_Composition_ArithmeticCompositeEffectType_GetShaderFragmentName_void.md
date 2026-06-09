# Windows::UI::Composition::ArithmeticCompositeEffectType::GetShaderFragmentName(void)

- ea: `0x18001d390`
- end: `0x18001d398`
- name: `?GetShaderFragmentName@ArithmeticCompositeEffectType@Composition@UI@Windows@@UEBAPEBDXZ`
- size: `8`
- prototype: `const char *__fastcall(Windows::UI::Composition::ArithmeticCompositeEffectType *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x18001d390`: `ArithComp`

## pseudocode

```c
const char *__fastcall Windows::UI::Composition::ArithmeticCompositeEffectType::GetShaderFragmentName(
        Windows::UI::Composition::ArithmeticCompositeEffectType *this)
{
  return "ArithComp";
}

```

## disassembly

```asm
0x18001d390  lea     rax, aArithcomp; "ArithComp"
0x18001d397  retn
```
