# _dynamic_initializer_for__g_comGlobalEntryObjectActivationCTokenActivation__

- ea: `0x180001270`
- end: `0x18000128d`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectActivationCTokenActivation__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectActivationCTokenActivation__()
{
  __int64 *result; // rax

  qword_1800464F8 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_1800464F8;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_1800464F8;
  return result;
}

```

## disassembly

```asm
0x180001270  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001277  mov     cs:qword_1800464F8, rax
0x18000127e  lea     rax, qword_1800464F8
0x180001285  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000128c  retn
```
