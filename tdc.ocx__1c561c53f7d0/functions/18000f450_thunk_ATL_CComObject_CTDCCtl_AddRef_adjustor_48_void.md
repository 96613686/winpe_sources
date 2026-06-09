# [thunk]:ATL::CComObject<CTDCCtl>::AddRef`adjustor{48}' (void)

- ea: `0x18000f450`
- end: `0x18000f459`
- name: `?AddRef@?$CComObject@VCTDCCtl@@@ATL@@WDA@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::AddRef(a1 - 48);
}

```

## disassembly

```asm
0x18000f450  sub     rcx, 30h ; '0'
0x18000f454  jmp     ?AddRef@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::AddRef(void)
```
