# wil_details_StagingConfigFeature::.cctor

- ea: `0x15010`
- end: `0x150b2`
- name: `wil_details_StagingConfigFeature::.cctor`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0xc10`
- `0xc20`

## pseudocode

```c

```

## disassembly

```asm
0x15010  ldc.i4.1
0x15011  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue)
0x15016  stsfld   valuetype Section wil_details_StagingConfigFeature::ChangedInSessionSection
0x1501b  ldc.i4.1
0x1501c  ldsfld   valuetype Section wil_details_StagingConfigFeature::ChangedInSessionSection
0x15021  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x15026  stsfld   valuetype Section wil_details_StagingConfigFeature::IsWexpConfigSection
0x1502b  ldc.i4.s 0x3F
0x1502d  ldsfld   valuetype Section wil_details_StagingConfigFeature::IsWexpConfigSection
0x15032  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x15037  stsfld   valuetype Section wil_details_StagingConfigFeature::Unused1Section
0x1503c  ldc.i4.3
0x1503d  ldsfld   valuetype Section wil_details_StagingConfigFeature::Unused1Section
0x15042  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x15047  stsfld   valuetype Section wil_details_StagingConfigFeature::ServiceStateSection
0x1504c  ldc.i4.3
0x1504d  ldsfld   valuetype Section wil_details_StagingConfigFeature::ServiceStateSection
0x15052  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x15057  stsfld   valuetype Section wil_details_StagingConfigFeature::UserStateSection
0x1505c  ldc.i4.3
0x1505d  ldsfld   valuetype Section wil_details_StagingConfigFeature::UserStateSection
0x15062  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x15067  stsfld   valuetype Section wil_details_StagingConfigFeature::TestStateSection
0x1506c  ldc.i4.3
0x1506d  ldsfld   valuetype Section wil_details_StagingConfigFeature::TestStateSection
0x15072  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x15077  stsfld   valuetype Section wil_details_StagingConfigFeature::Unused2Section
0x1507c  ldc.i4   0xFF
0x15081  ldsfld   valuetype Section wil_details_StagingConfigFeature::Unused2Section
0x15086  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x1508b  stsfld   valuetype Section wil_details_StagingConfigFeature::Unused3Section
0x15090  ldc.i4.s 0x3F
0x15092  ldsfld   valuetype Section wil_details_StagingConfigFeature::Unused3Section
0x15097  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x1509c  stsfld   valuetype Section wil_details_StagingConfigFeature::VariantSection
0x150a1  ldc.i4.3
0x150a2  ldsfld   valuetype Section wil_details_StagingConfigFeature::VariantSection
0x150a7  call     valuetype Section Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSection(int16 maxValue, valuetype Section previous)
0x150ac  stsfld   valuetype Section wil_details_StagingConfigFeature::PayloadKindSection
0x150b1  ret
```
