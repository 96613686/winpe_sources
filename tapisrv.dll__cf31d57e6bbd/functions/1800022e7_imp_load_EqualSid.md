# __imp_load_EqualSid

- ea: `0x1800022e7`
- end: `0x1800022f3`
- name: `__imp_load_EqualSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x1800022e7`

## pseudocode

```c
__int64 load_EqualSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800022e7  lea     rax, __imp_EqualSid
0x1800022ee  jmp     __tailMerge_advapi32_dll
```
