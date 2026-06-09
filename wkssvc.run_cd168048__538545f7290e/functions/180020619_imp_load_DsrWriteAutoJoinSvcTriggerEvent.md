# __imp_load_DsrWriteAutoJoinSvcTriggerEvent

- ea: `0x180020619`
- end: `0x180020625`
- name: `__imp_load_DsrWriteAutoJoinSvcTriggerEvent`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180020552`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcTriggerEvent` at `0x180020619`

## pseudocode

```c
__int64 load_DsrWriteAutoJoinSvcTriggerEvent()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x180020619  lea     rax, __imp_DsrWriteAutoJoinSvcTriggerEvent
0x180020620  jmp     __tailMerge_dsreg_dll
```
