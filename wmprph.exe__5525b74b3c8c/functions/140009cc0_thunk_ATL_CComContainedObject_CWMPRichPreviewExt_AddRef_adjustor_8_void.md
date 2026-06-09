# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef`adjustor{8}' (void)

- ea: `0x140009cc0`
- end: `0x140009cc9`
- name: `?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@W7EAAKXZ`
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
  return ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x140009cc0  sub     rcx, 8
0x140009cc4  jmp     ?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(void)
```
