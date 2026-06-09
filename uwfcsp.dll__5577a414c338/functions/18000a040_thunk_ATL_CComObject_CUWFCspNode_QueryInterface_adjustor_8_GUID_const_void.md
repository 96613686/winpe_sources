# [thunk]:ATL::CComObject<CUWFCspNode>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000a040`
- end: `0x18000a049`
- name: `?QueryInterface@?$CComObject@VCUWFCspNode@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a020`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspNode>::QueryInterface(__int64 a1, const struct _GUID *a2, char **a3)
{
  return ATL::CComObject<CUWFCspNode>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000a040  sub     rcx, 8
0x18000a044  jmp     ?QueryInterface@?$CComObject@VCUWFCspNode@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CUWFCspNode>::QueryInterface(_GUID const &,void * *)
```
