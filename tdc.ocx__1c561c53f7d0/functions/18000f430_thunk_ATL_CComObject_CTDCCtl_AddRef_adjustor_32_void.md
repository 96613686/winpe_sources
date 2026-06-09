# [thunk]:ATL::CComObject<CTDCCtl>::AddRef`adjustor{32}' (void)

- ea: `0x18000f430`
- end: `0x18000f439`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@WCA@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::AddRef(a1 - 32);
}

```

## disassembly

```asm
0x18000f430  sub     rcx, 20h ; ' '
0x18000f434  jmp     ?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::AddRef(void)
```
