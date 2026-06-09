# _dynamic_initializer_for__g_comObjectActivationCSLLUAComInstance__

- ea: `0x1800014b0`
- end: `0x1800014d4`
- name: `_dynamic_initializer_for__g_comObjectActivationCSLLUAComInstance__`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800014bb`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800014bb`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCSLLUAComInstance__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_180046880 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x1800014b0  sub     rsp, 28h
0x1800014b4  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCSLLUAComInstance@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x1800014bb  call    cs:__imp_EncodePointer
0x1800014c2  nop     dword ptr [rax+rax+00h]
0x1800014c7  mov     cs:qword_180046880, rax
0x1800014ce  add     rsp, 28h
0x1800014d2  retn
```
