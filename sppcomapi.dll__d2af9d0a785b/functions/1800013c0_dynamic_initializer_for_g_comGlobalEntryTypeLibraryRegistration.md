# _dynamic_initializer_for__g_comGlobalEntryTypeLibraryRegistration__

- ea: `0x1800013c0`
- end: `0x1800013dd`
- name: `_dynamic_initializer_for__g_comGlobalEntryTypeLibraryRegistration__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryTypeLibraryRegistration__()
{
  __int64 *result; // rax

  qword_180046260 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_180046260;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_180046260;
  return result;
}

```

## disassembly

```asm
0x1800013c0  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800013c7  mov     cs:qword_180046260, rax
0x1800013ce  lea     rax, qword_180046260
0x1800013d5  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800013dc  retn
```
