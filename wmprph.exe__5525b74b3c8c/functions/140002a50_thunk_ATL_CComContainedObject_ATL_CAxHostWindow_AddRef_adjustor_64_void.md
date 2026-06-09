# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef`adjustor{64}' (void)

- ea: `0x140002a50`
- end: `0x140002a59`
- name: `?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WEA@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(a1 - 64);
}

```

## disassembly

```asm
0x140002a50  sub     rcx, 40h ; '@'
0x140002a54  jmp     ?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(void)
```
