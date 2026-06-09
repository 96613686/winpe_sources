# [thunk]:ATL::CComObject<CXmlContentFilter>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800121d0`
- end: `0x1800121d9`
- name: `?QueryInterface@?$CComObject@VCXmlContentFilter@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800121b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CXmlContentFilter>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CXmlContentFilter>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x1800121d0  sub     rcx, 8
0x1800121d4  jmp     ?QueryInterface@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CXmlContentFilter>::QueryInterface(_GUID const &,void * *)
```
