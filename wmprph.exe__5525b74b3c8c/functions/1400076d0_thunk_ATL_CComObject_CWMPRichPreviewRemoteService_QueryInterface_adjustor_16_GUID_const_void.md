# [thunk]:ATL::CComObject<CWMPRichPreviewRemoteService>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x1400076d0`
- end: `0x1400076d9`
- name: `?QueryInterface@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400076a0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWMPRichPreviewRemoteService>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComObject<CWMPRichPreviewRemoteService>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x1400076d0  sub     rcx, 10h
0x1400076d4  jmp     ?QueryInterface@?$CComObject@VCWMPRichPreviewRemoteService@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CWMPRichPreviewRemoteService>::QueryInterface(_GUID const &,void * *)
```
