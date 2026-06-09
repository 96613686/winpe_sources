# __imp_load_CreateILockBytesOnHGlobal

- ea: `0x180009725`
- end: `0x180009731`
- name: `__imp_load_CreateILockBytesOnHGlobal`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009670`

## import_xrefs

- `ole32!CreateILockBytesOnHGlobal` at `0x180009725`

## pseudocode

```c
__int64 load_CreateILockBytesOnHGlobal()
{
  return _tailMerge_ole32_dll();
}

```

## disassembly

```asm
0x180009725  lea     rax, __imp_CreateILockBytesOnHGlobal
0x18000972c  jmp     __tailMerge_ole32_dll
```
