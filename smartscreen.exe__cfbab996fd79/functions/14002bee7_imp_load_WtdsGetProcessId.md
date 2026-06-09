# __imp_load_WtdsGetProcessId

- ea: `0x14002bee7`
- end: `0x14002bef3`
- name: `__imp_load_WtdsGetProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14002be20`

## import_xrefs

- `WTDSENSOR!WtdsGetProcessId` at `0x14002bee7`

## pseudocode

```c
__int64 load_WtdsGetProcessId()
{
  return _tailMerge_wtdsensor_dll();
}

```

## disassembly

```asm
0x14002bee7  lea     rax, __imp_WtdsGetProcessId
0x14002beee  jmp     __tailMerge_wtdsensor_dll
```
