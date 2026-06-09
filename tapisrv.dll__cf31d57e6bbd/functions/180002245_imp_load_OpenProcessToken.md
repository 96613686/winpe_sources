# __imp_load_OpenProcessToken

- ea: `0x180002245`
- end: `0x180002251`
- name: `__imp_load_OpenProcessToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800020a6`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180002245`

## pseudocode

```c
__int64 load_OpenProcessToken()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002245  lea     rax, __imp_OpenProcessToken
0x18000224c  jmp     __tailMerge_advapi32_dll
```
