# __imp_load_RollbackTransaction

- ea: `0x18003b441`
- end: `0x18003b44d`
- name: `__imp_load_RollbackTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x18003b3c2`

## import_xrefs

- `ktmw32!RollbackTransaction` at `0x18003b441`

## pseudocode

```c
__int64 load_RollbackTransaction()
{
  return _tailMerge_ktmw32_dll();
}

```

## disassembly

```asm
0x18003b441  lea     rax, __imp_RollbackTransaction
0x18003b448  jmp     __tailMerge_ktmw32_dll
```
