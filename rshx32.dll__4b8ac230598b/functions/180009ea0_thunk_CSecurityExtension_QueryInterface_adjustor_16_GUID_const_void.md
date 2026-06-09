# [thunk]:CSecurityExtension::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x180009ea0`
- end: `0x180009ea9`
- name: `?QueryInterface@CSecurityExtension@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, CSecurityExtension **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009de0`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::QueryInterface(__int64 a1, const struct _GUID *a2, CSecurityExtension **a3)
{
  return CSecurityExtension::QueryInterface((CSecurityExtension *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x180009ea0  sub     rcx, 10h; this
0x180009ea4  jmp     ?QueryInterface@CSecurityExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z; CSecurityExtension::QueryInterface(_GUID const &,void * *)
```
