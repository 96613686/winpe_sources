# __std_type_info_compare

- ea: `0x180004106`
- end: `0x18000410c`
- name: `__std_type_info_compare`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800159b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x180004106`

## pseudocode

```c
// attributes: thunk
__int64 _std_type_info_compare()
{
  return __std_type_info_compare();
}

```

## disassembly

```asm
0x180004106  jmp     cs:__imp___std_type_info_compare
```
