# [thunk]:ATL::CComObject<CTDCCtl>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180011480`
- end: `0x180011489`
- name: `?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComObject<CTDCCtl>::QueryInterface(a1 - 16, a2, a3);
}

```

## disassembly

```asm
0x180011480  sub     rcx, 10h
0x180011484  jmp     ?QueryInterface@?$CComObject@VCTDCCtl@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CTDCCtl>::QueryInterface(_GUID const &,void * *)
```
