# [thunk]:ATL::CComObject<CTDCCtl>::Release`adjustor{16}' (void)

- ea: `0x180012380`
- end: `0x180012389`
- name: `?Release@?$CComObject@VCTDCCtl@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CTDCCtl>::Release(a1 - 16);
}

```

## disassembly

```asm
0x180012380  sub     rcx, 10h
0x180012384  jmp     ?Release@?$CComObject@VCTDCCtl@@@ATL@@UEAAKXZ; ATL::CComObject<CTDCCtl>::Release(void)
```
