# [thunk]:ATL::CComObject<CUWFCspNextSessionNode>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000f890`
- end: `0x18000f899`
- name: `?QueryInterface@?$CComObject@VCUWFCspNextSessionNode@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f870`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspNextSessionNode>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CUWFCspNextSessionNode>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000f890  sub     rcx, 8
0x18000f894  jmp     ?QueryInterface@?$CComObject@VCUWFCspNextSessionNode@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CUWFCspNextSessionNode>::QueryInterface(_GUID const &,void * *)
```
