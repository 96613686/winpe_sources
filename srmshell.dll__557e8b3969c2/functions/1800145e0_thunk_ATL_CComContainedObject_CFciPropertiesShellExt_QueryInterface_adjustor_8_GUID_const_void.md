# [thunk]:ATL::CComContainedObject<CFciPropertiesShellExt>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800145e0`
- end: `0x1800145e9`
- name: `?QueryInterface@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800145c0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CFciPropertiesShellExt>::QueryInterface(a1 - 8);
}

```

## disassembly

```asm
0x1800145e0  sub     rcx, 8
0x1800145e4  jmp     ?QueryInterface@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CFciPropertiesShellExt>::QueryInterface(_GUID const &,void * *)
```
