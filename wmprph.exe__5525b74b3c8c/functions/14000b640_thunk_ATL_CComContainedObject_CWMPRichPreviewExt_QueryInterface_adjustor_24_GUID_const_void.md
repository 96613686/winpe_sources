# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x14000b640`
- end: `0x14000b649`
- name: `?QueryInterface@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b5c0`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface(
        __int64 a1,
        struct _GUID *a2,
        char **a3)
{
  return ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface((char *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x14000b640  sub     rcx, 18h; void *
0x14000b644  jmp     ?QueryInterface@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface(_GUID const &,void * *)
```
