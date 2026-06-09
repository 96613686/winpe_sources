# _dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCTokenActivation__

- ea: `0x180001390`
- end: `0x1800013ad`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCTokenActivation__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCTokenActivation__()
{
  __int64 *result; // rax

  qword_1800464E0 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_1800464E0;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_1800464E0;
  return result;
}

```

## disassembly

```asm
0x180001390  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x180001397  mov     cs:qword_1800464E0, rax
0x18000139e  lea     rax, qword_1800464E0
0x1800013a5  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800013ac  retn
```
