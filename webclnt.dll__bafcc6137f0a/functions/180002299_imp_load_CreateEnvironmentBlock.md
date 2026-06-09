# __imp_load_CreateEnvironmentBlock

- ea: `0x180002299`
- end: `0x1800022a5`
- name: `__imp_load_CreateEnvironmentBlock`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002208`

## import_xrefs

- `USERENV!CreateEnvironmentBlock` at `0x180002299`

## pseudocode

```c
__int64 load_CreateEnvironmentBlock()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180002299  lea     rax, __imp_CreateEnvironmentBlock
0x1800022a0  jmp     __tailMerge_userenv_dll
```
