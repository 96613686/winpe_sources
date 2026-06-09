# _dynamic_initializer_for__g_comGlobalEntryObjectActivationCOfflineActivation__

- ea: `0x1800011e0`
- end: `0x1800011fd`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectActivationCOfflineActivation__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectActivationCOfflineActivation__()
{
  __int64 *result; // rax

  qword_1800463F8 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_1800463F8;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_1800463F8;
  return result;
}

```

## disassembly

```asm
0x1800011e0  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800011e7  mov     cs:qword_1800463F8, rax
0x1800011ee  lea     rax, qword_1800463F8
0x1800011f5  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800011fc  retn
```
