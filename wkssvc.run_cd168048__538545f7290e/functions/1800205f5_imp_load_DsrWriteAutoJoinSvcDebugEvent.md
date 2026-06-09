# __imp_load_DsrWriteAutoJoinSvcDebugEvent

- ea: `0x1800205f5`
- end: `0x180020601`
- name: `__imp_load_DsrWriteAutoJoinSvcDebugEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020552`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x1800205f5`

## pseudocode

```c
__int64 load_DsrWriteAutoJoinSvcDebugEvent()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x1800205f5  lea     rax, __imp_DsrWriteAutoJoinSvcDebugEvent
0x1800205fc  jmp     __tailMerge_dsreg_dll
```
