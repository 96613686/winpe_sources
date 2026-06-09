# __imp_load_SHCreateThread

- ea: `0x18000ab3b`
- end: `0x18000ab47`
- name: `__imp_load_SHCreateThread`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000aabc`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x18000ab3b`

## pseudocode

```c
__int64 load_SHCreateThread()
{
  return _tailMerge_shlwapi_dll();
}

```

## disassembly

```asm
0x18000ab3b  lea     rax, __imp_SHCreateThread
0x18000ab42  jmp     __tailMerge_shlwapi_dll
```
