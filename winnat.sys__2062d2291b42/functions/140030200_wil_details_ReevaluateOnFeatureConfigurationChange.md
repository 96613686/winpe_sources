# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140030200`
- end: `0x140030214`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002ff70`
- `0x1400302a0`

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
0x140030200  sub     rsp, 28h
0x140030204  call    wil_details_UpdateFeatureConfiguredStates
0x140030209  call    wil_details_EvaluateFeatureDependencies
0x14003020e  add     rsp, 28h
0x140030212  retn
```
