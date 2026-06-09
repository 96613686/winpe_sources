# __imp_load_DsrWriteAutoJoinSvcTriggerEvent

- ea: `0x18001ee69`
- end: `0x18001ee75`
- name: `__imp_load_DsrWriteAutoJoinSvcTriggerEvent`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001eda2`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcTriggerEvent` at `0x18001ee69`

## pseudocode

```c
__int64 load_DsrWriteAutoJoinSvcTriggerEvent()
{
  return _tailMerge_dsreg_dll();
}

```

## disassembly

```asm
0x18001ee69  lea     rax, __imp_DsrWriteAutoJoinSvcTriggerEvent
0x18001ee70  jmp     __tailMerge_dsreg_dll
```
