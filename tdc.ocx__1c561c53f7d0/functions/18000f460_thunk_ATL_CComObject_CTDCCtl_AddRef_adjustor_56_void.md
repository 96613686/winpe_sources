# [thunk]:ATL::CComObject<CTDCCtl>::AddRef`adjustor{56}' (void)

- ea: `0x18000f460`
- end: `0x18000f469`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@WDI@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::AddRef(a1 - 56);
}

```

## disassembly

```asm
0x18000f460  sub     rcx, 38h ; '8'
0x18000f464  jmp     ?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::AddRef(void)
```
