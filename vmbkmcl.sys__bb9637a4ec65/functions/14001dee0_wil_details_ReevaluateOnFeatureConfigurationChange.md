# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x14001dee0`
- end: `0x14001def4`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001dc5c`
- `0x14001df80`

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
0x14001dee0  sub     rsp, 28h
0x14001dee4  call    wil_details_UpdateFeatureConfiguredStates
0x14001dee9  call    wil_details_EvaluateFeatureDependencies
0x14001deee  add     rsp, 28h
0x14001def2  retn
```
