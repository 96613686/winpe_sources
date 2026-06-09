# __imp_load_SystemParametersInfoW

- ea: `0x180001512`
- end: `0x18000151e`
- name: `__imp_load_SystemParametersInfoW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x180001512`

## pseudocode

```c
__int64 load_SystemParametersInfoW()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180001512  lea     rax, __imp_SystemParametersInfoW
0x180001519  jmp     __tailMerge_user32_dll
```
