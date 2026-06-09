# [thunk]:ATL::CComObject<CWMPRichPreviewRemoteService>::Release`adjustor{16}' (void)

- ea: `0x140007b90`
- end: `0x140007b99`
- name: `?Release@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007b20`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::Release(__int64 a1)
{
  return ATL::CComObject<CWMPRichPreviewRemoteService>::Release((_DWORD *)(a1 - 16));
}

```

## disassembly

```asm
0x140007b90  sub     rcx, 10h; void *
0x140007b94  jmp     ?Release@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewRemoteService>::Release(void)
```
