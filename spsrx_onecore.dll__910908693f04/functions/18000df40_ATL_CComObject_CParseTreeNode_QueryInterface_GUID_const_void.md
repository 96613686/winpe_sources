# ATL::CComObject<CParseTreeNode>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000df40`
- end: `0x18000df52`
- name: `?QueryInterface@?$CComObject@VCParseTreeNode@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800019a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CParseTreeNode>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CParseTreeNode::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000df40  mov     r9, r8; void **
0x18000df43  mov     r8, rdx; struct _GUID *
0x18000df46  lea     rdx, ?_entries@?1??_GetEntries@CParseTreeNode@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000df4d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
