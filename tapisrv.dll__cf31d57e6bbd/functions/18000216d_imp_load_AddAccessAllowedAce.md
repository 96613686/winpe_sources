# __imp_load_AddAccessAllowedAce

- ea: `0x18000216d`
- end: `0x180002179`
- name: `__imp_load_AddAccessAllowedAce`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!AddAccessAllowedAce` at `0x18000216d`

## pseudocode

```c
__int64 load_AddAccessAllowedAce()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000216d  lea     rax, __imp_AddAccessAllowedAce
0x180002174  jmp     __tailMerge_advapi32_dll
```
