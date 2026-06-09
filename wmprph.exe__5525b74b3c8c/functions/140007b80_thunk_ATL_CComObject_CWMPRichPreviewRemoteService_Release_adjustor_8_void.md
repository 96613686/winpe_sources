# [thunk]:ATL::CComObject<CWMPRichPreviewRemoteService>::Release`adjustor{8}' (void)

- ea: `0x140007b80`
- end: `0x140007b89`
- name: `?Release@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@W7EAAKXZ`
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
  return ATL::CComObject<CWMPRichPreviewRemoteService>::Release((_DWORD *)(a1 - 8));
}

```

## disassembly

```asm
0x140007b80  sub     rcx, 8; void *
0x140007b84  jmp     ?Release@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewRemoteService>::Release(void)
```
