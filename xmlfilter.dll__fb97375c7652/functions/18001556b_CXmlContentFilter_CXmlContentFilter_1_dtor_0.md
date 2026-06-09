# _CXmlContentFilter::CXmlContentFilter_::_1_::dtor$0

- ea: `0x18001556b`
- end: `0x18001557b`
- name: `_CXmlContentFilter::CXmlContentFilter_::_1_::dtor$0`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000fc4c`

## pseudocode

```c
void __fastcall CXmlContentFilter::CXmlContentFilter_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(*(_QWORD *)(a2 + 64) + 24LL);
}

```

## disassembly

```asm
0x18001556b  mov     rcx, [rdx+40h]
0x180015572  add     rcx, 18h
0x180015576  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
