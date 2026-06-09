# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::Release`adjustor{8}' (void)

- ea: `0x14000c600`
- end: `0x14000c609`
- name: `?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000c5e0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWMPRichPreviewExt>::Release(__int64 a1)
{
  return ATL::CComContainedObject<CWMPRichPreviewExt>::Release(a1 - 8);
}

```

## disassembly

```asm
0x14000c600  sub     rcx, 8
0x14000c604  jmp     ?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWMPRichPreviewExt>::Release(void)
```
