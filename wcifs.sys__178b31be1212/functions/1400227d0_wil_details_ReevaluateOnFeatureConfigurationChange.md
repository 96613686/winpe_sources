# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x1400227d0`
- end: `0x1400227e4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002254c`
- `0x140022870`

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
0x1400227d0  sub     rsp, 28h
0x1400227d4  call    wil_details_UpdateFeatureConfiguredStates
0x1400227d9  call    wil_details_EvaluateFeatureDependencies
0x1400227de  add     rsp, 28h
0x1400227e2  retn
```
