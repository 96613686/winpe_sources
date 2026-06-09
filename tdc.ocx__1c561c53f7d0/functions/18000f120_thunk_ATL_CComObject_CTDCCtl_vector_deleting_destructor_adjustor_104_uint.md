# [thunk]:ATL::CComObject<CTDCCtl>::`vector deleting destructor'`adjustor{104}' (uint)

- ea: `0x18000f120`
- end: `0x18000f129`
- name: `??_E?$CComObject@VCTDCCtl@@@ATL@@WGI@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f130`

## pseudocode

```c
CTDCCtl *__fastcall ATL::CComObject<CTDCCtl>::`vector deleting destructor'(__int64 a1, char a2)
{
  return ATL::CComObject<CTDCCtl>::`vector deleting destructor'((CTDCCtl *)(a1 - 104), a2);
}

```

## disassembly

```asm
0x18000f120  sub     rcx, 68h ; 'h'; Block
0x18000f124  jmp     ??_E?$CComObject@VCTDCCtl@@@ATL@@UEAAPEAXI@Z; ATL::CComObject<CTDCCtl>::`vector deleting destructor'(uint)
```
