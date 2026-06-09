# _dynamic_initializer_for__g_comObjectActivationCOfflineActivation__

- ea: `0x180001450`
- end: `0x180001474`
- name: `_dynamic_initializer_for__g_comObjectActivationCOfflineActivation__`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000145b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000145b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCOfflineActivation__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_180046820 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180001450  sub     rsp, 28h
0x180001454  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCOfflineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x18000145b  call    cs:__imp_EncodePointer
0x180001462  nop     dword ptr [rax+rax+00h]
0x180001467  mov     cs:qword_180046820, rax
0x18000146e  add     rsp, 28h
0x180001472  retn
```
