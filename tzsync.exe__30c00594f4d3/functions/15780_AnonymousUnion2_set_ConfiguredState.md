# AnonymousUnion2::set_ConfiguredState

- ea: `0x15780`
- end: `0x15792`
- name: `AnonymousUnion2::set_ConfiguredState`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14a30`

## callees

- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x15780  ldarg.0
0x15781  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15786  ldsfld   valuetype Section AnonymousUnion2::ConfiguredStateSection
0x1578b  ldarg.1
0x1578c  call     instance void Microsoft.Internal.PInvoke.Util.BitVector32Light::set_Item(valuetype Section section, int32 value)
0x15791  ret
```
