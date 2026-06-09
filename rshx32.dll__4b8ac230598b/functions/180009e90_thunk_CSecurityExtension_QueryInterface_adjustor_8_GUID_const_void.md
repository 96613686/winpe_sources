# [thunk]:CSecurityExtension::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180009e90`
- end: `0x180009e99`
- name: `?QueryInterface@CSecurityExtension@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return CSecurityExtension::QueryInterface((CSecurityExtension *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180009e90  sub     rcx, 8; this
0x180009e94  jmp     ?QueryInterface@CSecurityExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z; CSecurityExtension::QueryInterface(_GUID const &,void * *)
```
