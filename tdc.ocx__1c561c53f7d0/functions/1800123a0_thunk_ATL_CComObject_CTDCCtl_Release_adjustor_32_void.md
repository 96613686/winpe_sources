# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{32}' (void)

- ea: `0x1800123a0`
- end: `0x1800123a9`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@WCA@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::Release(a1 - 32);
}

```

## disassembly

```asm
0x1800123a0  sub     rcx, 20h ; ' '
0x1800123a4  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
