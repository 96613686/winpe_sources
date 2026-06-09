# wil_details_StagingConfigFeature::get_ServiceState

- ea: `0x14e50`
- end: `0x14e61`
- name: `wil_details_StagingConfigFeature::get_ServiceState`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

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
0x14e50  ldarg.0
0x14e51  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light wil_details_StagingConfigFeature::BitFieldEncodedData
0x14e56  ldsfld   valuetype Section wil_details_StagingConfigFeature::ServiceStateSection
0x14e5b  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x14e60  ret
```
