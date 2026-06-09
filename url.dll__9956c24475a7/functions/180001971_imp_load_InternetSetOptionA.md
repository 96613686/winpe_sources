# __imp_load_InternetSetOptionA

- ea: `0x180001971`
- end: `0x18000197d`
- name: `__imp_load_InternetSetOptionA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018e0`

## import_xrefs

- `WININET!InternetSetOptionA` at `0x180001971`

## pseudocode

```c
__int64 __fastcall load_InternetSetOptionA(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_wininet_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001971  lea     rax, __imp_InternetSetOptionA
0x180001978  jmp     __tailMerge_wininet_dll
```
