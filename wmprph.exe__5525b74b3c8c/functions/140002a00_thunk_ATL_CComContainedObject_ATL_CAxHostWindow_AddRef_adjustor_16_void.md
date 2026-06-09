# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef`adjustor{16}' (void)

- ea: `0x140002a00`
- end: `0x140002a09`
- name: `?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x140002a00  sub     rcx, 10h
0x140002a04  jmp     ?AddRef@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ; ATL::CComContainedObject<ATL::CAxHostWindow>::AddRef(void)
```
