# [thunk]:ATL::CComObject<CXmlContentFilter>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x1800121e0`
- end: `0x1800121e9`
- name: `?QueryInterface@?$CComObject@VCXmlContentFilter@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CXmlContentFilter>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x1800121e0  sub     rcx, 10h
0x1800121e4  jmp     ?QueryInterface@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CXmlContentFilter>::QueryInterface(_GUID const &,void * *)
```
