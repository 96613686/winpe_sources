# wil_details_StagingConfigFeature::get_TestState

- ea: `0x14ed0`
- end: `0x14ee1`
- name: `wil_details_StagingConfigFeature::get_TestState`
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
0x14ed0  ldarg.0
0x14ed1  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light wil_details_StagingConfigFeature::BitFieldEncodedData
0x14ed6  ldsfld   valuetype Section wil_details_StagingConfigFeature::TestStateSection
0x14edb  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x14ee0  ret
```
