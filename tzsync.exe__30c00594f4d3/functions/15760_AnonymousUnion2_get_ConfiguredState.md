# AnonymousUnion2::get_ConfiguredState

- ea: `0x15760`
- end: `0x15771`
- name: `AnonymousUnion2::get_ConfiguredState`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14a10`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x15760  ldarg.0
0x15761  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15766  ldsfld   valuetype Section AnonymousUnion2::ConfiguredStateSection
0x1576b  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x15770  ret
```
