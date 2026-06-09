# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14000b4c0`
- end: `0x14000b4d4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14000b238`
- `0x14000b560`

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
0x14000b4c0  sub     rsp, 28h
0x14000b4c4  call    wil_details_UpdateFeatureConfiguredStates
0x14000b4c9  call    wil_details_EvaluateFeatureDependencies
0x14000b4ce  add     rsp, 28h
0x14000b4d2  retn
```
