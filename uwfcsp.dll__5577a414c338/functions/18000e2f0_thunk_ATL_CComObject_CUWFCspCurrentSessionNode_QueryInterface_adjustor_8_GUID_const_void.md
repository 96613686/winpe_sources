# [thunk]:ATL::CComObject<CUWFCspCurrentSessionNode>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x18000e2f0`
- end: `0x18000e2f9`
- name: `?QueryInterface@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e2d0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspCurrentSessionNode>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CUWFCspCurrentSessionNode>::QueryInterface((char *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x18000e2f0  sub     rcx, 8
0x18000e2f4  jmp     ?QueryInterface@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CUWFCspCurrentSessionNode>::QueryInterface(_GUID const &,void * *)
```
