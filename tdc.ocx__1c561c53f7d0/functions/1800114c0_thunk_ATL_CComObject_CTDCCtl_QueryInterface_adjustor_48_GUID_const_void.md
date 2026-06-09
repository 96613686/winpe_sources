# [thunk]:ATL::CComObject<CTDCCtl>::QueryInterface`adjustor{48}' (_GUID const &,void * *)

- ea: `0x1800114c0`
- end: `0x1800114c9`
- name: `?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@WDA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011450`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTDCCtl>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CTDCCtl>::QueryInterface(a1 - 48, a2, a3);
}

```

## disassembly

```asm
0x1800114c0  sub     rcx, 30h ; '0'
0x1800114c4  jmp     ?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CTDCCtl>::QueryInterface(_GUID const &,void * *)
```
