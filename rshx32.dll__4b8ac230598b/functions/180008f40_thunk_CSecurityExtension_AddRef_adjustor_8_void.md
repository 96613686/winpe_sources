# [thunk]:CSecurityExtension::AddRef`adjustor{8}' (void)

- ea: `0x180008f40`
- end: `0x180008f49`
- name: `?AddRef@CSecurityExtension@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008f30`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::AddRef(__int64 a1)
{
  return CSecurityExtension::AddRef((CSecurityExtension *)(a1 - 8));
}

```

## disassembly

```asm
0x180008f40  sub     rcx, 8; this
0x180008f44  jmp     ?AddRef@CSecurityExtension@@UEAAKXZ; CSecurityExtension::AddRef(void)
```
