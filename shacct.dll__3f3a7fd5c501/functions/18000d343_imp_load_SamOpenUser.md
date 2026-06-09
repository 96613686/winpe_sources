# __imp_load_SamOpenUser

- ea: `0x18000d343`
- end: `0x18000d34f`
- name: `__imp_load_SamOpenUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamOpenUser` at `0x18000d343`

## pseudocode

```c
__int64 load_SamOpenUser()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d343  lea     rax, __imp_SamOpenUser
0x18000d34a  jmp     __tailMerge_samlib_dll
```
