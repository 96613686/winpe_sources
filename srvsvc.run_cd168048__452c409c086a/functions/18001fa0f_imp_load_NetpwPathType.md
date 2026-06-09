# __imp_load_NetpwPathType

- ea: `0x18001fa0f`
- end: `0x18001fa1b`
- name: `__imp_load_NetpwPathType`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f049`

## import_xrefs

- `netutils!NetpwPathType` at `0x18001fa0f`

## pseudocode

```c
__int64 load_NetpwPathType()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x18001fa0f  lea     rax, __imp_NetpwPathType
0x18001fa16  jmp     __tailMerge_netutils_dll
```
