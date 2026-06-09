# __imp_load_NetpwPathCanonicalize

- ea: `0x180021b3f`
- end: `0x180021b4b`
- name: `__imp_load_NetpwPathCanonicalize`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x180020a8c`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x180021b3f`

## pseudocode

```c
__int64 load_NetpwPathCanonicalize()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x180021b3f  lea     rax, __imp_NetpwPathCanonicalize
0x180021b46  jmp     __tailMerge_netutils_dll
```
