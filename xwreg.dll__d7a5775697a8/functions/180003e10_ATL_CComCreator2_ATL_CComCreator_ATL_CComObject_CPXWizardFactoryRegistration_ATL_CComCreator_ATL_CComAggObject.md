# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPXWizardFactoryRegistration>>,ATL::CComCreator<ATL::CComAggObject<CPXWizardFactoryRegistration>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003e10`
- end: `0x180003e1e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003e64`
- `0x1800041d0`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPXWizardFactoryRegistration>>,ATL::CComCreator<ATL::CComAggObject<CPXWizardFactoryRegistration>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CPXWizardFactoryRegistration>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CPXWizardFactoryRegistration>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180003e10  test    rcx, rcx
0x180003e13  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPXWizardFactoryRegistration>>::CreateInstance(void *,_GUID const &,void * *)
0x180003e19  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPXWizardFactoryRegistration>>::CreateInstance(void *,_GUID const &,void * *)
```
