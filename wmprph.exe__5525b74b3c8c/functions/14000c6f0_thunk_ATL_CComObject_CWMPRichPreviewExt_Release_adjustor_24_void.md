# [thunk]:ATL::CComObject<CWMPRichPreviewExt>::Release`adjustor{24}' (void)

- ea: `0x14000c6f0`
- end: `0x14000c6f9`
- name: `?Release@?$CComObject@VCWMPRichPreviewExt@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000c630`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewExt>::Release(__int64 a1)
{
  return ATL::CComObject<CWMPRichPreviewExt>::Release((CWMPRichPreviewExt *)(a1 - 24));
}

```

## disassembly

```asm
0x14000c6f0  sub     rcx, 18h; this
0x14000c6f4  jmp     ?Release@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewExt>::Release(void)
```
