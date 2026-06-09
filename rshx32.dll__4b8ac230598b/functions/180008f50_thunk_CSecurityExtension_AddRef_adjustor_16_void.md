# [thunk]:CSecurityExtension::AddRef`adjustor{16}' (void)

- ea: `0x180008f50`
- end: `0x180008f59`
- name: `?AddRef@CSecurityExtension@@WBA@EAAKXZ`
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
  return CSecurityExtension::AddRef((CSecurityExtension *)(a1 - 16));
}

```

## disassembly

```asm
0x180008f50  sub     rcx, 10h; this
0x180008f54  jmp     ?AddRef@CSecurityExtension@@UEAAKXZ; CSecurityExtension::AddRef(void)
```
