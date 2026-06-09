# __imp_load_InternetCreateUrlW

- ea: `0x180009883`
- end: `0x18000988f`
- name: `__imp_load_InternetCreateUrlW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800097e0`

## import_xrefs

- `WININET!InternetCreateUrlW` at `0x180009883`

## pseudocode

```c
__int64 load_InternetCreateUrlW()
{
  return _tailMerge_wininet_dll();
}

```

## disassembly

```asm
0x180009883  lea     rax, __imp_InternetCreateUrlW
0x18000988a  jmp     __tailMerge_wininet_dll
```
