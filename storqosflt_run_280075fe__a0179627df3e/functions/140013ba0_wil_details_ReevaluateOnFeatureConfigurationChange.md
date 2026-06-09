# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140013ba0`
- end: `0x140013bb4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001396c`
- `0x140013c40`

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
0x140013ba0  sub     rsp, 28h
0x140013ba4  call    wil_details_UpdateFeatureConfiguredStates
0x140013ba9  call    wil_details_EvaluateFeatureDependencies
0x140013bae  add     rsp, 28h
0x140013bb2  retn
```
