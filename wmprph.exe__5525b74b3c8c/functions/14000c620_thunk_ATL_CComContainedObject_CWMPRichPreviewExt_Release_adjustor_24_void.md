# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::Release`adjustor{24}' (void)

- ea: `0x14000c620`
- end: `0x14000c629`
- name: `?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@WBI@EAAKXZ`
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
  return ATL::CComContainedObject<CWMPRichPreviewExt>::Release(a1 - 24);
}

```

## disassembly

```asm
0x14000c620  sub     rcx, 18h
0x14000c624  jmp     ?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWMPRichPreviewExt>::Release(void)
```
