# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::Release`adjustor{72}' (void)

- ea: `0x1400079a0`
- end: `0x1400079a9`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WEI@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::Release(a1 - 72);
}

```

## disassembly

```asm
0x1400079a0  sub     rcx, 48h ; 'H'
0x1400079a4  jmp     ?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)
```
