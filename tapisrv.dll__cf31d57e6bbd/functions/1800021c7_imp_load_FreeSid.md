# __imp_load_FreeSid

- ea: `0x1800021c7`
- end: `0x1800021d3`
- name: `__imp_load_FreeSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x1800021c7`

## pseudocode

```c
__int64 load_FreeSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021c7  lea     rax, __imp_FreeSid
0x1800021ce  jmp     __tailMerge_advapi32_dll
```
