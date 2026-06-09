# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{72}' (void)

- ea: `0x1800123f0`
- end: `0x1800123f9`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@WEI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800122e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTDCCtl>::Release(__int64 a1)
{
  return ATL::CComObject<CTDCCtl>::Release(a1 - 72);
}

```

## disassembly

```asm
0x1800123f0  sub     rcx, 48h ; 'H'
0x1800123f4  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
