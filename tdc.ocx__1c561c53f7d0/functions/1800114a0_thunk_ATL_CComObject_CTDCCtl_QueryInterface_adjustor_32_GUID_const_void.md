# [thunk]:ATL::CComObject<CTDCCtl>::QueryInterface`adjustor{32}' (_GUID const &,void * *)

- ea: `0x1800114a0`
- end: `0x1800114a9`
- name: `?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@WCA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CTDCCtl>::QueryInterface(a1 - 32, a2, a3);
}

```

## disassembly

```asm
0x1800114a0  sub     rcx, 20h ; ' '
0x1800114a4  jmp     ?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CTDCCtl>::QueryInterface(_GUID const &,void * *)
```
