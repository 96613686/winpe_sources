# __imp_load_CheckTokenMembership

- ea: `0x18000232e`
- end: `0x18000233a`
- name: `__imp_load_CheckTokenMembership`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000221f`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x18000232e`

## pseudocode

```c
__int64 load_CheckTokenMembership()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000232e  lea     rax, __imp_CheckTokenMembership
0x180002335  jmp     __tailMerge_advapi32_dll
```
