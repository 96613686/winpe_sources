# __imp_load_DsrWriteAutoJoinSvcAdminEvent

- ea: `0x18001ee57`
- end: `0x18001ee63`
- name: `__imp_load_DsrWriteAutoJoinSvcAdminEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001eda2`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x18001ee57`

## pseudocode

```c
__int64 load_DsrWriteAutoJoinSvcAdminEvent()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x18001ee57  lea     rax, __imp_DsrWriteAutoJoinSvcAdminEvent
0x18001ee5e  jmp     __tailMerge_dsreg_dll
```
