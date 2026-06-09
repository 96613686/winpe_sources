# __imp_load_StgCreateDocfileOnILockBytes

- ea: `0x180009737`
- end: `0x180009743`
- name: `__imp_load_StgCreateDocfileOnILockBytes`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009670`

## import_xrefs

- `ole32!StgCreateDocfileOnILockBytes` at `0x180009737`

## pseudocode

```c
__int64 load_StgCreateDocfileOnILockBytes()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180009737  lea     rax, __imp_StgCreateDocfileOnILockBytes
0x18000973e  jmp     __tailMerge_ole32_dll
```
