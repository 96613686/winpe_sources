# __imp_load_SamDeleteUser

- ea: `0x18000d4ca`
- end: `0x18000d4d6`
- name: `__imp_load_SamDeleteUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamDeleteUser` at `0x18000d4ca`

## pseudocode

```c
__int64 load_SamDeleteUser()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d4ca  lea     rax, __imp_SamDeleteUser
0x18000d4d1  jmp     __tailMerge_samlib_dll
```
