# ATL::CComObject<CTDCCtl>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011450`
- end: `0x180011469`
- name: `?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `25`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011470`
- `0x180011480`
- `0x180011490`
- `0x1800114a0`
- `0x1800114b0`
- `0x1800114c0`
- `0x1800114d0`
- `0x1800114e0`
- `0x1800114f0`

## callees

- `0x1800070ac`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTDCCtl>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           (char *)(a1 - 176),
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CTDCCtl::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180011450  mov     r9, r8; void **
0x180011453  add     rcx, 0FFFFFFFFFFFFFF50h; void *
0x18001145a  mov     r8, rdx; struct _GUID *
0x18001145d  lea     rdx, ?_entries@?1??_GetEntries@CTDCCtl@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180011464  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
