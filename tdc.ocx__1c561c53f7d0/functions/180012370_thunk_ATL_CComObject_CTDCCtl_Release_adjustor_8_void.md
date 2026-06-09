# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{8}' (void)

- ea: `0x180012370`
- end: `0x180012379`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::Release(a1 - 8);
}

```

## disassembly

```asm
0x180012370  sub     rcx, 8
0x180012374  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
