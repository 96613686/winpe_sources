# wil_details_ReevaluateOnFeatureConfigurationChange

- ea: `0x140017e40`
- end: `0x140017e54`
- name: `wil_details_ReevaluateOnFeatureConfigurationChange`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x140017bb0`
- `0x140017ee0`

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
0x140017e40  sub     rsp, 28h
0x140017e44  call    wil_details_UpdateFeatureConfiguredStates
0x140017e49  call    wil_details_EvaluateFeatureDependencies
0x140017e4e  add     rsp, 28h
0x140017e52  retn
```
