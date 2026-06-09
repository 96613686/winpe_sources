# [thunk]:ATL::CComObject<CWMPRichPreviewExt>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x14000b670`
- end: `0x14000b679`
- name: `?QueryInterface@?$CComObject@VCWMPRichPreviewExt@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b650`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewExt>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CWMPRichPreviewExt>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x14000b670  sub     rcx, 8
0x14000b674  jmp     ?QueryInterface@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CWMPRichPreviewExt>::QueryInterface(_GUID const &,void * *)
```
