# Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection

- ea: `0xc10`
- end: `0xc19`
- name: `Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection`
- size: `9`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x15010`
- `0x151d0`
- `0x158a0`

## callees

- `0xd40`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldarg.0
0xc11  ldc.i4.0
0xc12  ldc.i4.0
0xc13  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSectionHelper(int16 maxValue, int16 priorMask, int16 priorOffset)
0xc18  ret
```
