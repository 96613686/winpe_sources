# [thunk]:ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface`adjustor{72}' (_GUID const &,void * *)

- ea: `0x140007620`
- end: `0x140007629`
- name: `?QueryInterface@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@WEI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(a1 - 72, a2, a3);
}

```

## disassembly

```asm
0x140007620  sub     rcx, 48h ; 'H'
0x140007624  jmp     ?QueryInterface@?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<ATL::CAxHostWindow>::QueryInterface(_GUID const &,void * *)
```
