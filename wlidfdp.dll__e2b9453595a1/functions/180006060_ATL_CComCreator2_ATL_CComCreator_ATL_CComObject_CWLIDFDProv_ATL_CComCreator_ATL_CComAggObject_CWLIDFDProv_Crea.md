# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWLIDFDProv>>,ATL::CComCreator<ATL::CComAggObject<CWLIDFDProv>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006060`
- end: `0x18000606e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCWLIDFDProv@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCWLIDFDProv@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006074`
- `0x18000618c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWLIDFDProv>>,ATL::CComCreator<ATL::CComAggObject<CWLIDFDProv>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CWLIDFDProv>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CWLIDFDProv>>::CreateInstance();
}

```

## disassembly

```asm
0x180006060  test    rcx, rcx
0x180006063  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCWLIDFDProv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CWLIDFDProv>>::CreateInstance(void *,_GUID const &,void * *)
0x180006069  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCWLIDFDProv@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CWLIDFDProv>>::CreateInstance(void *,_GUID const &,void * *)
```
