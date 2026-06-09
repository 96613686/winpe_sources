# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140027b80`
- end: `0x140027b94`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14002794c`
- `0x140027c20`

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
0x140027b80  sub     rsp, 28h
0x140027b84  call    wil_details_UpdateFeatureConfiguredStates
0x140027b89  call    wil_details_EvaluateFeatureDependencies
0x140027b8e  add     rsp, 28h
0x140027b92  retn
```
