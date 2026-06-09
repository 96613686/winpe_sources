# _dynamic_initializer_for__g_comObjectActivationCTokenActivation__

- ea: `0x1800014e0`
- end: `0x180001504`
- name: `_dynamic_initializer_for__g_comObjectActivationCTokenActivation__`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800014eb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800014eb`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCTokenActivation__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_180046860 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x1800014e0  sub     rsp, 28h
0x1800014e4  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCTokenActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x1800014eb  call    cs:__imp_EncodePointer
0x1800014f2  nop     dword ptr [rax+rax+00h]
0x1800014f7  mov     cs:qword_180046860, rax
0x1800014fe  add     rsp, 28h
0x180001502  retn
```
