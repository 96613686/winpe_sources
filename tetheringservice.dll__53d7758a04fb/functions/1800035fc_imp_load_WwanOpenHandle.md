# __imp_load_WwanOpenHandle

- ea: `0x1800035fc`
- end: `0x180003608`
- name: `__imp_load_WwanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003502`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800035fc`

## pseudocode

```c
__int64 load_WwanOpenHandle()
{
  return _tailMerge_ext_ms_win_wwan_wwapi_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800035fc  lea     rax, __imp_WwanOpenHandle
0x180003603  jmp     __tailMerge_ext_ms_win_wwan_wwapi_l1_1_0_dll
```
