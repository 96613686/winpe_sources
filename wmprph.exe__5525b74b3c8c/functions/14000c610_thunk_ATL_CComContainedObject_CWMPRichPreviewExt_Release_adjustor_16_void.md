# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::Release`adjustor{16}' (void)

- ea: `0x14000c610`
- end: `0x14000c619`
- name: `?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComContainedObject<CWMPRichPreviewExt>::Release(a1 - 16);
}

```

## disassembly

```asm
0x14000c610  sub     rcx, 10h
0x14000c614  jmp     ?Release@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAKXZ; ATL::CComContainedObject<CWMPRichPreviewExt>::Release(void)
```
