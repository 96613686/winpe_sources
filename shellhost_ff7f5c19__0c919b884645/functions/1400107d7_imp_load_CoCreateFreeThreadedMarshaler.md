# __imp_load_CoCreateFreeThreadedMarshaler

- ea: `0x1400107d7`
- end: `0x1400107e3`
- name: `__imp_load_CoCreateFreeThreadedMarshaler`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140010716`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400107d7`

## pseudocode

```c
__int64 load_CoCreateFreeThreadedMarshaler()
{
  return _tailMerge_api_ms_win_core_com_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400107d7  lea     rax, __imp_CoCreateFreeThreadedMarshaler
0x1400107de  jmp     __tailMerge_api_ms_win_core_com_l1_1_0_dll
```
