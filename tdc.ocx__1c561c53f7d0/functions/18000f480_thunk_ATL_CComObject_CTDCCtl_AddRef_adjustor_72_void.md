# [thunk]:ATL::CComObject<CTDCCtl>::AddRef`adjustor{72}' (void)

- ea: `0x18000f480`
- end: `0x18000f489`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@WEI@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::AddRef(a1 - 72);
}

```

## disassembly

```asm
0x18000f480  sub     rcx, 48h ; 'H'
0x18000f484  jmp     ?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::AddRef(void)
```
