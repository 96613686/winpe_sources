# [thunk]:CSecurityExtension::Release`adjustor{8}' (void)

- ea: `0x180009f30`
- end: `0x180009f39`
- name: `?Release@CSecurityExtension@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009f00`

## pseudocode

```c
__int64 __fastcall CSecurityExtension::Release(__int64 a1)
{
  return CSecurityExtension::Release((CSecurityExtension *)(a1 - 8));
}

```

## disassembly

```asm
0x180009f30  sub     rcx, 8; hMem
0x180009f34  jmp     ?Release@CSecurityExtension@@UEAAKXZ; CSecurityExtension::Release(void)
```
