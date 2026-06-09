# __imp_load_SamRidToSid

- ea: `0x18000d44c`
- end: `0x18000d458`
- name: `__imp_load_SamRidToSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000d1c8`

## import_xrefs

- `SAMLIB!SamRidToSid` at `0x18000d44c`

## pseudocode

```c
__int64 load_SamRidToSid()
{
  return _tailMerge_samlib_dll();
}

```

## disassembly

```asm
0x18000d44c  lea     rax, __imp_SamRidToSid
0x18000d453  jmp     __tailMerge_samlib_dll
```
