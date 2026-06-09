# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::Release`adjustor{80}' (void)

- ea: `0x1400079b0`
- end: `0x1400079b9`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WFA@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::Release(a1 - 80);
}

```

## disassembly

```asm
0x1400079b0  sub     rcx, 50h ; 'P'
0x1400079b4  jmp     ?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)
```
