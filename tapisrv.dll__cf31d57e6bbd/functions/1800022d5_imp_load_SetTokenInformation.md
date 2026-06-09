# __imp_load_SetTokenInformation

- ea: `0x1800022d5`
- end: `0x1800022e1`
- name: `__imp_load_SetTokenInformation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!SetTokenInformation` at `0x1800022d5`

## pseudocode

```c
__int64 load_SetTokenInformation()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022d5  lea     rax, __imp_SetTokenInformation
0x1800022dc  jmp     __tailMerge_advapi32_dll
```
