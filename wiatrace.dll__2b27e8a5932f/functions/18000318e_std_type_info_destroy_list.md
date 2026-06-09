# __std_type_info_destroy_list

- ea: `0x18000318e`
- end: `0x180003194`
- name: `__std_type_info_destroy_list`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_type_info_destroy_list` at `0x18000318e`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _std_type_info_destroy_list(__int64 a1)
{
  return __std_type_info_destroy_list(a1);
}

```

## disassembly

```asm
0x18000318e  jmp     cs:__imp___std_type_info_destroy_list
```
