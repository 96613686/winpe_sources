# _dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCSLLUAComInstance__

- ea: `0x180001360`
- end: `0x18000137d`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCSLLUAComInstance__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCSLLUAComInstance__()
{
  __int64 *result; // rax

  qword_180046560 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_180046560;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_180046560;
  return result;
}

```

## disassembly

```asm
0x180001360  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001367  mov     cs:qword_180046560, rax
0x18000136e  lea     rax, qword_180046560
0x180001375  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000137c  retn
```
