# [thunk]:ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x14000b630`
- end: `0x14000b639`
- name: `?QueryInterface@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface((char *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x14000b630  sub     rcx, 10h; void *
0x14000b634  jmp     ?QueryInterface@?$CComContainedObject@VCWMPRichPreviewExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CWMPRichPreviewExt>::QueryInterface(_GUID const &,void * *)
```
