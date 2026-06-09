# _dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCElevationConfig__

- ea: `0x1800012a0`
- end: `0x1800012bd`
- name: `_dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCElevationConfig__`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 *dynamic_initializer_for__g_comGlobalEntryObjectRegistrationCElevationConfig__()
{
  __int64 *result; // rax

  qword_1800462E0 = CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst;
  result = &qword_1800462E0;
  CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst = (__int64)&qword_1800462E0;
  return result;
}

```

## disassembly

```asm
0x1800012a0  mov     rax, cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800012a7  mov     cs:qword_1800462E0, rax
0x1800012ae  lea     rax, qword_1800462E0
0x1800012b5  mov     cs:?g_pFirst@?$CGlobalList@V?$CComGlobalEntryT@VCEmptyType@@@@@@2PEAV?$CComGlobalEntryT@VCEmptyType@@@@EA, rax; CComGlobalEntryT<CEmptyType> * CGlobalList<CComGlobalEntryT<CEmptyType>>::g_pFirst
0x1800012bc  retn
```
