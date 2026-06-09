# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140036a40`
- end: `0x140036a54`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1400367bc`
- `0x140036ae0`

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
0x140036a40  sub     rsp, 28h
0x140036a44  call    wil_details_UpdateFeatureConfiguredStates
0x140036a49  call    wil_details_EvaluateFeatureDependencies
0x140036a4e  add     rsp, 28h
0x140036a52  retn
```
