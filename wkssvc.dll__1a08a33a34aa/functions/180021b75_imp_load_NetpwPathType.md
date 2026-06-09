# __imp_load_NetpwPathType

- ea: `0x180021b75`
- end: `0x180021b81`
- name: `__imp_load_NetpwPathType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020a8c`

## import_xrefs

- `netutils!NetpwPathType` at `0x180021b75`

## pseudocode

```c
__int64 load_NetpwPathType()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x180021b75  lea     rax, __imp_NetpwPathType
0x180021b7c  jmp     __tailMerge_netutils_dll
```
