# __imp_load_WtdsGetProcessId

- ea: `0x14002ad27`
- end: `0x14002ad33`
- name: `__imp_load_WtdsGetProcessId`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14002ac60`

## import_xrefs

- `WTDSENSOR!WtdsGetProcessId` at `0x14002ad27`

## pseudocode

```c
__int64 load_WtdsGetProcessId()
{
  return _tailMerge_wtdsensor_dll();
}

```

## disassembly

```asm
0x14002ad27  lea     rax, __imp_WtdsGetProcessId
0x14002ad2e  jmp     __tailMerge_wtdsensor_dll
```
