# __imp_load_InitializeSid

- ea: `0x1800021d9`
- end: `0x1800021e5`
- name: `__imp_load_InitializeSid`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!InitializeSid` at `0x1800021d9`

## pseudocode

```c
__int64 load_InitializeSid()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800021d9  lea     rax, __imp_InitializeSid
0x1800021e0  jmp     __tailMerge_advapi32_dll
```
