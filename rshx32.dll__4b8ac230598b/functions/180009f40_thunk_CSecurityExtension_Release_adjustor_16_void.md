# [thunk]:CSecurityExtension::Release`adjustor{16}' (void)

- ea: `0x180009f40`
- end: `0x180009f49`
- name: `?Release@CSecurityExtension@@WBA@EAAKXZ`
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
  return CSecurityExtension::Release((CSecurityExtension *)(a1 - 16));
}

```

## disassembly

```asm
0x180009f40  sub     rcx, 10h; hMem
0x180009f44  jmp     ?Release@CSecurityExtension@@UEAAKXZ; CSecurityExtension::Release(void)
```
