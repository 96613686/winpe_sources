# __imp_load_WTSQueryUserToken

- ea: `0x1800092fd`
- end: `0x180009309`
- name: `__imp_load_WTSQueryUserToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000927e`

## import_xrefs

- `WTSAPI32!WTSQueryUserToken` at `0x1800092fd`

## pseudocode

```c
__int64 load_WTSQueryUserToken()
{
  return _tailMerge_wtsapi32_dll();
}

```

## disassembly

```asm
0x1800092fd  lea     rax, __imp_WTSQueryUserToken
0x180009304  jmp     __tailMerge_wtsapi32_dll
```
