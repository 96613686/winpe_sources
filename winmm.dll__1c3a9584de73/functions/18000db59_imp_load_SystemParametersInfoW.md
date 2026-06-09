# __imp_load_SystemParametersInfoW

- ea: `0x18000db59`
- end: `0x18000db65`
- name: `__imp_load_SystemParametersInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000dada`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18000db59`

## pseudocode

```c
__int64 load_SystemParametersInfoW()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000db59  lea     rax, __imp_SystemParametersInfoW
0x18000db60  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_sysparams_l1_1_0_dll
```
