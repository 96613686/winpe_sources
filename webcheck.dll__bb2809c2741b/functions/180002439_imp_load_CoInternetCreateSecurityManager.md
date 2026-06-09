# __imp_load_CoInternetCreateSecurityManager

- ea: `0x180002439`
- end: `0x180002445`
- name: `__imp_load_CoInternetCreateSecurityManager`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800023ba`

## import_xrefs

- `urlmon!CoInternetCreateSecurityManager` at `0x180002439`

## pseudocode

```c
__int64 load_CoInternetCreateSecurityManager()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x180002439  lea     rax, __imp_CoInternetCreateSecurityManager
0x180002440  jmp     __tailMerge_urlmon_dll
```
