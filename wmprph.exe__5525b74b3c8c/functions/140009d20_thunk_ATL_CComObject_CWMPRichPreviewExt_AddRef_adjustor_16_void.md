# [thunk]:ATL::CComObject<CWMPRichPreviewExt>::AddRef`adjustor{16}' (void)

- ea: `0x140009d20`
- end: `0x140009d29`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CWMPRichPreviewExt>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x140009d20  sub     rcx, 10h
0x140009d24  jmp     ?AddRef@?$CComObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewExt>::AddRef(void)
```
