# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::Release`adjustor{32}' (void)

- ea: `0x140007960`
- end: `0x140007969`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WCA@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::Release(a1 - 32);
}

```

## disassembly

```asm
0x140007960  sub     rcx, 20h ; ' '
0x140007964  jmp     ?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)
```
