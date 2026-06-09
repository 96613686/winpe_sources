# ATL::CComObject<CWinInetHelperClass>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000af50`
- end: `0x18000af62`
- name: `?QueryInterface@?$CComObject@VCWinInetHelperClass@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000af70`
- `0x18000af80`

## callees

- `0x1800086a8`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWinInetHelperClass>::QueryInterface(char *a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           a1,
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`CNetDiagHelperEx::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000af50  mov     r9, r8; void **
0x18000af53  mov     r8, rdx; struct _GUID *
0x18000af56  lea     rdx, ?_entries@?1??_GetEntries@CNetDiagHelperEx@@SAPEBU_ATL_INTMAP_ENTRY@ATL@@XZ@4QBU34@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000af5d  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
