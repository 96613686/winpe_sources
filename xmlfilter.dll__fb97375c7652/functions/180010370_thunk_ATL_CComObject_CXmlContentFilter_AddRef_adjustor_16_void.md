# [thunk]:ATL::CComObject<CXmlContentFilter>::AddRef`adjustor{16}' (void)

- ea: `0x180010370`
- end: `0x180010379`
- name: `?AddRef@?$CComObject@VCXmlContentFilter@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180010330`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CXmlContentFilter>::AddRef(__int64 a1)
{
  return ATL::CComObject<CXmlContentFilter>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180010370  sub     rcx, 10h
0x180010374  jmp     ?AddRef@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAKXZ; ATL::CComObject<CXmlContentFilter>::AddRef(void)
```
