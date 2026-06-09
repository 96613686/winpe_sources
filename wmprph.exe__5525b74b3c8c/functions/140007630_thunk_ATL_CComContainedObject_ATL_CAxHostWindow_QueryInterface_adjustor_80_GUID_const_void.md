# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface`adjustor{80}' (_GUID const &,void * *)

- ea: `0x140007630`
- end: `0x140007639`
- name: `?QueryInterface@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WFA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007540`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        char **a3)
{
  return ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(a1 - 80, a2, a3);
}

```

## disassembly

```asm
0x140007630  sub     rcx, 50h ; 'P'
0x140007634  jmp     ?QueryInterface@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(_GUID const &,void * *)
```
