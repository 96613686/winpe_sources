# __imp_load_GetTokenInformation

- ea: `0x180002125`
- end: `0x180002131`
- name: `__imp_load_GetTokenInformation`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x180002125`

## pseudocode

```c
__int64 load_GetTokenInformation()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002125  lea     rax, __imp_GetTokenInformation
0x18000212c  jmp     __tailMerge_advapi32_dll
```
