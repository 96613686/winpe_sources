# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::Release`adjustor{56}' (void)

- ea: `0x140007980`
- end: `0x140007989`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WDI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007910`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::Release(__int64 a1)
{
  return ATL::CComContainedObject<ATL::CAxHostWindow>::Release(a1 - 56);
}

```

## disassembly

```asm
0x140007980  sub     rcx, 38h ; '8'
0x140007984  jmp     ?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)
```
