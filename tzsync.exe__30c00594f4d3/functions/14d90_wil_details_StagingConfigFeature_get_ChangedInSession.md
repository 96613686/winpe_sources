# wil_details_StagingConfigFeature::get_ChangedInSession

- ea: `0x14d90`
- end: `0x14da4`
- name: `wil_details_StagingConfigFeature::get_ChangedInSession`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x12c70`
- `0x12ee0`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x14d90  ldarg.0
0x14d91  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light wil_details_StagingConfigFeature::BitFieldEncodedData
0x14d96  ldsfld   valuetype Section wil_details_StagingConfigFeature::ChangedInSessionSection
0x14d9b  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x14da0  ldc.i4.0
0x14da1  cgt.un
0x14da3  ret
```
