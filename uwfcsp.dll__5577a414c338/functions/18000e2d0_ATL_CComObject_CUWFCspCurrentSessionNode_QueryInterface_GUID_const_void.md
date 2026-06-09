# ATL::CComObject<CUWFCspCurrentSessionNode>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000e2d0`
- end: `0x18000e2e2`
- name: `?QueryInterface@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e2f0`

## callees

- `0x18000951c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspCurrentSessionNode>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CUWFCspCurrentSessionNode::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000e2d0  mov     r9, r8; void **
0x18000e2d3  mov     r8, rdx; struct _GUID *
0x18000e2d6  lea     rdx, ?_entries@?1??_GetEntries@CUWFCspCurrentSessionNode@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000e2dd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
