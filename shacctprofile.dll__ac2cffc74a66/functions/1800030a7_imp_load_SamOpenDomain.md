# __imp_load_SamOpenDomain

- ea: `0x1800030a7`
- end: `0x1800030b3`
- name: `__imp_load_SamOpenDomain`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ff2`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x1800030a7`

## pseudocode

```c
__int64 load_SamOpenDomain()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x1800030a7  lea     rax, __imp_SamOpenDomain
0x1800030ae  jmp     __tailMerge_samlib_dll
```
