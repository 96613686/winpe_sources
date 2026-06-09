# AnonymousUnion2::get_VariantCached

- ea: `0x156e0`
- end: `0x156f4`
- name: `AnonymousUnion2::get_VariantCached`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14950`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x156e0  ldarg.0
0x156e1  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x156e6  ldsfld   valuetype Section AnonymousUnion2::VariantCachedSection
0x156eb  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x156f0  ldc.i4.0
0x156f1  cgt.un
0x156f3  ret
```
