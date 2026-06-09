# __imp_load_HtCreateHandleTable

- ea: `0x1800096ac`
- end: `0x1800096b8`
- name: `__imp_load_HtCreateHandleTable`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000962d`

## import_xrefs

- `MobileNetworking!HtCreateHandleTable` at `0x1800096ac`

## pseudocode

```c
__int64 load_HtCreateHandleTable()
{
  return _tailMerge_mobilenetworking_dll();
}

```

## disassembly

```asm
0x1800096ac  lea     rax, __imp_HtCreateHandleTable
0x1800096b3  jmp     __tailMerge_mobilenetworking_dll
```
