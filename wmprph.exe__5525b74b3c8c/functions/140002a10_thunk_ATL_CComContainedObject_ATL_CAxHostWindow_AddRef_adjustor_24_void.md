# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef`adjustor{24}' (void)

- ea: `0x140002a10`
- end: `0x140002a19`
- name: `?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400029d0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x140002a10  sub     rcx, 18h
0x140002a14  jmp     ?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(void)
```
