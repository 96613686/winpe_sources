# __imp_load_WwanOpenHandle

- ea: `0x180002a92`
- end: `0x180002a9e`
- name: `__imp_load_WwanOpenHandle`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002a13`

## import_xrefs

- `wwapi!WwanOpenHandle` at `0x180002a92`

## pseudocode

```c
__int64 load_WwanOpenHandle()
{
  return _tailMerge_wwapi_dll();
}

```

## disassembly

```asm
0x180002a92  lea     rax, __imp_WwanOpenHandle
0x180002a99  jmp     __tailMerge_wwapi_dll
```
