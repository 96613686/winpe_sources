# [thunk]:ATL::CComContainedObject<CRecoExt>::QueryInterface`adjustor{48}' (_GUID const &,void * *)

- ea: `0x180003370`
- end: `0x180003379`
- name: `?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@WDA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComContainedObject<CRecoExt>::QueryInterface(a1 - 48);
}

```

## disassembly

```asm
0x180003370  sub     rcx, 30h ; '0'
0x180003374  jmp     ?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CRecoExt>::QueryInterface(_GUID const &,void * *)
```
