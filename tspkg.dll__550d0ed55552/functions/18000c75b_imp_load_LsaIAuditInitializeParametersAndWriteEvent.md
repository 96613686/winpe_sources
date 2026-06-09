# __imp_load_LsaIAuditInitializeParametersAndWriteEvent

- ea: `0x18000c75b`
- end: `0x18000c767`
- name: `__imp_load_LsaIAuditInitializeParametersAndWriteEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c65e`

## import_xrefs

- `LSASRV!LsaIAuditInitializeParametersAndWriteEvent` at `0x18000c75b`

## pseudocode

```c
__int64 load_LsaIAuditInitializeParametersAndWriteEvent()
{
  return _tailMerge_lsasrv_dll();
}

```

## disassembly

```asm
0x18000c75b  lea     rax, __imp_LsaIAuditInitializeParametersAndWriteEvent
0x18000c762  jmp     __tailMerge_lsasrv_dll
```
