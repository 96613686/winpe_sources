# __imp_load_CreateUri

- ea: `0x180020fcc`
- end: `0x180020fd8`
- name: `__imp_load_CreateUri`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180020f3b`

## import_xrefs

- `urlmon!CreateUri` at `0x180020fcc`

## pseudocode

```c
__int64 load_CreateUri()
{
  return _tailMerge_urlmon_dll();
}

```

## disassembly

```asm
0x180020fcc  lea     rax, __imp_CreateUri
0x180020fd3  jmp     __tailMerge_urlmon_dll
```
