# AnonymousUnion2::set_IsWexpConfiguration

- ea: `0x15840`
- end: `0x15855`
- name: `AnonymousUnion2::set_IsWexpConfiguration`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14af0`

## callees

- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x15840  ldarg.0
0x15841  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15846  ldsfld   valuetype Section AnonymousUnion2::IsWexpConfigurationSection
0x1584b  ldarg.1
0x1584c  ldc.i4.0
0x1584d  cgt.un
0x1584f  call     instance void Microsoft.Internal.PInvoke.Util.BitVector32Light::set_Item(valuetype Section section, int32 value)
0x15854  ret
```
