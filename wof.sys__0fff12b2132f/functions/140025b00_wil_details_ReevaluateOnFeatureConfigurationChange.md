# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140025b00`
- end: `0x140025b14`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1400258cc`
- `0x140025ba0`

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
0x140025b00  sub     rsp, 28h
0x140025b04  call    wil_details_UpdateFeatureConfiguredStates
0x140025b09  call    wil_details_EvaluateFeatureDependencies
0x140025b0e  add     rsp, 28h
0x140025b12  retn
```
