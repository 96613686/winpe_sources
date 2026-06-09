# ATL::CComObject<CPXWizardTypeRegistration>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005110`
- end: `0x180005122`
- name: `?QueryInterface@?$CComObject@VCPXWizardTypeRegistration@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003bcc`

## pseudocode

```c
int __fastcall ATL::CComObject<CPXWizardTypeRegistration>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPXWizardTypeRegistration::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180005110  mov     r9, r8; void **
0x180005113  mov     r8, rdx; struct _GUID *
0x180005116  lea     rdx, ?_entries@?1??_GetEntries@CPXWizardTypeRegistration@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000511d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
