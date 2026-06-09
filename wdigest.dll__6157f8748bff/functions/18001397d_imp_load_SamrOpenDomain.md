# __imp_load_SamrOpenDomain

- ea: `0x18001397d`
- end: `0x180013989`
- name: `__imp_load_SamrOpenDomain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180013892`

## import_xrefs

- `SAMSRV!SamrOpenDomain` at `0x18001397d`

## pseudocode

```c
__int64 load_SamrOpenDomain()
{
  return _tailMerge_samsrv_dll();
}

```

## disassembly

```asm
0x18001397d  lea     rax, __imp_SamrOpenDomain
0x180013984  jmp     __tailMerge_samsrv_dll
```
