# __imp_load_NetpwPathType

- ea: `0x1800203c5`
- end: `0x1800203d1`
- name: `__imp_load_NetpwPathType`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001f2dc`

## import_xrefs

- `netutils!NetpwPathType` at `0x1800203c5`

## pseudocode

```c
__int64 load_NetpwPathType()
{
  return _tailMerge_netutils_dll();
}

```

## disassembly

```asm
0x1800203c5  lea     rax, __imp_NetpwPathType
0x1800203cc  jmp     __tailMerge_netutils_dll
```
