# _dynamic_initializer_for__g_comGlobalEntryObjectActivationCSLLUAComInstance__

- ea: `0x180001240`
- end: `0x18000125d`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectActivationCSLLUAComInstance__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectActivationCSLLUAComInstance__()
{
  __int64 *result; // rax

  qword_180046578 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_180046578;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_180046578;
  return result;
}

```

## disassembly

```asm
0x180001240  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001247  mov     cs:qword_180046578, rax
0x18000124e  lea     rax, qword_180046578
0x180001255  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000125c  retn
```
