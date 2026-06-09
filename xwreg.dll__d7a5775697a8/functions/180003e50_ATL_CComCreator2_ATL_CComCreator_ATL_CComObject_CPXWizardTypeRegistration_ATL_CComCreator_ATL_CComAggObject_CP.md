# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPXWizardTypeRegistration>>,ATL::CComCreator<ATL::CComAggObject<CPXWizardTypeRegistration>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003e50`
- end: `0x180003e5e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPXWizardTypeRegistration@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800040ac`
- `0x1800043e8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPXWizardTypeRegistration>>,ATL::CComCreator<ATL::CComAggObject<CPXWizardTypeRegistration>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CPXWizardTypeRegistration>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CPXWizardTypeRegistration>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180003e50  test    rcx, rcx
0x180003e53  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPXWizardTypeRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPXWizardTypeRegistration>>::CreateInstance(void *,_GUID const &,void * *)
0x180003e59  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPXWizardTypeRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPXWizardTypeRegistration>>::CreateInstance(void *,_GUID const &,void * *)
```
