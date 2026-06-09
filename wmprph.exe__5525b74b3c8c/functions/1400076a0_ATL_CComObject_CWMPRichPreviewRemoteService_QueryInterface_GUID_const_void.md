# ATL::CComObject<CWMPRichPreviewRemoteService>::QueryInterface(_GUID const &,void * *)

- ea: `0x1400076a0`
- end: `0x1400076b2`
- name: `?QueryInterface@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400076c0`
- `0x1400076d0`

## callees

- `0x1400059b4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWMPRichPreviewRemoteService::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1400076a0  mov     r9, r8; void **
0x1400076a3  mov     r8, rdx; struct _GUID *
0x1400076a6  lea     rdx, ?_entries@?1??_GetEntries@CWMPRichPreviewRemoteService@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1400076ad  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
