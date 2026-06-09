# __imp_load_DevRtlWriteTextLog

- ea: `0x1800115f0`
- end: `0x1800115fc`
- name: `__imp_load_DevRtlWriteTextLog`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011571`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x1800115f0`

## pseudocode

```c
__int64 load_DevRtlWriteTextLog()
{
  return _tailMerge_devrtl_dll();
}

```

## disassembly

```asm
0x1800115f0  lea     rax, __imp_DevRtlWriteTextLog
0x1800115f7  jmp     __tailMerge_devrtl_dll
```
