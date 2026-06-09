# _dynamic_initializer_for__g_comObjectActivationCOnlineActivation__

- ea: `0x180001480`
- end: `0x1800014a4`
- name: `_dynamic_initializer_for__g_comObjectActivationCOnlineActivation__`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000148b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000148b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCOnlineActivation__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_180046840 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180001480  sub     rsp, 28h
0x180001484  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCOnlineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x18000148b  call    cs:__imp_EncodePointer
0x180001492  nop     dword ptr [rax+rax+00h]
0x180001497  mov     cs:qword_180046840, rax
0x18000149e  add     rsp, 28h
0x1800014a2  retn
```
