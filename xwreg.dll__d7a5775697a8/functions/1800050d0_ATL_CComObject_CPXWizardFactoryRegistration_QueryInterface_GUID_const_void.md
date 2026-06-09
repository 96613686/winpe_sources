# ATL::CComObject<CPXWizardFactoryRegistration>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800050d0`
- end: `0x1800050e2`
- name: `?QueryInterface@?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003bcc`

## pseudocode

```c
int __fastcall ATL::CComObject<CPXWizardFactoryRegistration>::QueryInterface(
        void *a1,
        const struct _GUID *a2,
        void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPXWizardFactoryRegistration::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800050d0  mov     r9, r8; void **
0x1800050d3  mov     r8, rdx; struct _GUID *
0x1800050d6  lea     rdx, ?_entries@?1??_GetEntries@CPXWizardFactoryRegistration@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800050dd  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
