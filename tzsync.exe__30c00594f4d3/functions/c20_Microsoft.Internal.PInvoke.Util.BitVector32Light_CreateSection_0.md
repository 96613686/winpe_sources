# Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection_0

- ea: `0xc20`
- end: `0xc35`
- name: `Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection_0`
- size: `21`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x15010`
- `0x151d0`
- `0x158a0`

## callees

- `0xd40`
- `0x13ed0`
- `0x13ee0`

## pseudocode

```c

```

## disassembly

```asm
0xc20  ldarg.0
0xc21  ldarga.s 1
0xc23  call     instance int16 Section::get_Mask()
0xc28  ldarga.s 1
0xc2a  call     instance int16 Section::get_Offset()
0xc2f  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSectionHelper(int16 maxValue, int16 priorMask, int16 priorOffset)
0xc34  ret
```
