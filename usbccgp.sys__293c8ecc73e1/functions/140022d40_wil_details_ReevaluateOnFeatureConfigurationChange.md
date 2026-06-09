# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140022d40`
- end: `0x140022d54`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140022de0`
- `0x14002dd58`

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
0x140022d40  sub     rsp, 28h
0x140022d44  call    wil_details_UpdateFeatureConfiguredStates
0x140022d49  call    wil_details_EvaluateFeatureDependencies
0x140022d4e  add     rsp, 28h
0x140022d52  retn
```
