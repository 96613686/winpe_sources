# [thunk]:ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef`adjustor{8}' (void)

- ea: `0x140002ae0`
- end: `0x140002ae9`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002ac0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(__int64 a1)
{
  return ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(a1 - 8);
}

```

## disassembly

```asm
0x140002ae0  sub     rcx, 8
0x140002ae4  jmp     ?AddRef@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(void)
```
