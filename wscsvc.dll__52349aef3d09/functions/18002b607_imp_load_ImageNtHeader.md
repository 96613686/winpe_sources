# __imp_load_ImageNtHeader

- ea: `0x18002b607`
- end: `0x18002b613`
- name: `__imp_load_ImageNtHeader`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18002b588`

## import_xrefs

- `dbghelp!ImageNtHeader` at `0x18002b607`

## pseudocode

```c
__int64 load_ImageNtHeader()
{
  return _tailMerge_dbghelp_dll();
}

```

## disassembly

```asm
0x18002b607  lea     rax, __imp_ImageNtHeader
0x18002b60e  jmp     __tailMerge_dbghelp_dll
```
