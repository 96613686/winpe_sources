# __imp_load_CreateURLMonikerEx

- ea: `0x180002481`
- end: `0x18000248d`
- name: `__imp_load_CreateURLMonikerEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800023ba`

## import_xrefs

- `urlmon!CreateURLMonikerEx` at `0x180002481`

## pseudocode

```c
__int64 load_CreateURLMonikerEx()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x180002481  lea     rax, __imp_CreateURLMonikerEx
0x180002488  jmp     __tailMerge_urlmon_dll
```
