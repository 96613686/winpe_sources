# wil_details_StagingConfigFeature::get_Variant

- ea: `0x14f90`
- end: `0x14fa1`
- name: `wil_details_StagingConfigFeature::get_Variant`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x12c70`
- `0x12fa0`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x14f90  ldarg.0
0x14f91  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light wil_details_StagingConfigFeature::BitFieldEncodedData
0x14f96  ldsfld   valuetype Section wil_details_StagingConfigFeature::VariantSection
0x14f9b  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x14fa0  ret
```
