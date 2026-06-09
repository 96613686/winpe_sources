# [thunk]:ATL::CComContainedObject<CXmlContentFilter>::Release`adjustor{16}' (void)

- ea: `0x180012f50`
- end: `0x180012f59`
- name: `?Release@?$CComContainedObject@VCXmlContentFilter@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012f20`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CXmlContentFilter>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CXmlContentFilter>::Release(a1 - 16);
}

```

## disassembly

```asm
0x180012f50  sub     rcx, 10h
0x180012f54  jmp     ?Release@?$CComContainedObject@VCXmlContentFilter@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CXmlContentFilter>::Release(void)
```
