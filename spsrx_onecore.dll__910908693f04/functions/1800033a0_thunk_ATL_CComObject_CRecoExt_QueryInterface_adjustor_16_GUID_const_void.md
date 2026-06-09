# [thunk]:ATL::CComObject<CRecoExt>::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x1800033a0`
- end: `0x1800033a9`
- name: `?QueryInterface@?$CComObject@VCRecoExt@@@ATL@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007390`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CRecoExt>::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return ATL::CComObject<CRecoExt>::QueryInterface((void *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x1800033a0  sub     rcx, 10h
0x1800033a4  jmp     ?QueryInterface@?$CComObject@VCRecoExt@@@ATL@@UEAAJAEBU_GUID@@PEAPEAX@Z; ATL::CComObject<CRecoExt>::QueryInterface(_GUID const &,void * *)
```
