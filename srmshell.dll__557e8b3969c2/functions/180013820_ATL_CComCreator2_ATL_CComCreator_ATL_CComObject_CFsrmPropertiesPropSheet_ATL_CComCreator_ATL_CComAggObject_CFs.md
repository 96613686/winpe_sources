# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFsrmPropertiesPropSheet>>,ATL::CComCreator<ATL::CComAggObject<CFsrmPropertiesPropSheet>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180013820`
- end: `0x18001382e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001394c`
- `0x180013b68`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CFsrmPropertiesPropSheet>>,ATL::CComCreator<ATL::CComAggObject<CFsrmPropertiesPropSheet>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CFsrmPropertiesPropSheet>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CFsrmPropertiesPropSheet>>::CreateInstance();
}

```

## disassembly

```asm
0x180013820  test    rcx, rcx
0x180013823  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CFsrmPropertiesPropSheet>>::CreateInstance(void *,_GUID const &,void * *)
0x180013829  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCFsrmPropertiesPropSheet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CFsrmPropertiesPropSheet>>::CreateInstance(void *,_GUID const &,void * *)
```
