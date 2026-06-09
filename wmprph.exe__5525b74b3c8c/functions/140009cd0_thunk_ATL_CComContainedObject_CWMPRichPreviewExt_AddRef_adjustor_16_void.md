# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef`adjustor{16}' (void)

- ea: `0x140009cd0`
- end: `0x140009cd9`
- name: `?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x140009cd0  sub     rcx, 10h
0x140009cd4  jmp     ?AddRef@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWMPRichPreviewExt>::AddRef(void)
```
