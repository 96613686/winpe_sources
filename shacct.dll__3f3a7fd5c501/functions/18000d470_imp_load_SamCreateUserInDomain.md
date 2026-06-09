# __imp_load_SamCreateUserInDomain

- ea: `0x18000d470`
- end: `0x18000d47c`
- name: `__imp_load_SamCreateUserInDomain`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamCreateUserInDomain` at `0x18000d470`

## pseudocode

```c
__int64 load_SamCreateUserInDomain()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d470  lea     rax, __imp_SamCreateUserInDomain
0x18000d477  jmp     __tailMerge_samlib_dll
```
