# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CXmlContentFilter>>,ATL::CComCreator<ATL::CComAggObject<CXmlContentFilter>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180011560`
- end: `0x18001156e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCXmlContentFilter@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCXmlContentFilter@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011574`
- `0x1800116b0`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CXmlContentFilter>>,ATL::CComCreator<ATL::CComAggObject<CXmlContentFilter>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CXmlContentFilter>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CXmlContentFilter>>::CreateInstance();
}

```

## disassembly

```asm
0x180011560  test    rcx, rcx
0x180011563  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCXmlContentFilter@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CXmlContentFilter>>::CreateInstance(void *,_GUID const &,void * *)
0x180011569  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCXmlContentFilter@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CXmlContentFilter>>::CreateInstance(void *,_GUID const &,void * *)
```
