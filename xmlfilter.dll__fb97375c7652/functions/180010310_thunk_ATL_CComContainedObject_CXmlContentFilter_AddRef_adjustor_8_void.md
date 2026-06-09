# [thunk]:ATL::CComContainedObject<CXmlContentFilter>::AddRef`adjustor{8}' (void)

- ea: `0x180010310`
- end: `0x180010319`
- name: `?AddRef@?$CComContainedObject@VCXmlContentFilter@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800102f0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CXmlContentFilter>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CXmlContentFilter>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x180010310  sub     rcx, 8
0x180010314  jmp     ?AddRef@?$CComContainedObject@VCXmlContentFilter@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CXmlContentFilter>::AddRef(void)
```
