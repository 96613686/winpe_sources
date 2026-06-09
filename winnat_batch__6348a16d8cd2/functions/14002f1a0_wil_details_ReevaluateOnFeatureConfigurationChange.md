# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14002f1a0`
- end: `0x14002f1b4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002ef70`
- `0x14002f240`

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
0x14002f1a0  sub     rsp, 28h
0x14002f1a4  call    wil_details_UpdateFeatureConfiguredStates
0x14002f1a9  call    wil_details_EvaluateFeatureDependencies
0x14002f1ae  add     rsp, 28h
0x14002f1b2  retn
```
