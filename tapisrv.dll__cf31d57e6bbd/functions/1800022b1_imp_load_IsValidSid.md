# __imp_load_IsValidSid

- ea: `0x1800022b1`
- end: `0x1800022bd`
- name: `__imp_load_IsValidSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!IsValidSid` at `0x1800022b1`

## pseudocode

```c
__int64 load_IsValidSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022b1  lea     rax, __imp_IsValidSid
0x1800022b8  jmp     __tailMerge_advapi32_dll
```
