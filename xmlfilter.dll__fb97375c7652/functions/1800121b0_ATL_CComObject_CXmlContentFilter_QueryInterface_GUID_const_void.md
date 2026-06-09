# ATL::CComObject<CXmlContentFilter>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800121b0`
- end: `0x1800121c2`
- name: `?QueryInterface@?$CComObject@VCXmlContentFilter@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, char **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800121d0`
- `0x1800121e0`

## callees

- `0x180011b14`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CComObject<CXmlContentFilter>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CXmlContentFilter::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800121b0  mov     r9, r8; void **
0x1800121b3  mov     r8, rdx; struct _GUID *
0x1800121b6  lea     rdx, ?_entries@?1??_GetEntries@CXmlContentFilter@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800121bd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
