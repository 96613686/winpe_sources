# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{104}' (void)

- ea: `0x180012410`
- end: `0x180012419`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@WGI@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::Release(a1 - 104);
}

```

## disassembly

```asm
0x180012410  sub     rcx, 68h ; 'h'
0x180012414  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
