# wil_details_StagingConfigFeature::get_IsWexpConfig

- ea: `0x14dd0`
- end: `0x14de4`
- name: `wil_details_StagingConfigFeature::get_IsWexpConfig`
- size: `20`
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
0x14dd0  ldarg.0
0x14dd1  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light wil_details_StagingConfigFeature::BitFieldEncodedData
0x14dd6  ldsfld   valuetype Section wil_details_StagingConfigFeature::IsWexpConfigSection
0x14ddb  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x14de0  ldc.i4.0
0x14de1  cgt.un
0x14de3  ret
```
