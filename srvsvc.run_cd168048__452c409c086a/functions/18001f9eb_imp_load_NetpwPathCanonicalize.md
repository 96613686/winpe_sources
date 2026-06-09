# __imp_load_NetpwPathCanonicalize

- ea: `0x18001f9eb`
- end: `0x18001f9f7`
- name: `__imp_load_NetpwPathCanonicalize`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x18001f049`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x18001f9eb`

## pseudocode

```c
__int64 load_NetpwPathCanonicalize()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x18001f9eb  lea     rax, __imp_NetpwPathCanonicalize
0x18001f9f2  jmp     __tailMerge_netutils_dll
```
