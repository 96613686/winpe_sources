# ATL::CComObject<CPreflistFolder>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a7b0`
- end: `0x18000a7c2`
- name: `?QueryInterface@?$CComObject@VCPreflistFolder@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a7d0`
- `0x18000a7e0`
- `0x18000a7f0`
- `0x18000a800`
- `0x18000a810`
- `0x18000a820`
- `0x18000a830`
- `0x18000a840`

## callees

- `0x180004c88`

## pseudocode

```c
int __fastcall ATL::CComObject<CPreflistFolder>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CPreflistFolder::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000a7b0  mov     r9, r8; void **
0x18000a7b3  mov     r8, rdx; struct _GUID *
0x18000a7b6  lea     rdx, ?_entries@?1??_GetEntries@CPreflistFolder@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000a7bd  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
