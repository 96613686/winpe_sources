# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef`adjustor{8}' (void)

- ea: `0x1400029f0`
- end: `0x1400029f9`
- name: `?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@W7EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x1400029f0  sub     rcx, 8
0x1400029f4  jmp     ?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(void)
```
