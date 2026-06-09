# ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800086c0`
- end: `0x1800086d2`
- name: `?QueryInterface@?$CComObject@V?$CMyBindStatusCallback@VCTDCCtl@@@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800086e0`
- `0x1800086f0`
- `0x180008700`

## callees

- `0x1800070ac`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMyBindStatusCallback<CTDCCtl>>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CMyBindStatusCallback<CTDCCtl>::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800086c0  mov     r9, r8; void **
0x1800086c3  mov     r8, rdx; struct _GUID *
0x1800086c6  lea     rdx, ?_entries@?1??_GetEntries@?$CMyBindStatusCallback@VCTDCCtl@@@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800086cd  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
