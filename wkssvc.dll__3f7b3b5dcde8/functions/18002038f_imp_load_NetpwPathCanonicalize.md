# __imp_load_NetpwPathCanonicalize

- ea: `0x18002038f`
- end: `0x18002039b`
- name: `__imp_load_NetpwPathCanonicalize`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callees

- `0x18001f2dc`

## import_xrefs

- `netutils!NetpwPathCanonicalize` at `0x18002038f`

## pseudocode

```c
__int64 load_NetpwPathCanonicalize()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x18002038f  lea     rax, __imp_NetpwPathCanonicalize
0x180020396  jmp     __tailMerge_netutils_dll
```
