# __imp_load_CreateTransaction

- ea: `0x18003b453`
- end: `0x18003b45f`
- name: `__imp_load_CreateTransaction`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18003b3c2`

## import_xrefs

- `ktmw32!CreateTransaction` at `0x18003b453`

## pseudocode

```c
__int64 load_CreateTransaction()
{
  return _tailMerge_ktmw32_dll();
}

```

## disassembly

```asm
0x18003b453  lea     rax, __imp_CreateTransaction
0x18003b45a  jmp     __tailMerge_ktmw32_dll
```
