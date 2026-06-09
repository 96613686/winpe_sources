# [thunk]:ATL::CComObject<CTDCCtl>::AddRef`adjustor{16}' (void)

- ea: `0x18000f410`
- end: `0x18000f419`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f3e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTDCCtl>::AddRef(__int64 a1)
{
  return ATL::CComObject<CTDCCtl>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x18000f410  sub     rcx, 10h
0x18000f414  jmp     ?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::AddRef(void)
```
