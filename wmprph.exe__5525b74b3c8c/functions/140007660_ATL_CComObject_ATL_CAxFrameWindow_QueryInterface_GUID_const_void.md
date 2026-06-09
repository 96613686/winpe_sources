# ATL::CComObject<ATL::CAxFrameWindow>::QueryInterface(_GUID const &,void * *)

- ea: `0x140007660`
- end: `0x140007676`
- name: `?QueryInterface@?$CComObject@VCAxFrameWindow@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400059b4`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CAxFrameWindow>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObjectRootBase::InternalQueryInterface(
           (char *)(a1 - 64),
           (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CAxFrameWindow::_GetEntries'::`2'::_entries,
           a2,
           a3);
}

```

## disassembly

```asm
0x140007660  mov     r9, r8; void **
0x140007663  add     rcx, 0FFFFFFFFFFFFFFC0h; void *
0x140007667  mov     r8, rdx; struct _GUID *
0x14000766a  lea     rdx, ?_entries@?1??_GetEntries@CAxFrameWindow@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140007671  jmp     ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
```
