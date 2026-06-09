# __imp_load_InternetAutodialCallback

- ea: `0x180001983`
- end: `0x18000198f`
- name: `__imp_load_InternetAutodialCallback`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018e0`

## import_xrefs

- `WININET!InternetAutodialCallback` at `0x180001983`

## pseudocode

```c
__int64 __fastcall load_InternetAutodialCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_wininet_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001983  lea     rax, __imp_InternetAutodialCallback
0x18000198a  jmp     __tailMerge_wininet_dll
```
