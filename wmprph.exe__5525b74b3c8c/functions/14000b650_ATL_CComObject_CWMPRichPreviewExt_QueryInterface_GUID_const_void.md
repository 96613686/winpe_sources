# ATL::CComObject<CWMPRichPreviewExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000b650`
- end: `0x14000b662`
- name: `?QueryInterface@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b670`
- `0x14000b680`
- `0x14000b690`

## callees

- `0x1400059b4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewExt>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWMPRichPreviewExt::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x14000b650  mov     r9, r8; void **
0x14000b653  mov     r8, rdx; struct _GUID *
0x14000b656  lea     rdx, ?_entries@?1??_GetEntries@CWMPRichPreviewExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x14000b65d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
