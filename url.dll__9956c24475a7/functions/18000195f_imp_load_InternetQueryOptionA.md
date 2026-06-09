# __imp_load_InternetQueryOptionA

- ea: `0x18000195f`
- end: `0x18000196b`
- name: `__imp_load_InternetQueryOptionA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800018e0`

## import_xrefs

- `WININET!InternetQueryOptionA` at `0x18000195f`

## pseudocode

```c
__int64 __fastcall load_InternetQueryOptionA(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return _tailMerge_wininet_dll(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000195f  lea     rax, __imp_InternetQueryOptionA
0x180001966  jmp     __tailMerge_wininet_dll
```
