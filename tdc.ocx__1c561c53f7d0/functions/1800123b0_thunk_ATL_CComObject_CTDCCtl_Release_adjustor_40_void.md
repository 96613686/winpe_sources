# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{40}' (void)

- ea: `0x1800123b0`
- end: `0x1800123b9`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@WCI@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::Release(a1 - 40);
}

```

## disassembly

```asm
0x1800123b0  sub     rcx, 28h ; '('
0x1800123b4  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
