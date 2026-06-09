# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPXWizardRegistration>>,ATL::CComCreator<ATL::CComAggObject<CPXWizardRegistration>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003e30`
- end: `0x180003e3e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPXWizardRegistration@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPXWizardRegistration@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003f88`
- `0x1800042dc`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPXWizardRegistration>>,ATL::CComCreator<ATL::CComAggObject<CPXWizardRegistration>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CPXWizardRegistration>>::CreateInstance(a1, a2, a3);
  else
    return ATL::CComCreator<ATL::CComObject<CPXWizardRegistration>>::CreateInstance(0, a2, a3);
}

```

## disassembly

```asm
0x180003e30  test    rcx, rcx
0x180003e33  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPXWizardRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPXWizardRegistration>>::CreateInstance(void *,_GUID const &,void * *)
0x180003e39  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPXWizardRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPXWizardRegistration>>::CreateInstance(void *,_GUID const &,void * *)
```
