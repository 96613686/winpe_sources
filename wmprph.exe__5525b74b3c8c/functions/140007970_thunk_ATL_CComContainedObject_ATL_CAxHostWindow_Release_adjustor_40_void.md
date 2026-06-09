# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::Release`adjustor{40}' (void)

- ea: `0x140007970`
- end: `0x140007979`
- name: `?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WCI@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::Release(a1 - 40);
}

```

## disassembly

```asm
0x140007970  sub     rcx, 28h ; '('
0x140007974  jmp     ?Release@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::Release(void)
```
