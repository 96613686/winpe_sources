# [thunk]:ATL::CComObject<CTDCCtl>::AddRef`adjustor{80}' (void)

- ea: `0x18000f490`
- end: `0x18000f499`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@WFA@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::AddRef(a1 - 80);
}

```

## disassembly

```asm
0x18000f490  sub     rcx, 50h ; 'P'
0x18000f494  jmp     ?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::AddRef(void)
```
