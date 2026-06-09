# [thunk]:ATL::CComContainedObject<CXmlContentFilter>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x1800121a0`
- end: `0x1800121a9`
- name: `?QueryInterface@?$CComContainedObject@VCXmlContentFilter@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012170`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CXmlContentFilter>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CXmlContentFilter>::QueryInterface(a1 - 16);
}

```

## disassembly

```asm
0x1800121a0  sub     rcx, 10h
0x1800121a4  jmp     ?QueryInterface@?$CComContainedObject@VCXmlContentFilter@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CXmlContentFilter>::QueryInterface(_GUID const &,void * *)
```
