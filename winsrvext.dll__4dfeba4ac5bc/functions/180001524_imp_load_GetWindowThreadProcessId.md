# __imp_load_GetWindowThreadProcessId

- ea: `0x180001524`
- end: `0x180001530`
- name: `__imp_load_GetWindowThreadProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180001524`

## pseudocode

```c
__int64 load_GetWindowThreadProcessId()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180001524  lea     rax, __imp_GetWindowThreadProcessId
0x18000152b  jmp     __tailMerge_user32_dll
```
