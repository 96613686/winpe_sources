# ATL::CComObject<CWdsSimpleDeviceController>::QueryInterface(_GUID const &,void * *)

- ea: `0x180004030`
- end: `0x180004042`
- name: `?QueryInterface@?$CComObject@VCWdsSimpleDeviceController@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004050`

## callees

- `0x18000391c`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsSimpleDeviceController>::QueryInterface(
        char *a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CWdsSimpleDeviceController::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x180004030  mov     r9, r8; void **
0x180004033  mov     r8, rdx; struct _GUID *
0x180004036  lea     rdx, ?_entries@?1??_GetEntries@CWdsSimpleDeviceController@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000403d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
