# __imp_load_CreateEnvironmentBlock

- ea: `0x180003db5`
- end: `0x180003dc1`
- name: `__imp_load_CreateEnvironmentBlock`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003c51`

## import_xrefs

- `USERENV!CreateEnvironmentBlock` at `0x180003db5`

## pseudocode

```c
__int64 load_CreateEnvironmentBlock()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180003db5  lea     rax, __imp_CreateEnvironmentBlock
0x180003dbc  jmp     __tailMerge_userenv_dll
```
