# [thunk]:ATL::CComContainedObject<CWdsSimpleDeviceController>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180004020`
- end: `0x180004029`
- name: `?QueryInterface@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004000`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWdsSimpleDeviceController>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CWdsSimpleDeviceController>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x180004020  sub     rcx, 8
0x180004024  jmp     ?QueryInterface@?$CComContainedObject@VCWdsSimpleDeviceController@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CWdsSimpleDeviceController>::QueryInterface(_GUID const &,void * *)
```
