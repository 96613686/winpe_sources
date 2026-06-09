# __imp_load_RmAccessCheck

- ea: `0x180009621`
- end: `0x18000962d`
- name: `__imp_load_RmAccessCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800095a2`

## import_xrefs

- `RMCLIENT!RmAccessCheck` at `0x180009621`

## pseudocode

```c
__int64 load_RmAccessCheck()
{
  return _tailMerge_rmclient_dll();
}

```

## disassembly

```asm
0x180009621  lea     rax, __imp_RmAccessCheck
0x180009628  jmp     __tailMerge_rmclient_dll
```
