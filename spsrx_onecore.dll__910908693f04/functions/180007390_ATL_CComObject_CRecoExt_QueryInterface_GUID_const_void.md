# ATL::CComObject<CRecoExt>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007390`
- end: `0x1800073a2`
- name: `?QueryInterface@?$CComObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003390`
- `0x1800033a0`
- `0x1800033b0`
- `0x1800033c0`
- `0x1800033d0`
- `0x1800033e0`
- `0x1800033f0`

## callees

- `0x1800019a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRecoExt>::QueryInterface(void *a1, const struct _GUID *a2, void **a3)
{
  return ATL::AtlInternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CRecoExt::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180007390  mov     r9, r8; void **
0x180007393  mov     r8, rdx; struct _GUID *
0x180007396  lea     rdx, ?_entries@?1??_GetEntries@CRecoExt@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000739d  jmp     ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
