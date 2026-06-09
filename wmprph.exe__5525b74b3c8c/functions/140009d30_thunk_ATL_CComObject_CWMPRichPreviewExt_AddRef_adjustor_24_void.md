# [thunk]:ATL::CComObject<CWMPRichPreviewExt>::AddRef`adjustor{24}' (void)

- ea: `0x140009d30`
- end: `0x140009d39`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComObject<CWMPRichPreviewExt>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x140009d30  sub     rcx, 18h
0x140009d34  jmp     ?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewExt>::AddRef(void)
```
