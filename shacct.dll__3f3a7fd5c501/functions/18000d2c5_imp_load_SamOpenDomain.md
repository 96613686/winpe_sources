# __imp_load_SamOpenDomain

- ea: `0x18000d2c5`
- end: `0x18000d2d1`
- name: `__imp_load_SamOpenDomain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamOpenDomain` at `0x18000d2c5`

## pseudocode

```c
__int64 load_SamOpenDomain()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d2c5  lea     rax, __imp_SamOpenDomain
0x18000d2cc  jmp     __tailMerge_samlib_dll
```
