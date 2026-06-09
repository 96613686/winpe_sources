# AnonymousUnion2::get_StateCached

- ea: `0x15660`
- end: `0x15674`
- name: `AnonymousUnion2::get_StateCached`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x148d0`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x15660  ldarg.0
0x15661  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15666  ldsfld   valuetype Section AnonymousUnion2::StateCachedSection
0x1566b  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x15670  ldc.i4.0
0x15671  cgt.un
0x15673  ret
```
