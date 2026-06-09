# AnonymousUnion2::get_IsWexpConfiguration

- ea: `0x15820`
- end: `0x15834`
- name: `AnonymousUnion2::get_IsWexpConfiguration`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14ad0`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x15820  ldarg.0
0x15821  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15826  ldsfld   valuetype Section AnonymousUnion2::IsWexpConfigurationSection
0x1582b  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x15830  ldc.i4.0
0x15831  cgt.un
0x15833  ret
```
