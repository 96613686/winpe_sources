# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef`adjustor{24}' (void)

- ea: `0x140009ce0`
- end: `0x140009ce9`
- name: `?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009ca0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(__int64 a1)
{
  return ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x140009ce0  sub     rcx, 18h
0x140009ce4  jmp     ?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(void)
```
