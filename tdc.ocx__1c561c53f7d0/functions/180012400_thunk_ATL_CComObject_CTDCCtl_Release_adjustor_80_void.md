# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{80}' (void)

- ea: `0x180012400`
- end: `0x180012409`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@WFA@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::Release(a1 - 80);
}

```

## disassembly

```asm
0x180012400  sub     rcx, 50h ; 'P'
0x180012404  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
