# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::Release`adjustor{16}' (void)

- ea: `0x140007940`
- end: `0x140007949`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::Release(a1 - 16);
}

```

## disassembly

```asm
0x140007940  sub     rcx, 10h
0x140007944  jmp     ?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)
```
