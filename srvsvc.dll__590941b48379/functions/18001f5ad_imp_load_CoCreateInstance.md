# __imp_load_CoCreateInstance

- ea: `0x18001f5ad`
- end: `0x18001f5b9`
- name: `__imp_load_CoCreateInstance`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f51c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f5ad`

## pseudocode

```c
__int64 load_CoCreateInstance()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001f5ad  lea     rax, __imp_CoCreateInstance
0x18001f5b4  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
