# __imp_load_CommitTransaction

- ea: `0x18003b465`
- end: `0x18003b471`
- name: `__imp_load_CommitTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003b3c2`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x18003b465`

## pseudocode

```c
__int64 load_CommitTransaction()
{
  return _tailMerge_ktmw32_dll();
}

```

## disassembly

```asm
0x18003b465  lea     rax, __imp_CommitTransaction
0x18003b46c  jmp     __tailMerge_ktmw32_dll
```
