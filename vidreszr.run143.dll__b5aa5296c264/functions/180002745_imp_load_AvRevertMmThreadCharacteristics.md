# __imp_load_AvRevertMmThreadCharacteristics

- ea: `0x180002745`
- end: `0x180002751`
- name: `__imp_load_AvRevertMmThreadCharacteristics`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800026c6`

## import_xrefs

- `AVRT!AvRevertMmThreadCharacteristics` at `0x180002745`

## pseudocode

```c
__int64 load_AvRevertMmThreadCharacteristics()
{
  return _tailMerge_avrt_dll();
}

```

## disassembly

```asm
0x180002745  lea     rax, __imp_AvRevertMmThreadCharacteristics
0x18000274c  jmp     __tailMerge_avrt_dll
```
