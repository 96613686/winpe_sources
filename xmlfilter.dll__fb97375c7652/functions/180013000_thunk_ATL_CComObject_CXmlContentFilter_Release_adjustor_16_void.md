# [thunk]:ATL::CComObject<CXmlContentFilter>::Release`adjustor{16}' (void)

- ea: `0x180013000`
- end: `0x180013009`
- name: `?Release@?$CComObject@VCXmlContentFilter@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012f60`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CXmlContentFilter>::Release(__int64 a1)
{
  return ATL::CComObject<CXmlContentFilter>::Release((volatile signed __int32 *)(a1 - 16));
}

```

## disassembly

```asm
0x180013000  sub     rcx, 10h
0x180013004  jmp     ?Release@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAKXZ; ATL::CComObject<CXmlContentFilter>::Release(void)
```
