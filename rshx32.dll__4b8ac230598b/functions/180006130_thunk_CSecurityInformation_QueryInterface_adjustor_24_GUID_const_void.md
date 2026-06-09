# [thunk]:CSecurityInformation::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x180006130`
- end: `0x180006139`
- name: `?QueryInterface@CSecurityInformation@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return CSecurityInformation::QueryInterface((CSecurityInformation *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x180006130  sub     rcx, 18h; this
0x180006134  jmp     ?QueryInterface@CSecurityInformation@@UEAAJAEBU_GUID@@PEAPEAX@Z; CSecurityInformation::QueryInterface(_GUID const &,void * *)
```
