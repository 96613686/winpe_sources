# AnonymousUnion2::set_VariantCached

- ea: `0x15700`
- end: `0x15715`
- name: `AnonymousUnion2::set_VariantCached`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14970`

## callees

- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x15700  ldarg.0
0x15701  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15706  ldsfld   valuetype Section AnonymousUnion2::VariantCachedSection
0x1570b  ldarg.1
0x1570c  ldc.i4.0
0x1570d  cgt.un
0x1570f  call     instance void Microsoft.Internal.PInvoke.Util.BitVector32Light::set_Item(valuetype Section section, int32 value)
0x15714  ret
```
