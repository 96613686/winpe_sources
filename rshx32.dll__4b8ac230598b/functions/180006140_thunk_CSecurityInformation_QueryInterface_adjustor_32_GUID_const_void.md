# [thunk]:CSecurityInformation::QueryInterface`adjustor{32}' (_GUID const &,void * *)

- ea: `0x180006140`
- end: `0x180006149`
- name: `?QueryInterface@CSecurityInformation@@WCA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, CSecurityInformation **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c580`

## pseudocode

```c
__int64 __fastcall CSecurityInformation::QueryInterface(__int64 a1, const struct _GUID *a2, CSecurityInformation **a3)
{
  return CSecurityInformation::QueryInterface((CSecurityInformation *)(a1 - 32), a2, a3);
}

```

## disassembly

```asm
0x180006140  sub     rcx, 20h ; ' '; this
0x180006144  jmp     ?QueryInterface@CSecurityInformation@@UEAAJAEBU_GUID@@PEAPEAX@Z; CSecurityInformation::QueryInterface(_GUID const &,void * *)
```
