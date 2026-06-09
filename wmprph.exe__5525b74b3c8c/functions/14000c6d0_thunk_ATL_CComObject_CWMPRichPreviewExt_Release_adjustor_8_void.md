# [thunk]:ATL::CComObject<CWMPRichPreviewExt>::Release`adjustor{8}' (void)

- ea: `0x14000c6d0`
- end: `0x14000c6d9`
- name: `?Release@?$CComObject@VCWMPRichPreviewExt@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CWMPRichPreviewExt>::Release((CWMPRichPreviewExt *)(a1 - 8));
}

```

## disassembly

```asm
0x14000c6d0  sub     rcx, 8; this
0x14000c6d4  jmp     ?Release@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewExt>::Release(void)
```
