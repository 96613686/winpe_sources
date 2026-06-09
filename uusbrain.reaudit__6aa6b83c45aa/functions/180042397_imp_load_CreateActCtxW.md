# __imp_load_CreateActCtxW

- ea: `0x180042397`
- end: `0x1800423a3`
- name: `__imp_load_CreateActCtxW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180042318`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180042397`

## pseudocode

```c
__int64 load_CreateActCtxW()
{
  return _tailMerge_api_ms_win_core_sidebyside_l1_1_0_dll();
}

```

## disassembly

```asm
0x180042397  lea     rax, __imp_CreateActCtxW
0x18004239e  jmp     __tailMerge_api_ms_win_core_sidebyside_l1_1_0_dll
```
