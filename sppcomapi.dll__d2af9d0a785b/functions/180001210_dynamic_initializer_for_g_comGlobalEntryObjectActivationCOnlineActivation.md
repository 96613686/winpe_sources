# _dynamic_initializer_for__g_comGlobalEntryObjectActivationCOnlineActivation__

- ea: `0x180001210`
- end: `0x18000122d`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectActivationCOnlineActivation__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectActivationCOnlineActivation__()
{
  __int64 *result; // rax

  qword_180046478 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_180046478;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_180046478;
  return result;
}

```

## disassembly

```asm
0x180001210  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001217  mov     cs:qword_180046478, rax
0x18000121e  lea     rax, qword_180046478
0x180001225  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x18000122c  retn
```
