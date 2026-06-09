# __imp_load_CheckTokenMembership

- ea: `0x1800021b5`
- end: `0x1800021c1`
- name: `__imp_load_CheckTokenMembership`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x1800021b5`

## pseudocode

```c
__int64 load_CheckTokenMembership()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021b5  lea     rax, __imp_CheckTokenMembership
0x1800021bc  jmp     __tailMerge_advapi32_dll
```
