# [thunk]:ATL::CComObject<CUWFCspCurrentSessionNode>::AddRef`adjustor{8}' (void)

- ea: `0x1800085a0`
- end: `0x1800085a9`
- name: `?AddRef@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008570`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CUWFCspCurrentSessionNode>::AddRef(__int64 a1)
{
  return ATL::CComObject<CUWFCspNode>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1800085a0  sub     rcx, 8
0x1800085a4  jmp     ?AddRef@?$CComObject@VCUWFCspNode@@@ATL@@UEAAKXZ; ATL::CComObject<CUWFCspNode>::AddRef(void)
```
