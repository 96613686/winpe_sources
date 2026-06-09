# _dynamic_initializer_for__g_comObjectActivationCElevationConfig__

- ea: `0x1800013f0`
- end: `0x180001414`
- name: `_dynamic_initializer_for__g_comObjectActivationCElevationConfig__`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800013fb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800013fb`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCElevationConfig__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_1800467E0 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x1800013f0  sub     rsp, 28h
0x1800013f4  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCElevationConfig@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x1800013fb  call    cs:__imp_EncodePointer
0x180001402  nop     dword ptr [rax+rax+00h]
0x180001407  mov     cs:qword_1800467E0, rax
0x18000140e  add     rsp, 28h
0x180001412  retn
```
