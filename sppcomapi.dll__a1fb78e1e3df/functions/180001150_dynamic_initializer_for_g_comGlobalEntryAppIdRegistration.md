# _dynamic_initializer_for__g_comGlobalEntryAppIdRegistration__

- ea: `0x180001150`
- end: `0x18000116d`
- name: `_dynamic_initializer_for__g_comGlobalEntryAppIdRegistration__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryAppIdRegistration__()
{
  __int64 *result; // rax

  qword_180046278 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_180046278;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_180046278;
  return result;
}

```

## disassembly

```asm
0x180001150  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001157  mov     cs:qword_180046278, rax
0x18000115e  lea     rax, qword_180046278
0x180001165  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000116c  retn
```
