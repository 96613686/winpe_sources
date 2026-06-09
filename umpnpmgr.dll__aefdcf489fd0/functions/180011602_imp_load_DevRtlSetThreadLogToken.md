# __imp_load_DevRtlSetThreadLogToken

- ea: `0x180011602`
- end: `0x18001160e`
- name: `__imp_load_DevRtlSetThreadLogToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011571`

## import_xrefs

- `DEVRTL!DevRtlSetThreadLogToken` at `0x180011602`

## pseudocode

```c
__int64 load_DevRtlSetThreadLogToken()
{
  return _tailMerge_devrtl_dll();
}

```

## disassembly

```asm
0x180011602  lea     rax, __imp_DevRtlSetThreadLogToken
0x180011609  jmp     __tailMerge_devrtl_dll
```
