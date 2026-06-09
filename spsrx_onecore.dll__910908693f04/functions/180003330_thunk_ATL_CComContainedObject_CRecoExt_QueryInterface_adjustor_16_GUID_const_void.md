# [thunk]:ATL::CComContainedObject<CRecoExt>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180003330`
- end: `0x180003339`
- name: `?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return ATL::CComContainedObject<CRecoExt>::QueryInterface(a1 - 16);
}

```

## disassembly

```asm
0x180003330  sub     rcx, 10h
0x180003334  jmp     ?QueryInterface@?$CComContainedObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComContainedObject<CRecoExt>::QueryInterface(_GUID const &,void * *)
```
