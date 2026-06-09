# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1400369f0`
- end: `0x140036a04`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1400367bc`
- `0x140036a90`

## pseudocode

```c
__int64 wil_details_ReevaluateOnFeatureConfigurationChange()
{
  wil_details_UpdateFeatureConfiguredStates();
  return wil_details_EvaluateFeatureDependencies();
}

```

## disassembly

```asm
0x1400369f0  sub     rsp, 28h
0x1400369f4  call    wil_details_UpdateFeatureConfiguredStates
0x1400369f9  call    wil_details_EvaluateFeatureDependencies
0x1400369fe  add     rsp, 28h
0x140036a02  retn
```
