# __imp_load_DsrWriteAutoJoinSvcAdminEvent

- ea: `0x180020607`
- end: `0x180020613`
- name: `__imp_load_DsrWriteAutoJoinSvcAdminEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020552`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcAdminEvent` at `0x180020607`

## pseudocode

```c
__int64 load_DsrWriteAutoJoinSvcAdminEvent()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x180020607  lea     rax, __imp_DsrWriteAutoJoinSvcAdminEvent
0x18002060e  jmp     __tailMerge_dsreg_dll
```
