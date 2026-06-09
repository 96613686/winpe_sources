# [thunk]:ATL::CComContainedObject<CRecoExt>::QueryInterface`adjustor{40}' (_GUID const &,void * *)

- ea: `0x180003360`
- end: `0x180003369`
- name: `?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@WCI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007370`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CRecoExt>::QueryInterface(__int64 a1)
{
  return ATL::CComContainedObject<CRecoExt>::QueryInterface(a1 - 40);
}

```

## disassembly

```asm
0x180003360  sub     rcx, 28h ; '('
0x180003364  jmp     ?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CRecoExt>::QueryInterface(_GUID const &,void * *)
```
