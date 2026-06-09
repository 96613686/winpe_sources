# _dynamic_initializer_for__g_comObjectActivationCLicensingStateTools__

- ea: `0x180001420`
- end: `0x180001444`
- name: `_dynamic_initializer_for__g_comObjectActivationCLicensingStateTools__`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000142b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000142b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCLicensingStateTools__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_180046800 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180001420  sub     rsp, 28h
0x180001424  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCLicensingStateTools@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x18000142b  call    cs:__imp_EncodePointer
0x180001432  nop     dword ptr [rax+rax+00h]
0x180001437  mov     cs:qword_180046800, rax
0x18000143e  add     rsp, 28h
0x180001442  retn
```
