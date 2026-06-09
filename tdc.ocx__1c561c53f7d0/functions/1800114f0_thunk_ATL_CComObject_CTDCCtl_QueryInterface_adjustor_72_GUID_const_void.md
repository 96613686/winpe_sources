# [thunk]:ATL::CComObject<CTDCCtl>::QueryInterface`adjustor{72}' (_GUID const &,void * *)

- ea: `0x1800114f0`
- end: `0x1800114f9`
- name: `?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@WEI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CTDCCtl>::QueryInterface(a1 - 72, a2, a3);
}

```

## disassembly

```asm
0x1800114f0  sub     rcx, 48h ; 'H'
0x1800114f4  jmp     ?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CTDCCtl>::QueryInterface(_GUID const &,void * *)
```
