# [thunk]:ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef`adjustor{16}' (void)

- ea: `0x140002af0`
- end: `0x140002af9`
- name: `?AddRef@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@WBA@EAAKXZ`
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
  return ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x140002af0  sub     rcx, 10h
0x140002af4  jmp     ?AddRef@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAKXZ; ATL::CComObject<CWMPRichPreviewRemoteService>::AddRef(void)
```
