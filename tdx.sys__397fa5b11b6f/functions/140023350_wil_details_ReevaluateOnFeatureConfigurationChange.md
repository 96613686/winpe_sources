# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140023350`
- end: `0x140023364`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1400230c8`
- `0x1400233f0`

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
0x140023350  sub     rsp, 28h
0x140023354  call    wil_details_UpdateFeatureConfiguredStates
0x140023359  call    wil_details_EvaluateFeatureDependencies
0x14002335e  add     rsp, 28h
0x140023362  retn
```
