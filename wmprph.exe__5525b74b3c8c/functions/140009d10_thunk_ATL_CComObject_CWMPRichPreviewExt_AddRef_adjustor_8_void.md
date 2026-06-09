# [thunk]:ATL::CComObject<CWMPRichPreviewExt>::AddRef`adjustor{8}' (void)

- ea: `0x140009d10`
- end: `0x140009d19`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009cf0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewExt>::AddRef(__int64 a1)
{
  return ATL::CComObject<CWMPRichPreviewExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x140009d10  sub     rcx, 8
0x140009d14  jmp     ?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewExt>::AddRef(void)
```
